# 🎨 FRONTEND DEVELOPMENT ROADMAP

> **🎯 AMAÇ:** Hızlı ve etkili frontend geliştirme - AI destekli, müşteriye gösterilebilir prototip.  
> **SÜRE:** 1-2 hafta  
> **ARAÇLAR:** VS Code + GitHub Copilot, Next.js 14, Tailwind CSS, Framer Motion

**Proje:** [COMPANY_NAME] - Frontend Geliştirme  
**Teknoloji:** Next.js 14+ (App Router), TypeScript, Tailwind CSS 3.4+, Framer Motion 11.11+  
**Backend:** Henüz yok - Mock/Static verilerle çalış  
**Hedef:** Müşteriye gösterilebilir, responsive, animasyonlu frontend  
**Versiyon:** 1.0 (Frontend-Only)  
**Son Güncelleme:** 29.11.2025

> **⚠️ ÖNEMLI NOT - Base64 Resim Problemi:**
> 
> Bu projede `Gereksinim Analizi.md` dosyasında base64 kodlu resimler bulunmaktadır. Bu resimler AI model karakter limitini aştığı için şu çözüm uygulanmıştır:
> 
> - **Kaynak Dosya:** `Gereksinim Analizi.pdf` (orijinal döküman)
> - **İşlenmiş Dosya:** `Gereksinim Analizi.md` (base64 resimler çıkarılmış)
> - **Resim Referansları:** PDF sayfa numaraları ile verilmiştir
> 
> AI'ya prompt gönderirken bu referans sistemini kullanın!

---

## 📑 İÇINDEKİLER

1. [Faz 0: Proje Hazırlık ve Next.js Kurulumu](#-faz-0-proje-hazirlik-ve-nextjs-kurulumu)
2. [Faz 1: Design System ve Temel Yapı](#-faz-1-design-system-ve-temel-yapi)
3. [Faz 2: Global Componentler](#-faz-2-global-componentler)
4. [Faz 3: Landing Page](#-faz-3-landing-page)
5. [Faz 4: Modül Sayfaları](#-faz-4-modül-sayfalari)
6. [Faz 5: Animasyonlar ve Polish](#-faz-5-animasyonlar-ve-polish)
7. [Faz 6: Responsive ve Accessibility](#-faz-6-responsive-ve-accessibility)
8. [Faz 7: Mock Data ve Test](#-faz-7-mock-data-ve-test)

---

## 🎯 FAZ 0: PROJE HAZIRLIK VE NEXT.JS KURULUMU

> **SÜRE:** 15 dakika  
> **ÇIKTI:** Çalışan Next.js projesi + Git repository

### 0.1 Boş Proje Klasörü Oluşturma

**Adımlar:**

1. **Windows Explorer'da klasör oluştur:**
   ```
   C:\Repos\HAVSAN\[project-name]-frontend-app
   ```
   
   > **💡 İsimlendirme Örneği:**  
   > `havsan-group-website-frontend-app`
   >
   > **ÖNEMLİ:** Bu klasör **havsan-grup-app**'ten FARKLI bir klasördür!  
   > - `havsan-grup-app` → Template repository (şablon deposu)  
   > - `[project-name]-frontend-app` → Gerçek proje (geliştirme yapılacak)

2. **VS Code ile aç:**
   - VS Code'u aç
   - `File → Open Folder`
   - Oluşturduğun **boş** klasörü seç

3. **VS Code'da Terminal aç:**
   - `` Ctrl + ` `` (backtick tuşu)
   - Veya `Terminal → New Terminal`

**✅ Kontrol:** Terminal'de pwd komutu çalıştır, doğru klasörde olduğunu doğrula:
```powershell
pwd  # Çıktı: C:\Repos\HAVSAN\[project-name]-frontend-app olmalı
```

---

### 0.2 Next.js Projesi Kurulumu (Boş Klasörde)

**Terminal'de çalıştır:**

```powershell
# Next.js kur (mevcut klasörde - nokta işareti önemli!)
npx create-next-app@latest . --typescript --tailwind --app --no-src-dir
```

**Sorulacak Sorular ve Cevaplar:**
- `Which linter would you like to use?` → **ESLint** (Enter)
- `Would you like to use React Compiler?` → **No** (Enter)
- `Would you like to customize the import alias?` → **No** (Enter)

> **⚡ Kurulum süresi:** 2-3 dakika

---

### 0.3 FRONTEND-DOCS Klasörü ve Müşteri Dökümanlarını Ekleme

**Terminal'de çalıştır:**

```powershell
# Frontend doküman klasörlerini oluştur
mkdir FRONTEND-DOCS
mkdir FRONTEND-DOCS\Gereksinim-Analizi
mkdir FRONTEND-DOCS\Files
mkdir FRONTEND-DOCS\Files\Logolar
mkdir FRONTEND-DOCS\Files\Bilgi-Belge-Gorsel
```

**Klasör yapısı:**
```
FRONTEND-DOCS/
├── FRONTEND-ROADMAP.md              # Bu dosya (şablon reposundan kopyalanacak)
├── FRONTEND-PRD.md                  # AI ile oluşturulacak (Faz 0.8)
├── FRONTEND-TASKS.md                # AI ile oluşturulacak (Faz 0.9)
├── API-CONTRACT.md                  # İleride oluşturulacak
│
├── Gereksinim-Analizi/              # İster dökümanları (AI'ya INPUT)
│   ├── Gereksinim Analizi.pdf       # Müşteriden gelen PDF
│   ├── Gereksinim Analizi.md        # PDF'den markdown'a çevrilmiş
│   └── Ek-Notlar.txt                # (Opsiyonel) Email'ler, notlar
│
└── Files/                           # Statik dosyalar (Projeye dahil edilecek)
    ├── Logolar/                     # Company logo, referans logoları
    │   ├── company-logo.png
    │   └── company-logo.svg
    └── Bilgi-Belge-Gorsel/          # Sertifikalar, görseller
        ├── sertifikalar/
        └── referans-screenshots/
```

**🔹 FRONTEND-ROADMAP.md'yi Kopyala:**

```powershell
# Şablon reposundan bu dosyayı kopyala (template path'ini güncelle)
Copy-Item "C:\Repos\HAVSAN\havsan-grup-app\FRONTEND-DOCS\FRONTEND-ROADMAP.md" -Destination ".\FRONTEND-DOCS\"

# Veya manuel olarak: File Explorer'da kopyala-yapıştır
```

> **💡 NOT:** `havsan-grup-app` klasörü şirketinizin template repository'sidir. Her yeni proje başlangıcında FRONTEND-ROADMAP.md'yi buradan kopyalayın.

**🔹 Şimdi Müşteri Dökümanlarını Ekle:**

1. **İster Dokümanı (AI'ya verilecek):**
   ```
   FRONTEND-DOCS/Gereksinim-Analizi/ klasörüne kopyala
   
   Örnek:
   - Gereksinim Analizi.pdf (müşteriden gelen orijinal - KAYNAK)
   - Gereksinim Analizi.md (PDF'den markdown'a çevrilmiş, base64 resimler çıkarılmış)
   - Ek-Notlar.txt (müşteri email'leri, toplantı notları)
   ```

2. **Logolar (projeye dahil edilecek):**
   ```
   FRONTEND-DOCS/Files/Logolar/ klasörüne kopyala
   
   Örnek:
   - company-logo.png
   - company-logo.svg
   - favicon.ico
   ```

3. **Diğer Görseller (projeye dahil edilecek):**
   ```
   FRONTEND-DOCS/Files/Bilgi-Belge-Gorsel/ klasörüne kopyala
   
   Örnek:
   - sertifikalar/ (ISO belgeleri PDF - web'de gösterilecek)
   - referans-screenshots/ (referans müşteri logoları)
   ```

> **💡 Fark:**  
> - **`Gereksinim-Analizi/`** → AI'ya okutulacak dökümanlar (PRD oluşturmak için)  
> - **`Files/`** → Web sitesinde kullanılacak statik dosyalar (logo, sertifika PDF)

> **⚠️ ÖNEMLİ - Base64 Resim Problemi Çözümü:**
> - Gereksinim Analizi.md dosyasındaki base64 resimler AI model limitini aşıyor
> - AI'ya gönderirken **PDF dosyasındaki sayfa numaralarına referans ver**:
>   - Havsan Robotik Kodlama görselleri → PDF Sayfa 2-3
>   - Havsan AI görselleri → PDF Sayfa 4-5  
>   - Havsan Enerji görselleri → PDF Sayfa 6-7
> - MD dosyasından base64 resimler çıkarılmalı, sadece "Bkz: PDF Sayfa X" şeklinde referans verilmeli

---

### 0.4 Git Repository Başlatma

**Terminal'de çalıştır:**

```powershell
# Git başlat
git init
git branch -M main

# İlk commit
git add .
git commit -m "feat: initialize Next.js project with TypeScript and Tailwind"
```

---

### 0.5 GitHub Repository Bağlama (Opsiyonel)

**GitHub'da yeni repo oluştur:**
1. https://github.com/[organization] → **New repository**
2. Repository name: `[project-name]-frontend-app`
3. **Create repository**

**Terminal'de çalıştır:**

```powershell
# Remote repository bağla
git remote add origin https://github.com/[organization]/[project-name]-frontend-app.git

# Push
git push -u origin main
```

---

### 0.6 Geliştirme Sunucusunu Başlatma

**Terminal'de çalıştır:**

```powershell
npm run dev
```

**Tarayıcıda aç:** http://localhost:3000

✅ Next.js başlangıç sayfası görünmeli!

---

### 0.7 Proje Klasör Yapısını Kontrol Et

**VS Code Explorer'da şu klasörler görünmeli:**

```
[project-name]-frontend-app/
├── app/
│   ├── favicon.ico
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
├── public/
├── FRONTEND-DOCS/
│   ├── FRONTEND-ROADMAP.md
│   ├── Gereksinim-Analizi/
│   │   ├── Gereksinim Analizi.pdf
│   │   └── Gereksinim Analizi.md
│   └── Files/
│       ├── Logolar/
│       │   └── company-logo.png
│       └── Bilgi-Belge-Gorsel/
│           └── sertifikalar/
├── node_modules/
├── .gitignore
├── next.config.js
├── package.json
├── tailwind.config.ts
├── tsconfig.json
└── README.md
```

---

### 0.8 FRONTEND-PRD.md Oluşturma (AI ile)

> **🤖 AMAÇ:** Müşteri isterlerini AI ile detaylı PRD'ye dönüştürmek.

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: Senior Product Manager, UX Designer ve Frontend Architect rolündeki bir uzmansın.

BAĞLAM: Bu bir Next.js 14 (App Router) + TypeScript + Tailwind CSS projesidir. Frontend-first yaklaşımla geliştiriliyor. Backend henüz yok, mock verilerle çalışacak.

GÖREV: `#file:FRONTEND-DOCS/Gereksinim-Analizi/Gereksinim Analizi.md` dosyasını detaylı oku ve profesyonel bir FRONTEND-PRD.md oluştur.

⚠️ ÖNEMLİ: Gereksinim Analizi.md dosyasında base64 kodlu resimler var ancak bunları okuma! Resimler için PDF dosyasından referans al:
- Havsan Robotik Kodlama bölümü görselleri → "Bkz: Gereksinim Analizi.pdf Sayfa 2-3"
- Havsan AI bölümü görselleri → "Bkz: Gereksinim Analizi.pdf Sayfa 4-5"  
- Havsan Enerji bölümü görselleri → "Bkz: Gereksinim Analizi.pdf Sayfa 6-7"

Bu görsellerden design system renkleri ve logo bilgileri çıkar.

---

PRD İÇERİK YAPISI:

## 1. EXECUTIVE SUMMARY
- **Proje Adı:** [Müşteriden al]
- **Elevator Pitch:** 2-3 cümle, projenin özü
- **Hedef:** Ne problemi çözüyor?
- **Teknoloji Stack:** Next.js 14, TypeScript, Tailwind CSS, Framer Motion
- **Zaman Çizelgesi:** Tahmini geliştirme süresi (1-2 hafta)

## 2. USER PERSONAS
Her persona için:
- **Persona Adı:** (örn: "Kurumsal Müşteri", "Bireysel Kullanıcı")
- **Demografik:** Yaş, meslek, teknik bilgi seviyesi
- **Hedefler:** Bu siteden ne bekliyor?
- **Pain Points:** Hangi sorunları var?
- **Kullanım Senaryosu:** Siteyi nasıl kullanacak? (user journey)

En az 2, maksimum 4 persona oluştur.

## 3. SAYFA YAPISI VE WIREFRAME AÇIKLAMALARI

### 3.1 Landing Page (Ana Sayfa)
**URL:** `/`

**Bölümler (Top to Bottom):**
1. **Hero Section:**
   - İçerik: [İsterlerden çıkar - logo mu, slogan mu, büyük başlık mı?]
   - Layout: Full-screen, centered
   - CTA: [Varsa action button - örn: "Keşfet", "İletişime Geç"]
   
2. **Video Showcase / Modül Kartları:**
   - İçerik: [Kaç modül var? Her modülün başlığı, açıklaması]
   - Layout: Grid (1 col mobile, 2-3 col desktop)
   - CTA: Her kart tıklanabilir → ilgili modül sayfasına git
   
3. **Footer:**
   - İçerik: [Sosyal medya linkleri, iletişim bilgileri, copyright]

**Wireframe:** ASCII art veya detaylı açıklama

### 3.2 [MODÜL A ADI] Sayfası
**URL:** `/[module-a-slug]`
**Başlık:** [İsterlerden çıkar]

**Bölümler:**
1. **Hero Section:**
   - İçerik: [Modül başlığı, açıklayıcı metin]
   
2. **Video Player (Opsiyonel):**
   - İçerik: [Varsa tanıtım videosu]
   
3. **Kategori/Ürün/Hizmet Grid:**
   - İçerik: [Kaç kategori var? Her birinin başlığı, açıklaması, ikonu]
   - Layout: Grid (2 col mobile, 3-4 col desktop)
   - CTA: [Varsa detay sayfası linki]
   
4. **Form Section:**
   - Form Adı: [örn: "Kayıt Formu", "Talep Formu"]
   - Fields: [Ad Soyad, Email, Telefon, vb. - isterlerden çıkar]
   - Validation Rules: [Her field için - required, email formatı, telefon formatı]
   - Submit Button: "Gönder" (disabled - backend henüz yok)
   - Success State: [Form gönderildikten sonra ne gösterilecek?]
   
5. **Back Button:** Sol üst, navigate to "/"

**Wireframe:** Detaylı açıklama

### 3.3 [MODÜL B ADI] Sayfası
[Yukarıdaki formatı tekrarla - içerik isterlerden çıkacak]

### 3.4 [MODÜL C ADI] Sayfası
[Yukarıdaki formatı tekrarla - içerik isterlerden çıkacak]

## 4. DESIGN SYSTEM

### 4.1 Color Palette
**Brand Colors:** [İsterlerden veya mevcut logolardan çıkar]
- Primary: [Hex code + kullanım alanı]
- Secondary: [Hex code + kullanım alanı]
- Accent: [Hex code + kullanım alanı]
- Neutral: Gray scale (50-950)

**Semantic Colors:**
- Success: Green (#10B981)
- Error: Red (#EF4444)
- Warning: Yellow (#F59E0B)
- Info: Blue (#3B82F6)

### 4.2 Typography
**Font Family:**
- Heading: [İsterlerden veya system fonts öner]
- Body: [İsterlerden veya system fonts öner]

**Type Scale:**
- H1: [Size, weight, line-height]
- H2: [Size, weight, line-height]
- H3: [Size, weight, line-height]
- Body: [Size, weight, line-height]
- Caption: [Size, weight, line-height]

### 4.3 Spacing System
Tailwind default spacing kullan + custom değerler varsa ekle.

### 4.4 Component Library
**Gerekli Component'ler:**
1. **Button**
   - Variants: primary, secondary, ghost, danger
   - Sizes: sm, md, lg
   - States: default, hover, active, disabled, loading

2. **Card**
   - Props: image, title, description, link, badge
   - Hover: scale, shadow

3. **Input**
   - Types: text, email, tel, textarea, select
   - States: default, focus, error, disabled

4. **Modal**
   - Props: isOpen, onClose, title, children
   - Use cases: [İsterlerden çıkar - örn: sertifika gösterimi]

5. **Carousel** (Eğer gerekiyorsa)
   - Use case: [İsterlerden çıkar]

6. **Preloader**
   - İlk yüklemede gösterilecek

[Diğer component'ler ihtiyaca göre ekle]

## 5. İNTERAKTİF ÖZELLİKLER

### 5.1 Animasyonlar (Framer Motion)
- **Page Transitions:** Fade in/out (0.3s)
- **Scroll Reveal:** Cards, sections (fadeIn, slideUp)
- **Hover Effects:** Button scale (1.05), Card scale (1.02)
- **Loading States:** Skeleton screens, spinners

### 5.2 Form Validations (Client-Side)
[Her form için validation rules]

Örnek:
- Email: Regex validation
- Telefon: Format (0XXX XXX XX XX)
- Required fields: Boş bırakılamaz uyarısı

### 5.3 Responsive Breakpoints (Tailwind)
- Mobile: 640px (sm)
- Tablet: 768px (md)
- Desktop: 1024px (lg)
- Large Desktop: 1280px (xl)

**Responsive Davranışlar:**
- Grid: 1 col → 2 col → 3-4 col
- Navigation: [Varsa mobile menu]
- Font sizes: Responsive scale

## 6. İÇERİK GEREKSİNİMLERİ (MOCK DATA)

### 6.1 Landing Page Mock Data
```typescript
// Landing page videoları/modül kartları
const mockVideos = [
  { id: 1, title: "[İsterlerden çıkar]", module: "[slug]" },
  // ... diğerleri
]
```

### 6.2 [MODÜL A] Mock Data
```typescript
// Kategoriler
const mockCategories = [
  { id: 1, name: "[İsterlerden çıkar]", icon: "📚" },
  // ... diğerleri
]
```

### 6.3 [MODÜL B] Mock Data
[Çözümler, sertifikalar, referanslar - isterlerden çıkar]

### 6.4 [MODÜL C] Mock Data
[Hizmetler, projeler - isterlerden çıkar]

**Mock Data Kaynağı:**
- İsterler dokümanından gerçek içerikler kullan
- Eksik veriler için placeholder'lar öner

## 7. FORM YAPILARI

### 7.1 [MODÜL A] Form
**Form Adı:** [İsterlerden çıkar]

**Fields:**
```typescript
interface FormData {
  fullName: string          // Required, min 3 char
  email: string             // Required, email format
  phone: string             // Required, phone format
  category: string          // Required, select dropdown
  message?: string          // Optional, textarea
}
```

**Submit Davranışı:**
- Button: Disabled (backend henüz yok)
- Validation: Client-side (Zod schema)
- Success State: Toast notification "Form başarıyla gönderildi!"

[Diğer form'lar için tekrarla]

## 8. NAVIGATION FLOW

**User Journey Haritası:**
```
Landing (/) 
  ↓ Click "Modül A Kartı"
  → /[module-a]
    ↓ Fill form (mock submit)
    ↓ Click "Back Button"
  ← Landing (/)
```

[Tüm navigation flow'ları çiz]

## 9. NON-FUNCTIONAL REQUIREMENTS

### 9.1 Performance
- Lighthouse Performance Score: 90+
- First Contentful Paint: < 1.5s
- Time to Interactive: < 3.5s

### 9.2 Accessibility (WCAG 2.1 AA)
- Keyboard navigation: Tab order
- Screen reader: ARIA labels
- Color contrast: 4.5:1 minimum

### 9.3 SEO
- Metadata: title, description, openGraph
- Semantic HTML: header, main, footer
- Sitemap: Auto-generate (future)

### 9.4 Browser Support
- Chrome (son 2 versiyon)
- Firefox (son 2 versiyon)
- Safari (son 2 versiyon)
- Edge (son 2 versiyon)

## 10. FUTURE CONSIDERATIONS (Backend Entegrasyon)

**API Endpoint İhtiyaçları:**
- POST /api/[module-a]/submit → Form submission
- GET /api/content → Dynamic content fetch

**Bu PRD, frontend geliştirme için yeterlidir. Backend entegrasyonu ayrı bir faz.**

---

FORMAT: 
- Markdown formatında yaz
- Developer-friendly (kod örnekleri ekle)
- Detaylı ama okunabilir
- Başlıklar emoji ile vurgula (opsiyonel)

ÇIKTI: 
`FRONTEND-DOCS/FRONTEND-PRD.md` dosyası olarak kaydet.

ÖNEMLİ: 
- İsterler dokümanını DİKKATLİCE oku
- Eksik bilgilerde mantıklı varsayımlar yap ama belirt
- Gerçek içerikleri kullan (mock data için)
- Her karar için gerekçe ekle
```

**Çıktı Kontrolü:**
- ✅ FRONTEND-PRD.md oluşturuldu
- ✅ Tüm sayfa yapıları tanımlandı
- ✅ Component listesi netleşti

---

### 0.9 FRONTEND-TASKS.md Oluşturma (AI ile)

> **🤖 AMAÇ:** PRD'den actionable, priori̇tize edilmiş task listesi çıkarmak.

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: Senior Agile Coach, Scrum Master ve Project Manager rolündeki bir uzmansın.

BAĞLAM: Bu bir Next.js 14 + TypeScript + Tailwind CSS frontend projesidir. Task listesi, tek bir developer için haftalık sprint'lere bölünmüş, actionable görevlerden oluşmalı.

GÖREV: `#file:FRONTEND-DOCS/FRONTEND-PRD.md` dosyasını detaylı oku ve FRONTEND-TASKS.md oluştur.

⚠️ ÖNEMLİ: PRD'de görsel referansları PDF sayfa numaraları olarak verilmiştir:
- Design system renkleri ve logo bilgileri → Gereksinim Analizi.pdf'den alınmalı
- Base64 resimler yerine "Bkz: PDF Sayfa X" şeklinde referanslar var

---

TASK LİSTESİ YAPISI:

## 📋 FRONTEND DEVELOPMENT TASK LIST

**Proje:** [Proje adı - PRD'den al]  
**Başlangıç:** [Tarih - bugün]  
**Hedef Teslim:** [Tarih - 2 hafta sonra]  
**Developer:** [İsim veya "TBD"]  
**Status:** 🟡 In Progress

---

## 🎯 SPRINT OVERVIEW

### Sprint 1 (Hafta 1) - Foundation
**Hedef:** Design system + Core components + Landing page  
**Tahmini Süre:** 40 saat

### Sprint 2 (Hafta 2) - Pages & Polish
**Hedef:** Modül sayfaları + Animations + Testing  
**Tahmini Süre:** 40 saat

---

## 📊 TASK BREAKDOWN

### ✅ FAZ 0: PROJE HAZIRLIK (TAMAMLANDI)
> **Durum:** ✅ Completed  
> **Süre:** 15 dakika

- [x] **0.1** Boş klasör oluştur ve VS Code ile aç
- [x] **0.2** Next.js kurulumu (`npx create-next-app@latest .`)
- [x] **0.3** FRONTEND-DOCS klasör yapısı oluştur
- [x] **0.4** Git repository başlat (`git init`)
- [x] **0.5** GitHub'a push (optional)
- [x] **0.6** Dev server test (`npm run dev`)
- [x] **0.7** Klasör yapısını kontrol et
- [x] **0.8** FRONTEND-PRD.md oluştur (AI ile)
- [x] **0.9** FRONTEND-TASKS.md oluştur (AI ile)

---

### 🎨 FAZ 1: DESIGN SYSTEM VE TEMEL YAPI
> **Durum:** 🟡 Todo  
> **Süre:** 1-2 saat  
> **Priority:** 🔴 Critical

#### 1.1 Klasör Yapısı
- [ ] **Task 1.1.1** `components/`, `lib/`, `types/`, `public/assets/` klasörlerini oluştur
  - **Command:** `mkdir components\layout, components\sections, components\shared, lib, types, public\assets\icons, public\assets\logos, public\assets\docs`
  - **Verification:** VS Code Explorer'da klasörlerin göründüğünü kontrol et

#### 1.2 Tailwind Config
- [ ] **Task 1.2.1** `tailwind.config.ts` dosyasını aç
- [ ] **Task 1.2.2** Brand colors'ları ekle
  - **Colors:** [PRD'deki Color Palette'ten al]
  - **Example:** `primary: { DEFAULT: '#0066CC', dark: '#004C99' }`
- [ ] **Task 1.2.3** Custom fonts ekle
  - **Fonts:** [PRD'deki Typography'den al]
- [ ] **Task 1.2.4** Custom spacing ekle (18, 22, 26)
- [ ] **Task 1.2.5** Animation keyframes ekle (fadeIn, slideUp, scaleUp)
- [ ] **Task 1.2.6** Test: `npm run dev` → Hata yok ✅

#### 1.3 Global Styles
- [ ] **Task 1.3.1** `app/globals.css` dosyasını aç
- [ ] **Task 1.3.2** Tailwind directives ekle (`@tailwind base;` vb.)
- [ ] **Task 1.3.3** Custom scrollbar styles ekle
- [ ] **Task 1.3.4** Smooth scroll behavior ekle (`scroll-behavior: smooth;`)
- [ ] **Task 1.3.5** Selection color ekle (brand color)
- [ ] **Task 1.3.6** Focus-visible styles ekle (accessibility)

#### 1.4 TypeScript Types
- [ ] **Task 1.4.1** `types/index.ts` dosyası oluştur
- [ ] **Task 1.4.2** Types tanımla (PRD'den çıkar):
  - `Card` interface
  - `Video` interface
  - `FormData` generic interface
  - [Modül-specific types - PRD'den al]
- [ ] **Task 1.4.3** Export types

#### 1.5 Utility Functions
- [ ] **Task 1.5.1** `lib/utils.ts` dosyası oluştur
- [ ] **Task 1.5.2** `cn()` function ekle (clsx + tailwind-merge)
  - **Dependency:** `npm install clsx tailwind-merge`
- [ ] **Task 1.5.3** `formatDate()` function ekle
- [ ] **Task 1.5.4** `slugify()` function ekle

#### 1.6 Constants
- [ ] **Task 1.6.1** `lib/constants.ts` dosyası oluştur
- [ ] **Task 1.6.2** Constants tanımla:
  - `SITE_CONFIG` (name, description, email, phone)
  - `SOCIAL_LINKS` (linkedin, twitter, instagram)
  - `MODULE_ROUTES` (moduleA, moduleB, moduleC paths)
  - `ANIMATION_DURATION` (default: 0.3s)

**✅ Faz 1 Acceptance Criteria:**
- [ ] Tailwind config'de brand colors görünüyor
- [ ] Global styles uygulandı (scrollbar, selection color)
- [ ] Types dosyası hatasız compile oluyor
- [ ] Utils ve constants import edilebiliyor

---

### 🧩 FAZ 2: GLOBAL COMPONENTLER
> **Durum:** 🟡 Todo  
> **Süre:** 2-3 saat  
> **Priority:** 🔴 Critical

#### 2.1 Button Component
- [ ] **Task 2.1.1** `components/shared/Button.tsx` dosyası oluştur
- [ ] **Task 2.1.2** Props interface tanımla:
  - `variant`: 'primary' | 'secondary' | 'ghost' | 'danger'
  - `size`: 'sm' | 'md' | 'lg'
  - `isLoading`: boolean
  - `icon`: React.ReactNode (optional)
- [ ] **Task 2.1.3** Tailwind variants ekle (cva pattern)
- [ ] **Task 2.1.4** Accessibility: ARIA labels, keyboard support
- [ ] **Task 2.1.5** Test: Button'ı `app/page.tsx`'de render et

#### 2.2 Card Component
- [ ] **Task 2.2.1** `components/shared/Card.tsx` dosyası oluştur
- [ ] **Task 2.2.2** Props: image, title, description, link, badge, onClick
- [ ] **Task 2.2.3** Hover animation: scale + shadow (Framer Motion)
- [ ] **Task 2.2.4** Responsive: Full-width mobile, auto desktop
- [ ] **Task 2.2.5** Test: Card'ı render et

#### 2.3 Input Component
- [ ] **Task 2.3.1** `components/shared/Input.tsx` dosyası oluştur
- [ ] **Task 2.3.2** Props: label, type, placeholder, error, required
- [ ] **Task 2.3.3** States: focus, error, disabled styles
- [ ] **Task 2.3.4** Icon support: Leading icon (optional)
- [ ] **Task 2.3.5** Accessibility: ARIA labels, error announcements
- [ ] **Task 2.3.6** Test: Input'u form içinde render et

#### 2.4 Modal Component
- [ ] **Task 2.4.1** `components/shared/Modal.tsx` dosyası oluştur
- [ ] **Task 2.4.2** Props: isOpen, onClose, title, children
- [ ] **Task 2.4.3** Backdrop: Click to close
- [ ] **Task 2.4.4** Animation: Fade + scale (Framer Motion)
- [ ] **Task 2.4.5** Portal: Render outside DOM (`createPortal`)
- [ ] **Task 2.4.6** Accessibility: Focus trap, ESC to close
- [ ] **Task 2.4.7** Test: Modal açma/kapama

#### 2.5 Preloader Component
- [ ] **Task 2.5.1** `components/Preloader.tsx` dosyası oluştur
- [ ] **Task 2.5.2** localStorage logic:
  - İlk ziyaret: 3 saniye göster → "hasVisited" = true
  - Sonraki: Gösterme
- [ ] **Task 2.5.3** Animation: Logo fade-in → fade-out
- [ ] **Task 2.5.4** Company logo ekle (FRONTEND-DOCS/Files/Logolar/)
- [ ] **Task 2.5.5** Test: Preloader localStorage'ı test et

#### 2.6 Layout Components
- [ ] **Task 2.6.1** `components/layout/PageTransition.tsx` oluştur
  - Wrapper: Children'ı animate eder
  - Animation: Fade + slide up (0.3s)
- [ ] **Task 2.6.2** `components/layout/BackButton.tsx` oluştur
  - useRouter: `router.push('/')`
  - Icon: Arrow left
  - Position: Fixed top-left
- [ ] **Task 2.6.3** `components/layout/SocialLinks.tsx` oluştur
  - Props: links (SITE_CONFIG.SOCIAL_LINKS'ten al)
  - Icons: SVG veya React Icons
  - Layout: Horizontal/Vertical prop

**✅ Faz 2 Acceptance Criteria:**
- [ ] Button, Card, Input, Modal component'leri çalışıyor
- [ ] Tüm component'ler TypeScript strict mode'da hatasız
- [ ] Preloader ilk ziyarette görünüyor, ikincide yok
- [ ] Accessibility: Keyboard ile navigate edilebiliyor

---

### 🏠 FAZ 3: LANDING PAGE
> **Durum:** 🟡 Todo  
> **Süre:** 2-3 saat  
> **Priority:** 🔴 Critical

#### 3.1 Framer Motion Setup
- [ ] **Task 3.1.1** Framer Motion kur: `npm install framer-motion`
- [ ] **Task 3.1.2** `lib/animations.ts` dosyası oluştur
- [ ] **Task 3.1.3** Variants tanımla:
  - `fadeIn`: opacity 0 → 1
  - `slideUp`: y: 50 → 0, opacity 0 → 1
  - `scaleUp`: scale: 0.8 → 1, opacity 0 → 1
  - `staggerContainer`: staggerChildren: 0.2

#### 3.2 Root Layout
- [ ] **Task 3.2.1** `app/layout.tsx` dosyasını aç
- [ ] **Task 3.2.2** Metadata ekle:
  - `title`: [PRD'den al]
  - `description`: [PRD'den al]
  - `openGraph`: image, title, description
- [ ] **Task 3.2.3** Preloader component'i import et ve ekle
- [ ] **Task 3.2.4** Font optimization (next/font)

#### 3.3 Landing Page - Hero Section
- [ ] **Task 3.3.1** `app/page.tsx` dosyasını aç
- [ ] **Task 3.3.2** Hero section ekle:
  - Layout: Full-screen (`h-screen`), centered
  - Content: Company logo (büyük), slogan
  - Animation: Logo fade-in (1s), slogan slide-up (1.5s delay)
- [ ] **Task 3.3.3** Scroll indicator ekle:
  - Icon: Arrow down
  - Animation: Bounce (infinite)

#### 3.4 Landing Page - Video Showcase
- [ ] **Task 3.4.1** Mock data: `lib/data/videos.ts` oluştur
  - [PRD'deki modül sayısını al]
  - Her video: id, title, thumbnail, module slug
- [ ] **Task 3.4.2** Video Showcase section ekle:
  - Grid: 1 col mobile, 3 col desktop
  - Card component kullan
  - CTA: "İncele" button → navigate to module page
- [ ] **Task 3.4.3** Animation: Scroll reveal (stagger)
- [ ] **Task 3.4.4** Navigation: useRouter ile modül sayfasına git

#### 3.5 Landing Page - Footer
- [ ] **Task 3.5.1** Footer section ekle:
  - SocialLinks component kullan
  - Copyright text: "© 2025 [COMPANY_NAME]"
  - Background: Dark (bg-gray-900)
- [ ] **Task 3.5.2** Responsive: Stack mobile, horizontal desktop

**✅ Faz 3 Acceptance Criteria:**
- [ ] Landing page render oluyor (Hero + Showcase + Footer)
- [ ] Preloader çalışıyor
- [ ] Video kartları tıklanıyor (navigation test et)
- [ ] Animasyonlar smooth (60fps)
- [ ] Responsive: Mobile ve desktop test et

---

### 📄 FAZ 4: MODÜL SAYFALARI
> **Durum:** 🟡 Todo  
> **Süre:** 4-6 saat  
> **Priority:** 🟠 High

#### 4.1 Genel Hazırlık
- [ ] **Task 4.1.1** PRD'deki modül isimlerini belirle
  - Modül A: [İsim] → Slug: [slug]
  - Modül B: [İsim] → Slug: [slug]
  - Modül C: [İsim] → Slug: [slug]
- [ ] **Task 4.1.2** `app/[module-a]/page.tsx` klasörlerini oluştur
  - PowerShell: `mkdir app\module-a, app\module-b, app\module-c`

#### 4.2 Module A Sayfası
- [ ] **Task 4.2.1** Mock data: `lib/data/categories.ts` oluştur
  - [PRD'den kategori sayısını al]
  - Her kategori: id, name, description, icon
- [ ] **Task 4.2.2** `app/module-a/page.tsx` oluştur
- [ ] **Task 4.2.3** Hero section ekle (başlık + açıklama)
- [ ] **Task 4.2.4** Video player section ekle (optional - PRD'ye göre)
- [ ] **Task 4.2.5** Category grid ekle:
  - Card component kullan
  - Grid: 2 col mobile, 3 col desktop
  - Animation: Scroll reveal
- [ ] **Task 4.2.6** Form section ekle:
  - Input component kullan
  - Fields: [PRD'den al - örn: Ad Soyad, Email, Telefon, Kategori, Mesaj]
  - Submit button: Disabled (backend henüz yok)
  - Client-side validation: Zod schema
- [ ] **Task 4.2.7** Back button ekle (sol üst)
- [ ] **Task 4.2.8** Metadata export ekle (SEO)

#### 4.3 Module B Sayfası
- [ ] **Task 4.3.1** Mock data dosyaları oluştur:
  - `lib/data/solutions.ts`
  - `lib/data/certificates.ts`
  - `lib/data/references.ts`
  - [Her biri PRD'den al]
- [ ] **Task 4.3.2** `app/module-b/page.tsx` oluştur
- [ ] **Task 4.3.3** Hero section ekle
- [ ] **Task 4.3.4** Solutions grid ekle
- [ ] **Task 4.3.5** Certificates showcase ekle:
  - Modal: Tıklanınca büyük görsel
  - Thumbnail: PDF'den image
- [ ] **Task 4.3.6** References carousel ekle:
  - Carousel component (Swiper.js veya custom)
  - Logo'lar: Horizontal scroll
- [ ] **Task 4.3.7** Form section ekle (PRD'deki form fields)
- [ ] **Task 4.3.8** Back button + metadata

#### 4.4 Module C Sayfası
- [ ] **Task 4.4.1** Mock data dosyaları oluştur:
  - `lib/data/services.ts`
  - `lib/data/projects.ts`
- [ ] **Task 4.4.2** `app/module-c/page.tsx` oluştur
- [ ] **Task 4.4.3** Hero section ekle
- [ ] **Task 4.4.4** Services grid ekle
- [ ] **Task 4.4.5** Projects showcase ekle:
  - Grid: 2x2 mobile, 4x2 desktop
  - Card: Image, title, date
- [ ] **Task 4.4.6** Form section ekle (PRD'deki form fields)
- [ ] **Task 4.4.7** Back button + metadata

#### 4.5 Carousel Component (Eğer Gerekiyorsa)
- [ ] **Task 4.5.1** `components/sections/Carousel.tsx` oluştur
  - Props: items, autoPlay, interval
  - Navigation: Previous/Next buttons
  - Touch: Swipe support
  - Animation: Smooth slide

**✅ Faz 4 Acceptance Criteria:**
- [ ] 3 modül sayfası tamamlandı
- [ ] Tüm mock data'lar import edildi
- [ ] Form'lar UI olarak hazır (submit disabled)
- [ ] Back button çalışıyor (tüm sayfalarda)
- [ ] Navigation flow test et: Landing → Module → Back

---

### ✨ FAZ 5: ANIMASYONLAR VE POLISH
> **Durum:** 🟡 Todo  
> **Süre:** 2-3 saat  
> **Priority:** 🟠 High

#### 5.1 Page Transitions
- [ ] **Task 5.1.1** `lib/transitions.ts` dosyası oluştur
- [ ] **Task 5.1.2** Page transition config ekle
- [ ] **Task 5.1.3** Tüm `page.tsx` dosyalarını PageTransition ile wrap et

#### 5.2 Scroll Reveal Hook
- [ ] **Task 5.2.1** `lib/hooks/useIntersection.ts` custom hook oluştur
- [ ] **Task 5.2.2** Intersection Observer logic ekle
- [ ] **Task 5.2.3** Tüm section'lara scroll reveal ekle

#### 5.3 Micro-Interactions
- [ ] **Task 5.3.1** Button hover/click animations güncelle:
  - `whileHover={{ scale: 1.05 }}`
  - `whileTap={{ scale: 0.95 }}`
- [ ] **Task 5.3.2** Card hover animations güncelle
- [ ] **Task 5.3.3** Link underline animations ekle

#### 5.4 Loading States
- [ ] **Task 5.4.1** `components/shared/Loader.tsx` oluştur
  - Spinner variant
  - Skeleton variant
  - Progress bar variant
- [ ] **Task 5.4.2** Form submit'e loading state ekle (future use)

**✅ Faz 5 Acceptance Criteria:**
- [ ] Sayfa geçişleri smooth (fade-in/out)
- [ ] Scroll animations çalışıyor (kartlar appear)
- [ ] Hover effects responsive (lag yok)
- [ ] 60fps animation (Chrome DevTools Performance)

---

### 📱 FAZ 6: RESPONSIVE VE ACCESSIBILITY
> **Durum:** 🟡 Todo  
> **Süre:** 2-3 saat  
> **Priority:** 🟠 High

#### 6.1 Responsive Design Audit
- [ ] **Task 6.1.1** Chrome DevTools: Mobile view testi
  - iPhone 13 (390px)
  - Samsung Galaxy S21 (360px)
  - iPad Pro (1024px)
- [ ] **Task 6.1.2** Grid layouts kontrol et:
  - Mobile: 1 col
  - Tablet: 2 col
  - Desktop: 3-4 col
- [ ] **Task 6.1.3** Font sizes kontrol et (responsive scale)
- [ ] **Task 6.1.4** Spacing kontrol et (mobile padding küçük)
- [ ] **Task 6.1.5** Images: Lazy loading + responsive sizes
- [ ] **Task 6.1.6** Form: Full-width mobile, 50% desktop

#### 6.2 Accessibility Audit
- [ ] **Task 6.2.1** Alt texts: Tüm image'lerde alt attribute
- [ ] **Task 6.2.2** ARIA labels: Icon-only button'larda ekle
- [ ] **Task 6.2.3** Keyboard navigation: Tab order kontrol et
- [ ] **Task 6.2.4** Focus visible: Outline styles ekle
- [ ] **Task 6.2.5** Color contrast: 4.5:1 kontrol et (WebAIM tool)
- [ ] **Task 6.2.6** Form labels: Her input'ta <label> var
- [ ] **Task 6.2.7** Semantic HTML: header, main, footer, nav
- [ ] **Task 6.2.8** Screen reader test: NVDA veya VoiceOver

#### 6.3 Lighthouse Audit
- [ ] **Task 6.3.1** Lighthouse test çalıştır (Chrome DevTools)
- [ ] **Task 6.3.2** Performance: 90+ hedef
  - Image optimization: next/image kullan
  - Font optimization: next/font kullan
- [ ] **Task 6.3.3** Accessibility: 95+ hedef
- [ ] **Task 6.3.4** Best Practices: 90+ hedef
- [ ] **Task 6.3.5** SEO: 95+ hedef
  - Metadata: Tüm sayfalarda var mı kontrol et

**✅ Faz 6 Acceptance Criteria:**
- [ ] Responsive: Mobile, tablet, desktop test edildi
- [ ] Accessibility: Lighthouse 95+ score
- [ ] Keyboard: Tab ile tüm sayfa navigate edilebiliyor
- [ ] Screen reader: NVDA ile test edildi

---

### 🧪 FAZ 7: MOCK DATA VE TEST
> **Durum:** 🟡 Todo  
> **Süre:** 1-2 saat  
> **Priority:** 🟢 Medium

#### 7.1 Mock Data Organizasyonu
- [ ] **Task 7.1.1** `lib/data/` klasöründeki tüm mock dosyaları kontrol et:
  - videos.ts
  - categories.ts
  - solutions.ts
  - certificates.ts
  - references.ts
  - services.ts
  - projects.ts
- [ ] **Task 7.1.2** Gerçekçi veriler ekle (placeholder'lar yerine)
- [ ] **Task 7.1.3** TypeScript types kontrol et (hatasız compile)

#### 7.2 End-to-End Testing (Manual)
- [ ] **Task 7.2.1** Landing page test:
  - Preloader ilk/ikinci ziyaret
  - Hero animation
  - Video kartları navigation
- [ ] **Task 7.2.2** Module A test:
  - Hero, kategori grid, form
  - Back button
- [ ] **Task 7.2.3** Module B test:
  - Çözümler, sertifikalar, carousel
  - Modal açma/kapama
- [ ] **Task 7.2.4** Module C test:
  - Hizmetler, projeler, form

#### 7.3 Performance Optimization
- [ ] **Task 7.3.1** Image optimization: next/image kullan
- [ ] **Task 7.3.2** Lazy loading: Dynamic imports
- [ ] **Task 7.3.3** Bundle size: `npm run build` → analiz et
- [ ] **Task 7.3.4** Lighthouse final test: Tüm skorlar 90+

**✅ Faz 7 Acceptance Criteria:**
- [ ] Mock data realistic (backend için örnek)
- [ ] Tüm sayfalar manuel test edildi (bug yok)
- [ ] Lighthouse: Performance 90+, Accessibility 95+
- [ ] Git commit: "feat: complete frontend development"

---

## 🎉 FRONTEND GELİŞTİRME TAMAMLANDI!

### 📦 FINAL CHECKLIST
- [ ] Landing page çalışıyor (Hero + Showcase + Footer)
- [ ] 3 modül sayfası çalışıyor (mock data ile)
- [ ] Component library hazır (10+ component)
- [ ] Responsive (mobile, tablet, desktop)
- [ ] Accessible (WCAG 2.1 AA)
- [ ] Animated (Framer Motion)
- [ ] Performance (Lighthouse 90+)
- [ ] Git: Tüm değişiklikler commit edildi
- [ ] README.md güncellendi (proje açıklaması)
- [ ] FRONTEND-PRD.md ve FRONTEND-TASKS.md tamamlandı

---

## 📊 TASK STATISTICS

**Toplam Task:** [X tasks]  
**Tamamlanan:** [X] ✅  
**Devam Eden:** [X] 🟡  
**Bekleyen:** [X] ⬜  

**Progress:** [X%]

---

## 🚀 SONRAKI ADIMLAR

1. **Müşteri Demo:**
   - [ ] Vercel'e deploy et (preview URL)
   - [ ] Demo sunumu hazırla
   - [ ] Feedback topla

2. **Backend Hazırlık:**
   - [ ] API-CONTRACT.md oluştur
   - [ ] Mock data'ları backend ekibine aktar
   - [ ] Form endpoint'lerini belirt

3. **Entegrasyon:**
   - [ ] .env.local dosyası oluştur
   - [ ] API fetch fonksiyonları yaz
   - [ ] Form submit handler'ları hazırla

---

FORMAT:
- GitHub markdown checkbox formatı (`- [ ]`)
- Task ID: Faz.Alt-faz.Sıra (örn: Task 2.3.5)
- Priority: 🔴 Critical, 🟠 High, 🟢 Medium, 🔵 Low
- Status: ✅ Done, 🟡 In Progress, ⬜ Todo

ÇIKTI:
`FRONTEND-DOCS/FRONTEND-TASKS.md` dosyası olarak kaydet.

ÖNEMLİ:
- PRD'yi DİKKATLİCE oku, her modülün özelliklerini task'lara dönüştür
- Her task actionable ve measurable olmalı
- Acceptance criteria net olmalı (test edilebilir)
- Time estimate realistic olmalı (developer için)
- Dependencies belirt (örn: Task 2.1.3, Task 2.1.2'ye bağlı)
```

**Çıktı Kontrolü:**
- ✅ FRONTEND-TASKS.md oluşturuldu
- ✅ Tüm task'lar ID ile numaralandırılmış
- ✅ Priority ve status etiketleri eklenmiş
- ✅ Acceptance criteria her faz için belirtilmiş
- ✅ Progress tracking bölümü var
- ✅ Next steps bölümü var

---

**✅ FAZ 0 TAMAMLANDI!**

Çıktılar:
- ✅ Next.js projesi kuruldu
- ✅ Git repository aktif
- ✅ Dev server çalışıyor
- ✅ Müşteri dökümanları eklendi
- ✅ FRONTEND-PRD.md oluşturuldu (AI ile)
- ✅ FRONTEND-TASKS.md oluşturuldu (AI ile)

---

## 🎨 FAZ 1: DESIGN SYSTEM VE TEMEL YAPI

> **SÜRE:** 1-2 saat  
> **ÇIKTI:** Tailwind config + Klasör yapısı + Global styles

### 1.1 Klasör Yapısı Oluşturma

**Hedef klasör yapısı:**
```
project-name/
├── app/
│   ├── layout.tsx          # Root layout
│   ├── page.tsx            # Landing page
│   ├── globals.css         # Global styles
│   ├── [module-a]/
│   │   └── page.tsx
│   ├── [module-b]/
│   │   └── page.tsx
│   └── [module-c]/
│       └── page.tsx
│
├── components/
│   ├── Preloader.tsx
│   ├── layout/
│   │   ├── PageTransition.tsx
│   │   ├── BackButton.tsx
│   │   └── SocialLinks.tsx
│   ├── sections/
│   │   ├── Hero.tsx
│   │   ├── VideoShowcase.tsx
│   │   └── Carousel.tsx
│   └── shared/
│       ├── Button.tsx
│       ├── Card.tsx
│       ├── Modal.tsx
│       └── Input.tsx
│
├── lib/
│   ├── animations.ts       # Framer Motion variants
│   ├── transitions.ts      # Page transitions
│   ├── utils.ts            # Helper functions
│   └── constants.ts        # App constants
│
├── types/
│   └── index.ts            # TypeScript types
│
├── public/
│   └── assets/
│       ├── icons/
│       ├── logos/
│       └── docs/
│
└── FRONTEND-DOCS/
```

**PowerShell komutu (klasörleri oluştur):**
```powershell
mkdir components\layout, components\sections, components\shared, lib, types, public\assets\icons, public\assets\logos, public\assets\docs
```

### 1.2 Tailwind Config Güncelleme

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: Senior Frontend Developer, Design System Architect ve Tailwind CSS uzmanısın.

BAĞLAM: Next.js 14 + TypeScript projesi için Tailwind config dosyasını brand guideline'a göre özelleştiriyoruz.

GÖREV: `#file:tailwind.config.ts` dosyasını güncelle.

REFERANS: `#file:FRONTEND-DOCS/FRONTEND-PRD.md` → Design System bölümünü oku.

---

KONFİGÜRASYON GEREKSİNİMLERİ:

### 1. COLOR PALETTE
**Brand Colors:** [PRD'den al]

Örnek yapı:
```typescript
colors: {
  primary: {
    DEFAULT: '#0066CC',
    dark: '#004C99',
    darker: '#003366',
    light: '#3385D6',
    lighter: '#66A3E0',
  },
  secondary: {
    DEFAULT: '#E31837',
    dark: '#B91429',
  },
  accent: {
    green: '#00A86B',
    yellow: '#FFB900',
    orange: '#FF6B00',
  },
  // Tailwind gray scale'i koru (gray-50 to gray-950)
}
```

### 2. TYPOGRAPHY
**Font Family:**
```typescript
fontFamily: {
  sans: [
    '-apple-system',
    'BlinkMacSystemFont',
    '"Segoe UI"',
    'Roboto',
    '"Helvetica Neue"',
    'Arial',
    'sans-serif',
  ],
  // Heading için ayrı font varsa PRD'den al
}
```

### 3. CUSTOM SPACING
```typescript
spacing: {
  18: '4.5rem',  // 72px
  22: '5.5rem',  // 88px
  26: '6.5rem',  // 104px
  // Tailwind default spacing'i extend et
}
```

### 4. ANIMATIONS
```typescript
keyframes: {
  fadeIn: {
    from: { opacity: '0' },
    to: { opacity: '1' },
  },
  slideUp: {
    from: { transform: 'translateY(50px)', opacity: '0' },
    to: { transform: 'translateY(0)', opacity: '1' },
  },
  scaleUp: {
    from: { transform: 'scale(0.8)', opacity: '0' },
    to: { transform: 'scale(1)', opacity: '1' },
  },
  bounce: {
    '0%, 100%': { transform: 'translateY(0)' },
    '50%': { transform: 'translateY(-10px)' },
  },
},
animation: {
  fadeIn: 'fadeIn 0.3s ease-in-out',
  slideUp: 'slideUp 0.5s ease-out',
  scaleUp: 'scaleUp 0.4s ease-out',
  bounce: 'bounce 2s infinite',
}
```

### 5. BREAKPOINTS (Tailwind Default'u Koru)
- sm: 640px
- md: 768px
- lg: 1024px
- xl: 1280px
- 2xl: 1536px

### 6. PLUGIN'LER
```typescript
plugins: [
  require('@tailwindcss/forms'),      // Form styling (optional)
  require('@tailwindcss/typography'), // Prose styling (optional)
]
```

---

ÇIKTI:
- Güncellenmiş `tailwind.config.ts` dosyası
- TypeScript type-safe config
- Yorumlar ekle (hangi renk nerede kullanılacak)

VERİFİCATION:
- `npm run dev` → Hata yok ✅
- `className="bg-primary text-white"` → Renk görünüyor ✅
```

### 1.3 Global Styles (globals.css)

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: CSS uzmanı ve Accessibility champion'ısın.

GÖREV: `#file:app/globals.css` dosyasını güncelle.

REFERANS: `#file:tailwind.config.ts` → Color palette'i al.

---

GLOBAL STYLES İÇERİĞİ:

### 1. TAILWIND DIRECTIVES
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 2. BASE STYLES (HTML Reset)
```css
@layer base {
  * {
    @apply border-border;
  }
  
  html {
    @apply scroll-smooth;
  }
  
  body {
    @apply bg-white text-gray-900 antialiased;
    /* Brand font'u kullan */
    font-feature-settings: "rlig" 1, "calt" 1;
  }
}
```

### 3. SELECTION COLOR
```css
::selection {
  background-color: [Primary color - Tailwind config'den al];
  color: white;
}
```

### 4. CUSTOM SCROLLBAR
```css
/* Webkit browsers (Chrome, Safari, Edge) */
::-webkit-scrollbar {
  width: 12px;
}

::-webkit-scrollbar-track {
  @apply bg-gray-100;
}

::-webkit-scrollbar-thumb {
  @apply bg-gray-400 rounded-full;
}

::-webkit-scrollbar-thumb:hover {
  @apply bg-primary;
}

/* Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: theme('colors.gray.400') theme('colors.gray.100');
}
```

### 5. FOCUS VISIBLE (Accessibility)
```css
@layer base {
  *:focus-visible {
    @apply outline-2 outline-offset-2 outline-primary;
  }
  
  /* Button'larda focus ring kaldır (custom stil eklenecek) */
  button:focus {
    @apply outline-none;
  }
}
```

### 6. SMOOTH TRANSITIONS
```css
@layer base {
  * {
    @apply transition-colors duration-200;
  }
}
```

### 7. CUSTOM UTILITIES (Optional)
```css
@layer utilities {
  .text-balance {
    text-wrap: balance;
  }
  
  .animation-delay-200 {
    animation-delay: 200ms;
  }
  
  .animation-delay-400 {
    animation-delay: 400ms;
  }
}
```

---

ÇIKTI:
- Güncellenmiş `app/globals.css` dosyası
- Tailwind @layer kullan (specificity için)
- Responsive scrollbar styles

VERİFİCATION:
- `npm run dev` → CSS compile oluyor ✅
- Selection color test et (text seç) ✅
- Scrollbar custom style görünüyor ✅
- Focus visible test et (Tab ile navigate) ✅
```

### 1.4 TypeScript Types Tanımlama

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: TypeScript expert ve type-safety advocate'ısın.

GÖREV: `types/index.ts` dosyasını oluştur.

REFERANS: `#file:FRONTEND-DOCS/FRONTEND-PRD.md` → Tüm veri yapılarını oku.

---

TYPE DEFİNİTİONS:

### 1. SHARED TYPES
```typescript
// Base types
export interface BaseEntity {
  id: string | number
  createdAt?: string
  updatedAt?: string
}

export type Status = 'active' | 'inactive' | 'pending'
```

### 2. COMPONENT TYPES
```typescript
// Card component
export interface Card {
  id: string | number
  title: string
  description: string
  image?: string
  link?: string
  badge?: string
  onClick?: () => void
}

// Button variants
export type ButtonVariant = 'primary' | 'secondary' | 'ghost' | 'danger'
export type ButtonSize = 'sm' | 'md' | 'lg'

export interface ButtonProps extends React.ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: ButtonVariant
  size?: ButtonSize
  isLoading?: boolean
  leftIcon?: React.ReactNode
  rightIcon?: React.ReactNode
}
```

### 3. PAGE DATA TYPES
```typescript
// Landing page videos
export interface Video extends BaseEntity {
  title: string
  description: string
  thumbnail: string
  url: string
  module: string  // Route slug (module-a, module-b, module-c)
  duration?: string
}

// Module A - Categories
export interface Category extends BaseEntity {
  name: string
  description: string
  icon: string  // Emoji or icon name
  slug: string
}

// Module B - Solutions
export interface Solution extends BaseEntity {
  title: string
  description: string
  image: string
  features?: string[]
}

// Module B - Certificates
export interface Certificate extends BaseEntity {
  name: string
  issuer: string
  thumbnail: string
  pdfUrl: string
  issuedDate: string
}

// Module B - References (Customer logos)
export interface Reference extends BaseEntity {
  companyName: string
  logo: string
  website?: string
  testimonial?: string
}

// Module C - Services
export interface Service extends BaseEntity {
  title: string
  description: string
  icon: string
  features?: string[]
}

// Module C - Projects
export interface Project extends BaseEntity {
  title: string
  description: string
  image: string
  completionDate: string
  client?: string
  technologies?: string[]
}
```

### 4. FORM TYPES
```typescript
// Generic form field
export interface FormField {
  name: string
  label: string
  type: 'text' | 'email' | 'tel' | 'textarea' | 'select'
  placeholder?: string
  required?: boolean
  validation?: {
    pattern?: RegExp
    minLength?: number
    maxLength?: number
    message?: string
  }
}

// Module A - Registration form
export interface RegistrationFormData {
  fullName: string
  email: string
  phone: string
  categoryId: string | number
  message?: string
}

// Module B - Inquiry form
export interface InquiryFormData {
  companyName: string
  contactPerson: string
  email: string
  phone: string
  inquiryType: string
  message: string
}

// Module C - Quote request form
export interface QuoteFormData {
  companyName: string
  contactPerson: string
  email: string
  phone: string
  projectDescription: string
  budget?: string
  timeline?: string
}

// Form submission response
export interface FormSubmissionResponse {
  success: boolean
  message: string
  submissionId?: string
}
```

### 5. NAVIGATION TYPES
```typescript
export interface NavLink {
  label: string
  href: string
  icon?: React.ReactNode
}

export interface SocialLink {
  platform: 'linkedin' | 'twitter' | 'instagram' | 'facebook' | 'email' | 'phone'
  url: string
  icon: React.ReactNode
}
```

### 6. SITE CONFIG TYPE
```typescript
export interface SiteConfig {
  name: string
  description: string
  url: string
  email: string
  phone: string
  address?: string
  socialLinks: SocialLink[]
}
```

---

ÇIKTI:
- `types/index.ts` dosyası
- Tüm type'lar export edilmiş
- JSDoc yorumları ekle (type açıklamaları)
- Extend edilebilir yapı (BaseEntity)

VERİFİCATION:
- TypeScript compile hatasız ✅
- `import type { Video, Card } from '@/types'` → Çalışıyor ✅
```

### 1.5 Utility Functions (lib/utils.ts)

**GitHub Copilot Prompt:**
```markdown
SEN: React uzmanısın.

GÖREV: `lib/utils.ts` dosyasını oluştur.

FUNCTIONS:
- cn(...classes): Tailwind class merger (clsx + tailwind-merge)
- formatDate(date): Tarih formatı
- slugify(text): URL slug oluştur

ÇIKTI: `lib/utils.ts` dosyası.
```

### 1.6 Constants (lib/constants.ts)

**GitHub Copilot Prompt:**
```markdown
SEN: Frontend Developer'sın.

GÖREV: `lib/constants.ts` dosyasını oluştur.

CONSTANTS:
- SITE_CONFIG: { name, description, url, email, phone }
- SOCIAL_LINKS: { linkedin, twitter, instagram }
- MODULE_ROUTES: { moduleA: "/module-a", ... }
- ANIMATION_DURATION: Default animation süreleri

ÇIKTI: `lib/constants.ts` dosyası.
```

---

**✅ FAZ 1 TAMAMLANDI!**

Çıktılar:
- ✅ Klasör yapısı oluşturuldu
- ✅ Tailwind config hazır (brand colors, fonts)
- ✅ Global styles set edildi
- ✅ TypeScript types tanımlandı
- ✅ Utility functions hazır

---

## 🧩 FAZ 2: GLOBAL COMPONENTLER

> **SÜRE:** 2-3 saat  
> **ÇIKTI:** Reusable component library

### 2.1 Shared UI Components

#### Button Component

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: React Component Library Architect ve Accessibility Expert'isin.

GÖREV: `components/shared/Button.tsx` komponenti oluştur.

REFERANS: 
- `#file:types/index.ts` → ButtonProps interface
- `#file:tailwind.config.ts` → Brand colors

---

KOMPONENT GEREKSİNİMLERİ:

### PROPS INTERFACE
```typescript
import { ButtonHTMLAttributes, ReactNode } from 'react'

interface ButtonProps extends ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: 'primary' | 'secondary' | 'ghost' | 'danger'
  size?: 'sm' | 'md' | 'lg'
  isLoading?: boolean
  leftIcon?: ReactNode
  rightIcon?: ReactNode
  children: ReactNode
}
```

### STYLING (cva pattern - class-variance-authority)
```bash
# Dependency kur
npm install class-variance-authority
```

```typescript
import { cva, type VariantProps } from 'class-variance-authority'

const buttonVariants = cva(
  // Base styles (all variants)
  'inline-flex items-center justify-center rounded-lg font-medium transition-all focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-primary focus-visible:ring-offset-2 disabled:opacity-50 disabled:pointer-events-none',
  {
    variants: {
      variant: {
        primary: 'bg-primary text-white hover:bg-primary-dark',
        secondary: 'bg-secondary text-white hover:bg-secondary-dark',
        ghost: 'bg-transparent border border-gray-300 hover:bg-gray-50',
        danger: 'bg-red-600 text-white hover:bg-red-700',
      },
      size: {
        sm: 'h-9 px-4 text-sm',
        md: 'h-11 px-6 text-base',
        lg: 'h-13 px-8 text-lg',
      },
    },
    defaultVariants: {
      variant: 'primary',
      size: 'md',
    },
  }
)
```

### FRAMER MOTION INTEGRATION
```typescript
import { motion } from 'framer-motion'

const MotionButton = motion.button

<MotionButton
  whileHover={{ scale: 1.05 }}
  whileTap={{ scale: 0.95 }}
  transition={{ type: 'spring', stiffness: 300 }}
/>
```

### LOADING STATE
```typescript
// Loading spinner SVG
{isLoading && (
  <svg
    className="animate-spin h-5 w-5 mr-2"
    xmlns="http://www.w3.org/2000/svg"
    fill="none"
    viewBox="0 0 24 24"
  >
    <circle
      className="opacity-25"
      cx="12"
      cy="12"
      r="10"
      stroke="currentColor"
      strokeWidth="4"
    />
    <path
      className="opacity-75"
      fill="currentColor"
      d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
    />
  </svg>
)}
```

### ACCESSIBILITY
- ARIA labels: `aria-label` prop support
- Disabled state: `disabled` prop
- Keyboard: Tab fokus, Enter/Space trigger
- Loading state: `aria-busy="true"` when loading

### KULLANIM ÖRNEĞİ
```typescript
// Primary button
<Button variant="primary" size="md" onClick={handleClick}>
  Submit
</Button>

// Loading state
<Button isLoading disabled>
  Processing...
</Button>

// With icons
<Button leftIcon={<ArrowLeftIcon />}>
  Back
</Button>
```

---

ÇIKTI:
- `components/shared/Button.tsx` dosyası
- Export: `export { Button, buttonVariants }`
- TypeScript strict mode
- Framer Motion animations

VERİFİCATION:
- Test: `app/page.tsx`'de render et
- Hover animation çalışıyor ✅
- Disabled state doğru ✅
- Keyboard accessible ✅
```

#### Card Component

**GitHub Copilot Prompt:**
```markdown
SEN: React Component uzmanısın.

GÖREV: `components/shared/Card.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: image, title, description, link, onClick
- Hover effect: Scale + shadow
- Optional: Badge, action buttons
- Responsive: Mobile/Desktop layouts

ÇIKTI: `components/shared/Card.tsx` dosyası.
```

#### Input Component

**GitHub Copilot Prompt:**
```markdown
SEN: Form component uzmanısın.

GÖREV: `components/shared/Input.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: label, placeholder, type, error, required
- States: focus, error, disabled
- Icon support: Leading icon
- Accessibility: ARIA labels, error messages

ÇIKTI: `components/shared/Input.tsx` dosyası.
```

#### Modal Component

**GitHub Copilot Prompt:**
```markdown
SEN: React Modal uzmanısın.

GÖREV: `components/shared/Modal.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: isOpen, onClose, title, children
- Backdrop: Click to close
- Animation: Fade in/out (Framer Motion)
- Accessibility: Focus trap, ESC to close, ARIA
- Portal: Render outside DOM tree

ÇIKTI: `components/shared/Modal.tsx` dosyası.
```

### 2.2 Layout Components

#### PageTransition

**GitHub Copilot Prompt:**
```markdown
SEN: Framer Motion uzmanısın.

GÖREV: `components/layout/PageTransition.tsx` komponenti oluştur.

ÖZELLİKLER:
- Wrapper component: Sayfa geçişlerini wrap eder
- Animation: Fade + slide up
- Duration: 0.3s
- Children: React.ReactNode

ÇIKTI: `components/layout/PageTransition.tsx` dosyası.
```

#### BackButton

**GitHub Copilot Prompt:**
```markdown
SEN: Next.js navigation uzmanısın.

GÖREV: `components/layout/BackButton.tsx` komponenti oluştur.

ÖZELLİKLER:
- useRouter hook ile geri git
- Icon: Arrow left
- Animation: Hover scale
- Position: Fixed top-left veya inline

ÇIKTI: `components/layout/BackButton.tsx` dosyası.
```

#### SocialLinks

**GitHub Copilot Prompt:**
```markdown
SEN: React component uzmanısın.

GÖREV: `components/layout/SocialLinks.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: links (linkedin, email, phone)
- Icons: SVG veya React Icons
- Layout: Horizontal/Vertical
- Hover: Scale animation

ÇIKTI: `components/layout/SocialLinks.tsx` dosyası.
```

### 2.3 Preloader Component

**GitHub Copilot Prompt:**
```markdown
SEN: Animation uzmanısın.

GÖREV: `components/Preloader.tsx` komponenti oluştur.

DAVRANIŞI:
- İlk ziyaret: 3 saniye logo animasyonu
- localStorage kontrolü: "hasVisited" key
- Sonraki ziyaretler: Preloader gösterme
- Animation: Fade-out (Framer Motion)
- Logo: Company logo + scale animation

ÇIKTI: `components/Preloader.tsx` dosyası.
```

---

**✅ FAZ 2 TAMAMLANDI!**

Çıktılar:
- ✅ Button, Card, Input, Modal component'leri hazır
- ✅ PageTransition, BackButton, SocialLinks hazır
- ✅ Preloader component hazır
- ✅ Tüm component'ler TypeScript + Accessible

---

## 🏠 FAZ 3: LANDING PAGE

> **SÜRE:** 2-3 saat  
> **ÇIKTI:** Ana sayfa (Hero + Video Showcase + Footer)

### 3.1 Root Layout (app/layout.tsx)

**GitHub Copilot Prompt:**
```markdown
SEN: Next.js 14 uzmanısın.

GÖREV: `app/layout.tsx` dosyasını güncelle.

İÇERİK:
- Metadata: title, description, openGraph
- Font optimization: System fonts
- Preloader wrapper: <Preloader /> ekle
- Global CSS import
- Children render

ÖRNEK METADATA:
- title: "[COMPANY_NAME] | [Slogan]"
- description: "150 karakterlik açıklama"
- openGraph: Image, title, description

ÇIKTI: Güncellenmiş `app/layout.tsx` dosyası.
```

### 3.2 Landing Page (app/page.tsx)

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: Senior React Developer, Framer Motion Specialist ve UX Designer'sın.

GÖREV: `app/page.tsx` landing page'i oluştur.

REFERANS:
- `#file:FRONTEND-DOCS/FRONTEND-PRD.md` → Landing Page wireframe
- `#file:lib/data/videos.ts` → Mock data (oluşturulacak)
- `#file:lib/animations.ts` → Animation variants

---

SAYFA YAPISI:

## 1. HERO SECTION

### Layout
```typescript
<section className="relative h-screen flex flex-col items-center justify-center bg-gradient-to-br from-primary/5 to-white">
  {/* Company Logo */}
  <motion.div
    initial={{ opacity: 0, scale: 0.8 }}
    animate={{ opacity: 1, scale: 1 }}
    transition={{ duration: 1, ease: 'easeOut' }}
    className="mb-8"
  >
    <Image
      src="/assets/logos/company-logo.png"
      alt="[COMPANY_NAME]"
      width={200}
      height={200}
      priority
    />
  </motion.div>

  {/* Slogan */}
  <motion.h1
    initial={{ opacity: 0, y: 30 }}
    animate={{ opacity: 1, y: 0 }}
    transition={{ duration: 0.8, delay: 0.5 }}
    className="text-4xl md:text-6xl font-bold text-center text-gray-900 mb-4"
  >
    [COMPANY_SLOGAN - PRD'den al]
  </motion.h1>

  <motion.p
    initial={{ opacity: 0, y: 20 }}
    animate={{ opacity: 1, y: 0 }}
    transition={{ duration: 0.8, delay: 0.8 }}
    className="text-lg md:text-xl text-gray-600 text-center max-w-2xl px-4"
  >
    [Alt başlık - PRD'den al]
  </motion.p>

  {/* Scroll Indicator */}
  <motion.div
    initial={{ opacity: 0 }}
    animate={{ opacity: 1 }}
    transition={{ delay: 1.5 }}
    className="absolute bottom-8"
  >
    <motion.div
      animate={{ y: [0, 10, 0] }}
      transition={{ repeat: Infinity, duration: 2 }}
      className="flex flex-col items-center text-gray-400 cursor-pointer"
      onClick={() => window.scrollTo({ top: window.innerHeight, behavior: 'smooth' })}
    >
      <span className="text-sm mb-2">Keşfet</span>
      <svg className="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M19 14l-7 7m0 0l-7-7m7 7V3" />
      </svg>
    </motion.div>
  </motion.div>
</section>
```

## 2. VIDEO SHOWCASE SECTION

### Mock Data
```typescript
// lib/data/videos.ts (ÖNCE BU DOSYAYI OLUŞTUR)
import { Video } from '@/types'

export const mockVideos: Video[] = [
  {
    id: 1,
    title: "[Modül A İsmi - PRD'den al]",
    description: "Kısa açıklama",
    thumbnail: "/assets/thumbnails/module-a.jpg", // Placeholder
    url: "https://youtube.com/watch?v=...",
    module: "module-a", // Route slug
  },
  // ... PRD'deki diğer modüller
]
```

### Layout
```typescript
<section className="py-20 px-4 md:px-8 bg-white">
  <motion.div
    initial="hidden"
    whileInView="visible"
    viewport={{ once: true, margin: "-100px" }}
    variants={staggerContainer}
    className="max-w-7xl mx-auto"
  >
    {/* Section Header */}
    <motion.h2
      variants={fadeIn}
      className="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12"
    >
      Çözümlerimiz
    </motion.h2>

    {/* Video Cards Grid */}
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {mockVideos.map((video) => (
        <motion.div
          key={video.id}
          variants={slideUp}
          whileHover={{ scale: 1.02 }}
          className="cursor-pointer"
          onClick={() => router.push(`/${video.module}`)}
        >
          <Card
            image={video.thumbnail}
            title={video.title}
            description={video.description}
          />
        </motion.div>
      ))}
    </div>
  </motion.div>
</section>
```

## 3. FOOTER

```typescript
<footer className="bg-gray-900 text-white py-12 px-4">
  <div className="max-w-7xl mx-auto">
    {/* Social Links */}
    <SocialLinks className="justify-center mb-6" />

    {/* Copyright */}
    <p className="text-center text-gray-400 text-sm">
      © {new Date().getFullYear()} [COMPANY_NAME]. Tüm hakları saklıdır.
    </p>
  </div>
</footer>
```

---

İMPORTS:
```typescript
'use client'

import { motion } from 'framer-motion'
import { useRouter } from 'next/navigation'
import Image from 'next/image'
import { Card } from '@/components/shared/Card'
import { SocialLinks } from '@/components/layout/SocialLinks'
import { mockVideos } from '@/lib/data/videos'
import { fadeIn, slideUp, staggerContainer } from '@/lib/animations'
```

RESPONSIVE:
- Mobile: 1 col grid, text-4xl heading
- Tablet: 2 col grid, text-5xl heading
- Desktop: 3 col grid, text-6xl heading

ÇIKTI:
- `app/page.tsx` dosyası
- Client component (`'use client'`)
- Framer Motion animations
- next/image optimization

VERİFİCATION:
- http://localhost:3000 → Hero görünüyor ✅
- Scroll indicator çalışıyor ✅
- Video kartları tıklanıyor (navigation test et) ✅
- Animasyonlar smooth (60fps) ✅
```

### 3.3 Framer Motion Animations (lib/animations.ts)

**GitHub Copilot Prompt:**
```markdown
SEN: Framer Motion uzmanısın.

GÖREV: `lib/animations.ts` dosyasını oluştur.

VARIANTS:
- fadeIn: { hidden: { opacity: 0 }, visible: { opacity: 1 } }
- slideUp: { hidden: { y: 50, opacity: 0 }, visible: { y: 0, opacity: 1 } }
- scaleUp: { hidden: { scale: 0.8, opacity: 0 }, visible: { scale: 1, opacity: 1 } }
- staggerContainer: { visible: { transition: { staggerChildren: 0.2 } } }

ÇIKTI: Export edilmiş Framer Motion variants.
```

### 3.4 Hero Section Component (Optional - Reusable)

**GitHub Copilot Prompt:**
```markdown
SEN: React component uzmanısın.

GÖREV: `components/sections/Hero.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: title, subtitle, backgroundImage (optional)
- Layout: Full-screen, centered
- Animation: Fade-in on mount

ÇIKTI: `components/sections/Hero.tsx` dosyası.
```

### 3.5 Video Showcase Component

**GitHub Copilot Prompt:**
```markdown
SEN: React component uzmanısın.

GÖREV: `components/sections/VideoShowcase.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: videos (array of { id, title, thumbnail, module })
- Layout: Grid (1 col mobile, 3 col desktop)
- Card: Image, title, description, CTA button
- Animation: Scroll reveal

ÇIKTI: `components/sections/VideoShowcase.tsx` dosyası.
```

---

**✅ FAZ 3 TAMAMLANDI!**

Çıktılar:
- ✅ Landing page tamamlandı (Hero + Video Showcase + Footer)
- ✅ Preloader entegre edildi
- ✅ Animasyonlar uygulandı (Framer Motion)
- ✅ Responsive (mobile-first)

**Test:** http://localhost:3000 → Landing page görünmeli ✅

---

## 📄 FAZ 4: MODÜL SAYFALARI

> **SÜRE:** 4-6 saat  
> **ÇIKTI:** 3 modül sayfası (mock verilerle)

### 4.1 Modül Sayfası Şablonu

**Her modül için ortak yapı:**
1. Hero section (başlık + açıklama)
2. Content section (kartlar, listeler)
3. Form section (kayıt/talep/teklif formu)
4. Back button (navigate home)

### 4.2 Module A Sayfası (app/[module-a]/page.tsx)

**GitHub Copilot Prompt (Copilot Chat'te çalıştır):**

```markdown
SEN: React ve Next.js uzmanı, Form Validation Expert'isin.

GÖREV: `app/module-a/page.tsx` sayfasını oluştur.

REFERANS: 
- `#file:FRONTEND-DOCS/FRONTEND-PRD.md` → Module A bölümünü DİKKATLE oku
- `#file:lib/data/categories.ts` → Mock data (oluşturulacak)
- `#file:types/index.ts` → Category ve RegistrationFormData types

---

## SAYFA YAPISIAŞAMA 1: MOCK DATA OLUŞTUR

```typescript
// lib/data/categories.ts
import { Category } from '@/types'

export const mockCategories: Category[] = [
  {
    id: 1,
    name: "[Kategori 1 - PRD'den al]",
    description: "Kısa açıklama",
    icon: "📚", // Emoji veya icon component
    slug: "category-1",
  },
  // ... PRD'deki diğer kategoriler (toplam 6-8 adet)
]
```

## AŞAMA 2: SAYFA LAYOUT

### Hero Section
```typescript
<section className="relative h-[50vh] flex items-center justify-center bg-gradient-to-br from-primary/10 to-white">
  <div className="text-center px-4">
    <motion.h1
      initial={{ opacity: 0, y: 30 }}
      animate={{ opacity: 1, y: 0 }}
      className="text-4xl md:text-5xl font-bold text-gray-900 mb-4"
    >
      [Module A Başlığı - PRD'den al]
    </motion.h1>
    <motion.p
      initial={{ opacity: 0, y: 20 }}
      animate={{ opacity: 1, y: 0 }}
      transition={{ delay: 0.2 }}
      className="text-lg md:text-xl text-gray-600 max-w-2xl mx-auto"
    >
      [Açıklama - PRD'den al]
    </motion.p>
  </div>
</section>
```

### Video Player Section (Eğer PRD'de varsa)
```typescript
<section className="py-16 px-4 bg-white">
  <div className="max-w-4xl mx-auto">
    <div className="aspect-video rounded-lg overflow-hidden shadow-xl">
      <iframe
        src="https://www.youtube.com/embed/[VIDEO_ID]"
        title="Module A Tanıtım"
        className="w-full h-full"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowFullScreen
      />
    </div>
  </div>
</section>
```

### Category Grid
```typescript
<section className="py-20 px-4 bg-gray-50">
  <div className="max-w-7xl mx-auto">
    <motion.h2
      initial={{ opacity: 0 }}
      whileInView={{ opacity: 1 }}
      viewport={{ once: true }}
      className="text-3xl font-bold text-center text-gray-900 mb-12"
    >
      Kategoriler
    </motion.h2>

    <motion.div
      initial="hidden"
      whileInView="visible"
      viewport={{ once: true, margin: "-100px" }}
      variants={staggerContainer}
      className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6"
    >
      {mockCategories.map((category) => (
        <motion.div key={category.id} variants={slideUp}>
          <Card
            title={category.name}
            description={category.description}
            badge={category.icon}
            onClick={() => console.log('Category clicked:', category.id)}
          />
        </motion.div>
      ))}
    </motion.div>
  </div>
</section>
```

### Form Section
```typescript
'use client'

import { useState } from 'react'
import { z } from 'zod'
import { Input } from '@/components/shared/Input'
import { Button } from '@/components/shared/Button'

// Zod schema (validation)
const registrationSchema = z.object({
  fullName: z.string().min(3, 'Ad Soyad en az 3 karakter olmalı'),
  email: z.string().email('Geçerli bir email adresi girin'),
  phone: z.string().regex(/^0\d{10}$/, 'Telefon formatı: 05XXXXXXXXX'),
  categoryId: z.string().min(1, 'Kategori seçiniz'),
  message: z.string().optional(),
})

type RegistrationFormData = z.infer<typeof registrationSchema>

export default function ModuleAPage() {
  const [formData, setFormData] = useState<RegistrationFormData>({
    fullName: '',
    email: '',
    phone: '',
    categoryId: '',
    message: '',
  })
  const [errors, setErrors] = useState<Partial<Record<keyof RegistrationFormData, string>>>({})
  const [isSubmitting, setIsSubmitting] = useState(false)

  const handleSubmit = async (e: React.FormEvent) => {
    e.preventDefault()
    setIsSubmitting(true)
    setErrors({})

    // Validate
    try {
      registrationSchema.parse(formData)
      
      // TODO: Backend entegrasyonu
      console.log('Form data:', formData)
      alert('Form başarıyla gönderildi! (Mock submission)')
      
      // Reset form
      setFormData({ fullName: '', email: '', phone: '', categoryId: '', message: '' })
    } catch (error) {
      if (error instanceof z.ZodError) {
        const fieldErrors: Partial<Record<keyof RegistrationFormData, string>> = {}
        error.errors.forEach((err) => {
          if (err.path[0]) {
            fieldErrors[err.path[0] as keyof RegistrationFormData] = err.message
          }
        })
        setErrors(fieldErrors)
      }
    } finally {
      setIsSubmitting(false)
    }
  }

  return (
    <section className="py-20 px-4 bg-white">
      <div className="max-w-2xl mx-auto">
        <h2 className="text-3xl font-bold text-center text-gray-900 mb-8">
          Kayıt Formu
        </h2>
        
        <form onSubmit={handleSubmit} className="space-y-6">
          <Input
            label="Ad Soyad"
            type="text"
            placeholder="Adınız Soyadınız"
            value={formData.fullName}
            onChange={(e) => setFormData({ ...formData, fullName: e.target.value })}
            error={errors.fullName}
            required
          />
          
          <Input
            label="Email"
            type="email"
            placeholder="ornek@email.com"
            value={formData.email}
            onChange={(e) => setFormData({ ...formData, email: e.target.value })}
            error={errors.email}
            required
          />
          
          <Input
            label="Telefon"
            type="tel"
            placeholder="05XXXXXXXXX"
            value={formData.phone}
            onChange={(e) => setFormData({ ...formData, phone: e.target.value })}
            error={errors.phone}
            required
          />
          
          <div>
            <label className="block text-sm font-medium text-gray-700 mb-2">
              Kategori <span className="text-red-500">*</span>
            </label>
            <select
              value={formData.categoryId}
              onChange={(e) => setFormData({ ...formData, categoryId: e.target.value })}
              className="w-full px-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-primary focus:border-transparent"
              required
            >
              <option value="">Seçiniz</option>
              {mockCategories.map((cat) => (
                <option key={cat.id} value={cat.id}>
                  {cat.name}
                </option>
              ))}
            </select>
            {errors.categoryId && (
              <p className="text-red-500 text-sm mt-1">{errors.categoryId}</p>
            )}
          </div>
          
          <Input
            label="Mesaj (Opsiyonel)"
            type="textarea"
            placeholder="Mesajınızı yazın..."
            value={formData.message}
            onChange={(e) => setFormData({ ...formData, message: e.target.value })}
          />
          
          <Button
            type="submit"
            variant="primary"
            size="lg"
            isLoading={isSubmitting}
            className="w-full"
          >
            {isSubmitting ? 'Gönderiliyor...' : 'Gönder'}
          </Button>
        </form>
      </div>
    </section>
  )
}
```

### Back Button
```typescript
<BackButton />  // Sol üst köşe, fixed position
```

### Metadata (SEO)
```typescript
import { Metadata } from 'next'

export const metadata: Metadata = {
  title: '[Module A Adı] | [COMPANY_NAME]',
  description: '[150 karakterlik açıklama - PRD'den al]',
  openGraph: {
    title: '[Module A Adı]',
    description: '[OG açıklama]',
    images: ['/og-module-a.jpg'],
  },
}
```

---

IMPORTS:
```typescript
'use client'

import { useState } from 'react'
import { motion } from 'framer-motion'
import { z } from 'zod'
import { Card } from '@/components/shared/Card'
import { Input } from '@/components/shared/Input'
import { Button } from '@/components/shared/Button'
import { BackButton } from '@/components/layout/BackButton'
import { mockCategories } from '@/lib/data/categories'
import { slideUp, staggerContainer } from '@/lib/animations'
```

DEPENDENCIES:
```bash
npm install zod  # Form validation
```

ÇIKTI:
- `app/module-a/page.tsx` dosyası
- `lib/data/categories.ts` mock data
- Client-side form validation (Zod)
- Responsive layout

VERİFİCATION:
- http://localhost:3000/module-a → Sayfa render oluyor ✅
- Form validation çalışıyor (boş submit test et) ✅
- Submit mock alert gösteriyor ✅
- Back button home'a dönüyor ✅
- Responsive: Mobile ve desktop test et ✅
```

### 4.3 Module B Sayfası (app/[module-b]/page.tsx)

**GitHub Copilot Prompt:**
```markdown
SEN: React ve Next.js uzmanısın.

GÖREV: `app/module-b/page.tsx` sayfasını oluştur.

SAYFA YAPISI:
1. **Hero Section**

2. **Solutions Grid:**
   - Mock data: 4 çözüm
   - Card component: Image, title, description

3. **Certificate Showcase:**
   - Mock data: ISO sertifikaları (PDF thumbnails)
   - Grid layout
   - Modal: Tıklanınca büyük görsel

4. **Reference Carousel:**
   - Mock data: Müşteri logoları
   - Carousel component (horizontal scroll)

5. **Inquiry Form:**
   - Fields: Firma, Yetkili, Email, Telefon, Talep Türü, Mesaj
   - Submit button (disabled)

6. **Back Button**

MOCK DATA:
```typescript
const solutions = [
  { id: 1, title: "Çözüm 1", description: "Açıklama", image: "/placeholder.jpg" },
  // ... 3 tane daha
]

const certificates = [
  { id: 1, name: "ISO 9001", thumbnail: "/cert1.jpg" },
  // ... 5 tane daha
]

const references = [
  { id: 1, company: "Şirket 1", logo: "/logo1.png" },
  // ... 10 tane daha
]
```

ÇIKTI: `app/module-b/page.tsx` dosyası.
```

### 4.4 Module C Sayfası (app/[module-c]/page.tsx)

**GitHub Copilot Prompt:**
```markdown
SEN: React ve Next.js uzmanısın.

GÖREV: `app/module-c/page.tsx` sayfasını oluştur.

SAYFA YAPISI:
1. **Hero Section**

2. **Services Grid:**
   - Mock data: 6 hizmet
   - Card: Icon, title, description

3. **Project Showcase:**
   - Mock data: 8 proje
   - Grid: 2x2 mobile, 4x2 desktop
   - Card: Image, title, completion date

4. **Quote Form:**
   - Fields: Firma, Yetkili, Email, Telefon, Proje Açıklaması, Bütçe Aralığı
   - Submit button (disabled)

5. **Back Button**

MOCK DATA:
```typescript
const services = [
  { id: 1, title: "Hizmet 1", description: "Açıklama", icon: "🔧" },
  // ... 5 tane daha
]

const projects = [
  { id: 1, title: "Proje 1", image: "/project1.jpg", date: "2024-01" },
  // ... 7 tane daha
]
```

ÇIKTI: `app/module-c/page.tsx` dosyası.
```

### 4.5 Carousel Component (components/sections/Carousel.tsx)

**GitHub Copilot Prompt:**
```markdown
SEN: React ve animation uzmanısın.

GÖREV: `components/sections/Carousel.tsx` komponenti oluştur.

ÖZELLİKLER:
- Props: items (array), autoPlay (boolean), interval (number)
- Navigation: Previous/Next buttons
- Indicators: Dots (bottom)
- Touch: Swipe support (mobile)
- Animation: Smooth slide

LIBRARY: Swiper.js veya custom implementation

ÇIKTI: `components/sections/Carousel.tsx` dosyası.
```

---

**✅ FAZ 4 TAMAMLANDI!**

Çıktılar:
- ✅ Module A sayfası tamamlandı (kategoriler + form)
- ✅ Module B sayfası tamamlandı (çözümler + sertifikalar + referanslar + form)
- ✅ Module C sayfası tamamlandı (hizmetler + projeler + form)
- ✅ Tüm sayfalar mock verilerle çalışıyor
- ✅ Form'lar UI olarak hazır (submit disabled)

**Test:** Her modül sayfasını tarayıcıda kontrol et ✅

---

## ✨ FAZ 5: ANIMASYONLAR VE POLISH

> **SÜRE:** 2-3 saat  
> **ÇIKTI:** Smooth animations + micro-interactions

### 5.1 Page Transitions

**GitHub Copilot Prompt:**
```markdown
SEN: Framer Motion uzmanısın.

GÖREV: `lib/transitions.ts` dosyasını oluştur.

TRANSITIONS:
- pageTransition: Sayfa geçiş animasyonu config
- slideTransition: Slide left/right
- fadeTransition: Fade in/out

Her page.tsx'i PageTransition component ile wrap et.

ÇIKTI: `lib/transitions.ts` dosyası + page.tsx güncellemeleri.
```

### 5.2 Scroll Reveal Animations

**GitHub Copilot Prompt:**
```markdown
SEN: Intersection Observer uzmanısın.

GÖREV: `lib/hooks/useIntersection.ts` custom hook'u oluştur.

AMAÇ: Element viewport'a girdiğinde animation tetikle.

KULLANIM:
```typescript
const ref = useIntersection()
<motion.div ref={ref} variants={fadeIn}>Content</motion.div>
```

ÇIKTI: `lib/hooks/useIntersection.ts` dosyası.
```

### 5.3 Hover ve Click Animations

**Tüm interactive elementlere ekle:**
- Button: Hover scale (1.05), active scale (0.95)
- Card: Hover shadow, scale (1.02)
- Link: Underline animation

**GitHub Copilot Prompt:**
```markdown
SEN: Micro-interaction uzmanısın.

GÖREV: Tüm Button ve Card component'lerine hover/click animasyonları ekle.

ANIMATION:
- whileHover={{ scale: 1.05 }}
- whileTap={{ scale: 0.95 }}
- transition={{ type: "spring", stiffness: 300 }}

ÇIKTI: Güncellenmiş Button.tsx ve Card.tsx.
```

### 5.4 Loading States

**GitHub Copilot Prompt:**
```markdown
SEN: Loading state uzmanısın.

GÖREV: `components/shared/Loader.tsx` komponenti oluştur.

TYPES:
- Spinner: Rotating circle
- Skeleton: Content placeholder
- Progress: Linear progress bar

ÇIKTI: `components/shared/Loader.tsx` dosyası.
```

---

**✅ FAZ 5 TAMAMLANDI!**

Çıktılar:
- ✅ Page transitions uygulandı
- ✅ Scroll reveal animations eklendi
- ✅ Hover ve click micro-interactions
- ✅ Loading states hazır

**Test:** Tüm sayfaları gez, animasyonların smooth olduğunu kontrol et ✅

---

## 📱 FAZ 6: RESPONSIVE VE ACCESSIBILITY

> **SÜRE:** 2-3 saat  
> **ÇIKTI:** Mobile-friendly + WCAG 2.1 AA compliant

### 6.1 Responsive Design Audit

**Test Cihazları:**
- Mobile: iPhone 13 (390x844), Samsung Galaxy S21 (360x800)
- Tablet: iPad Pro (1024x1366)
- Desktop: 1920x1080, 2560x1440

**GitHub Copilot Prompt:**
```markdown
SEN: Responsive design uzmanısın.

GÖREV: Tüm sayfaları ve component'leri responsive yap.

KONTROL LİSTESİ:
- [ ] Grid layouts: 1 col mobile, 2 col tablet, 3-4 col desktop
- [ ] Font sizes: Responsive (text-base → text-lg)
- [ ] Spacing: Smaller mobile padding/margin
- [ ] Navigation: Mobile menu (eğer varsa)
- [ ] Images: Responsive sizes, lazy loading
- [ ] Forms: Full-width mobile, 50% desktop

TAILWIND BREAKPOINTS:
- sm: 640px
- md: 768px
- lg: 1024px
- xl: 1280px
- 2xl: 1536px

ÇIKTI: Güncellenmiş component'ler.
```

### 6.2 Accessibility Audit

**GitHub Copilot Prompt:**
```markdown
SEN: Web accessibility (a11y) uzmanısın.

GÖREV: WCAG 2.1 AA standardına göre tüm sayfaları kontrol et.

KONTROL LİSTESİ:
- [ ] **Alt texts:** Tüm image'lerde alt attribute
- [ ] **ARIA labels:** Button'larda aria-label (icon-only)
- [ ] **Keyboard navigation:** Tab order doğru, focus visible
- [ ] **Color contrast:** 4.5:1 minimum (text/background)
- [ ] **Form labels:** Her input'ta <label> var
- [ ] **Error messages:** Screen reader accessible
- [ ] **Semantic HTML:** <header>, <main>, <footer>, <nav>
- [ ] **Skip to content:** Link (görünmez, keyboard ile erişilebilir)

TOOLS:
- Lighthouse (Accessibility score)
- axe DevTools (Chrome extension)

ÇIKTI: Düzeltilmiş component'ler + accessibility report.
```

### 6.3 SEO Metadata

**GitHub Copilot Prompt:**
```markdown
SEN: SEO uzmanısın.

GÖREV: Her page.tsx'e `metadata` export ekle.

ÖRNEK:
```typescript
export const metadata: Metadata = {
  title: "Module A | [COMPANY_NAME]",
  description: "150 karakterlik açıklama",
  openGraph: {
    title: "Module A",
    description: "OG açıklama",
    images: ["/og-image-module-a.jpg"],
  },
}
```

SAYFALAR:
- app/page.tsx
- app/module-a/page.tsx
- app/module-b/page.tsx
- app/module-c/page.tsx

ÇIKTI: Güncellenmiş page.tsx dosyaları.
```

---

**✅ FAZ 6 TAMAMLANDI!**

Çıktılar:
- ✅ Tüm sayfalar responsive (mobile, tablet, desktop)
- ✅ WCAG 2.1 AA compliant
- ✅ SEO metadata eklendi
- ✅ Lighthouse score: 90+ (tüm kategoriler)

**Test:**
- Chrome DevTools: Mobile view test et
- Lighthouse: Accessibility ve SEO skorlarını kontrol et ✅

---

## 🧪 FAZ 7: MOCK DATA VE TEST

> **SÜRE:** 1-2 saat  
> **ÇIKTI:** Mock data dosyaları + End-to-end test

### 7.1 Mock Data Dosyaları Oluşturma

**GitHub Copilot Prompt:**
```markdown
SEN: Data modeling uzmanısın.

GÖREV: `lib/data/` klasöründe mock data dosyaları oluştur.

DOSYALAR:
1. **videos.ts:** Landing page videoları
2. **categories.ts:** Module A kategorileri
3. **solutions.ts:** Module B çözümleri
4. **certificates.ts:** Module B sertifikaları
5. **references.ts:** Module B referansları
6. **services.ts:** Module C hizmetleri
7. **projects.ts:** Module C projeleri

HER DOSYA:
- TypeScript types
- Export const mockData
- Realistic data (örnek: gerçek şirket isimleri, açıklamalar)

ÖRNEK:
```typescript
// lib/data/videos.ts
import { Video } from '@/types'

export const mockVideos: Video[] = [
  {
    id: 1,
    title: "Module A Tanıtımı",
    thumbnail: "/assets/thumbnails/module-a.jpg",
    url: "https://youtube.com/watch?v=...",
    module: "module-a"
  },
  // ... 2 tane daha
]
```

ÇIKTI: 7 mock data dosyası.
```

### 7.2 Mock Data'yı Sayfalarda Kullanma

**GitHub Copilot Prompt:**
```markdown
SEN: React ve Next.js uzmanısın.

GÖREV: Sayfalardaki inline mock data'ları `lib/data/` dosyalarından import et.

DEĞİŞTİRİLECEK SAYFALAR:
- app/page.tsx → import { mockVideos } from '@/lib/data/videos'
- app/module-a/page.tsx → import { mockCategories } from '@/lib/data/categories'
- app/module-b/page.tsx → import { mockSolutions, mockCertificates, mockReferences }
- app/module-c/page.tsx → import { mockServices, mockProjects }

ÇIKTI: Güncellenmiş page.tsx dosyaları.
```

### 7.3 Manual Testing Checklist

**Test Senaryoları:**

**Landing Page:**
- [ ] Preloader ilk ziyarette görünüyor
- [ ] Preloader ikinci ziyarette görünmüyor (localStorage)
- [ ] Hero section animasyonu çalışıyor
- [ ] Video showcase kartları tıklanıyor
- [ ] Kartlara tıklandığında doğru sayfaya gidiyor

**Module A Page:**
- [ ] Hero section render oluyor
- [ ] Kategoriler grid olarak görünüyor
- [ ] Form alanları doldurulabiliyor
- [ ] Submit butonu disabled (backend henüz yok)
- [ ] Back button home'a dönüyor

**Module B Page:**
- [ ] Çözümler, sertifikalar, referanslar görünüyor
- [ ] Carousel çalışıyor (swipe/click)
- [ ] Form doldurulabiliyor
- [ ] Back button çalışıyor

**Module C Page:**
- [ ] Hizmetler ve projeler görünüyor
- [ ] Form doldurulabiliyor
- [ ] Back button çalışıyor

**Responsive:**
- [ ] Mobile (360px): Tüm sayfalar kullanılabilir
- [ ] Tablet (768px): Grid layout'lar doğru
- [ ] Desktop (1920px): İçerik centered, max-width var

**Accessibility:**
- [ ] Klavye ile navigate edilebiliyor (Tab)
- [ ] Focus visible (outline var)
- [ ] Screen reader test (NVDA/VoiceOver)

### 7.4 Performance Test (Lighthouse)

**Hedef Skorlar:**
- ⚡ Performance: 90+
- ♿ Accessibility: 95+
- ✅ Best Practices: 90+
- 🔍 SEO: 95+

**İyileştirmeler:**
- [ ] Image optimization: next/image kullan
- [ ] Font optimization: next/font kullan
- [ ] Code splitting: Dynamic imports (lazy loading)
- [ ] Bundle size: Unused dependencies kaldır

---

**✅ FAZ 7 TAMAMLANDI!**

Çıktılar:
- ✅ Mock data dosyaları oluşturuldu
- ✅ Tüm sayfalar test edildi
- ✅ Responsive test tamamlandı
- ✅ Accessibility audit passed
- ✅ Lighthouse score: 90+

---

## 🎉 FRONTEND GELİŞTİRME TAMAMLANDI!

### 📦 Proje Çıktıları:

✅ **Landing Page:** Hero + Video Showcase + Footer  
✅ **Module A Page:** Kategoriler + Kayıt Formu  
✅ **Module B Page:** Çözümler + Sertifikalar + Referanslar + Talep Formu  
✅ **Module C Page:** Hizmetler + Projeler + Teklif Formu  
✅ **Component Library:** 10+ reusable component  
✅ **Responsive:** Mobile, tablet, desktop  
✅ **Accessible:** WCAG 2.1 AA compliant  
✅ **Animated:** Framer Motion transitions  
✅ **Mock Data:** 7 veri dosyası (backend için hazır)

---

## 📋 SONRAKI ADIMLAR (Backend Entegrasyonu)

**Şimdi Ne Yapmalı?**

1. **Müşteriye Göster:**
   - Frontend demo (localhost veya Vercel preview)
   - Mock verilerle tam fonksiyonel
   - Feedback al, revizyonlar yap

2. **Backend Ekibine Aktar:**
   - `FRONTEND-DOCS/API-CONTRACT.md` oluştur
   - Frontend'in beklediği API'leri belirt
   - Mock data'ları referans göster (backend'in DB'ye ekleyeceği veriler)

3. **Database Şemasını Belirle:**
   - Mock data'lara bakarak tablo yapılarını tasarla
   - Frontend'deki form field'larına göre submission tabloları

4. **Entegrasyon Hazırlığı:**
   - Form'lardaki submit handler'ları hazırla
   - API fetch fonksiyonları yaz (şimdilik mock return)
   - Environment variables ekle (.env.local)

---

## 🚀 DEPLOYMENT (Opsiyonel - Müşteriye Göstermek İçin)

### Vercel (Hızlı Deploy)

```powershell
# Vercel CLI kur
npm i -g vercel

# Deploy
vercel

# Production deploy
vercel --prod
```

**Avantajlar:**
- 2 dakikada canlı
- Otomatik HTTPS
- Preview URL (her commit için)

---

## 📚 DOKÜMANTASYON

**Oluşturulması Gereken Dökümanlar:**

1. **API-CONTRACT.md:**
   ```markdown
   # API Contract - Frontend → Backend
   
   ## POST /api/module-a/register
   Request:
   {
     "fullName": string,
     "email": string,
     "phone": string,
     "categoryId": number,
     "message": string
   }
   
   Response:
   {
     "success": boolean,
     "message": string,
     "submissionId": number
   }
   ```

2. **COMPONENT-LIBRARY.md:** Component kullanım kılavuzu
3. **DEPLOYMENT-GUIDE.md:** Deploy adımları

---

**🎊 TEBRİKLER! Frontend tamamlandı ve müşteriye gösterilmeye hazır!**

**Toplam Süre:** 1-2 hafta (1 kişi, part-time)  
**Sonraki Faz:** Backend geliştirme (paralel çalışılabilir)  
**Proje Durumu:** 🟢 Frontend Complete, 🟡 Backend Pending
