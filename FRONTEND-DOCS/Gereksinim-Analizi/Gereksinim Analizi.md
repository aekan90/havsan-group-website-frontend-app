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

2. **VS Code ile aç:**
   - VS Code'u aç
   - `File → Open Folder`
   - Oluşturduğun boş klasörü seç

3. **VS Code'da Terminal aç:**
   - `` Ctrl + ` `` (backtick tuşu)
   - Veya `Terminal → New Terminal`

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
├── FRONTEND-ROADMAP.md              # Bu dosya (kopyala buraya)
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

**🔹 Şimdi Müşteri Dökümanlarını Ekle:**

1. **İster Dokümanı (AI'ya verilecek):**
   ```
   FRONTEND-DOCS/Gereksinim-Analizi/ klasörüne kopyala
   
   Örnek:
   - Gereksinim Analizi.pdf (müşteriden gelen orijinal)
   - Gereksinim Analizi.md (PDF'den markdown'a çevrilmiş)
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
SEN: Senior Product Manager ve UX Designer'sın.

GÖREV: `#file:FRONTEND-DOCS/Gereksinim-Analizi/Gereksinim Analizi.md` dosyasını oku ve FRONTEND-PRD.md oluştur.

PRD İÇERİĞİ:
1. **Proje Özeti:** Elevator pitch (2-3 cümle)
2. **Hedef Kitle:** Kim kullanacak? (user personas)
3. **Sayfa Yapısı:**
   - Landing page (Hero, Video Showcase, Footer)
   - Module A sayfası (Kategoriler + Form)
   - Module B sayfası (Çözümler + Sertifikalar + Referanslar + Form)
   - Module C sayfası (Hizmetler + Projeler + Form)
4. **UI/UX Gereksinimleri:**
   - Color palette (brand colors)
   - Typography (font'lar)
   - Component library (Button, Card, Input, Modal)
5. **İnteraktif Özellikler:**
   - Animasyonlar (Framer Motion)
   - Form validations
   - Responsive breakpoints
6. **İçerik Gereksinimleri:**
   - Hangi statik veriler gerekli? (mock data)
   - Hangi form'lar olacak?

FORMAT: Markdown, detaylı, developer-friendly

ÇIKTI: `FRONTEND-DOCS/FRONTEND-PRD.md` dosyası olarak kaydet.
```

**Çıktı Kontrolü:**
- ✅ FRONTEND-PRD.md oluşturuldu
- ✅ Tüm sayfa yapıları tanımlandı
- ✅ Component listesi netleşti

---

### 0.9 FRONTEND-TASKS.md Oluşturma (AI ile)

> **🤖 AMAÇ:** PRD'den actionable task listesi çıkarmak.

**GitHub Copilot Prompt:**

```markdown
SEN: Agile Scrum Master'sın.

GÖREV: `#file:FRONTEND-DOCS/FRONTEND-PRD.md` dosyasını oku ve FRONTEND-TASKS.md oluştur.

TASK LİSTESİ YAPISI:
- [ ] **Faz 0:** Proje hazırlık ✅ (tamamlandı)
- [ ] **Faz 1:** Design System ve Klasör Yapısı
  - [ ] Tailwind config güncelle
  - [ ] Global styles ekle
  - [ ] TypeScript types tanımla
  - [ ] Utility functions yaz
- [ ] **Faz 2:** Global Component'ler
  - [ ] Button component
  - [ ] Card component
  - [ ] Input component
  - [ ] Modal component
  - [ ] Preloader component
- [ ] **Faz 3:** Landing Page
  - [ ] Hero section
  - [ ] Video showcase
  - [ ] Footer (social links)
- [ ] **Faz 4:** Modül Sayfaları
  - [ ] Module A (kategoriler + form)
  - [ ] Module B (çözümler + sertifikalar + form)
  - [ ] Module C (hizmetler + projeler + form)
- [ ] **Faz 5:** Animasyonlar
- [ ] **Faz 6:** Responsive & Accessibility
- [ ] **Faz 7:** Mock Data & Test

FORMAT: GitHub checkbox formatı, priority etiketleri

ÇIKTI: `FRONTEND-DOCS/FRONTEND-TASKS.md` dosyası olarak kaydet.
```

**Çıktı Kontrolü:**
- ✅ FRONTEND-TASKS.md oluşturuldu
- ✅ Tüm task'lar listelenmiş
- ✅ Checkbox formatı doğru

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

**GitHub Copilot Prompt:**
```markdown
SEN: Senior Frontend Developer ve Design System uzmanısın.

GÖREV: `tailwind.config.ts` dosyasını güncelle.

DESIGN SYSTEM:
- **Colors:**
  - Primary: Blue (#0066CC, #004C99, #003366)
  - Secondary: Red (#E31837, #B91429)
  - Accent: Green (#00A86B), Yellow (#FFB900), Orange (#FF6B00)
  - Neutral: Gray scale (50-950)

- **Fonts:**
  - System fonts: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto

- **Spacing:**
  - Custom: 18, 22, 26 (Tailwind default'a ek)

- **Animations:**
  - fadeIn, slideUp, scaleUp

ÇIKTI: Güncellenmiş `tailwind.config.ts` dosyası.
```

### 1.3 Global Styles (globals.css)

**GitHub Copilot Prompt:**
```markdown
SEN: CSS uzmanısın.

GÖREV: `app/globals.css` dosyasını güncelle.

İÇERİK:
- Tailwind directives (@tailwind base, components, utilities)
- Custom scrollbar styles
- Smooth scroll behavior
- Selection color (brand color)
- Focus visible styles

ÇIKTI: Güncellenmiş `app/globals.css` dosyası.
```

### 1.4 TypeScript Types Tanımlama

**GitHub Copilot Prompt:**
```markdown
SEN: TypeScript uzmanısın.

GÖREV: `types/index.ts` dosyasını oluştur.

TYPES:
- Card (title, description, image, link)
- Video (id, title, thumbnail, url, module)
- FormData (generic form interface)
- Category, Solution, Service (module-specific)

ÇIKTI: `types/index.ts` dosyası.
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

**GitHub Copilot Prompt:**
```markdown
SEN: React Component Library uzmanısın.

GÖREV: `components/shared/Button.tsx` komponenti oluştur.

ÖZELLİKLER:
- Variants: primary, secondary, ghost, danger
- Sizes: sm, md, lg
- States: default, hover, active, disabled, loading
- Icons: Optional leading/trailing icon
- TypeScript: Strict typing
- Accessibility: ARIA labels, keyboard navigation

ÇIKTI: `components/shared/Button.tsx` dosyası.
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

**GitHub Copilot Prompt:**
```markdown
SEN: Senior React Developer'sın.

GÖREV: `app/page.tsx` landing page'i oluştur.

SAYFA YAPISI:
1. **Hero Section:**
   - Full-screen (h-screen)
   - Company logo (merkez, büyük)
   - Slogan (alt, fade-in animation)
   - Scroll indicator (arrow down, bounce animation)

2. **Video Showcase Section:**
   - 3 modül kartı (grid layout)
   - Her kart: Thumbnail, başlık, açıklama, "İncele" butonu
   - Hover: Scale effect
   - Navigate: useRouter ile modül sayfasına git

3. **Footer:**
   - Social links component
   - Copyright text
   - Background: Dark

ANIMATION:
- Framer Motion: Scroll reveal animations
- Stagger: Kartlar sırayla appear

MOCK DATA:
- 3 video: moduleA, moduleB, moduleC
- Thumbnail'ler: Placeholder image (unsplash)

ÇIKTI: `app/page.tsx` dosyası.
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

**GitHub Copilot Prompt:**
```markdown
SEN: React ve Next.js uzmanısın.

GÖREV: `app/module-a/page.tsx` sayfasını oluştur.

REFERANS: `#file:FRONTEND-DOCS/FRONTEND-PRD.md` dosyasındaki Module A açıklaması

SAYFA YAPISI:
1. **Hero Section:**
   - Başlık: "Module A"
   - Açıklama: Kısa tanıtım
   - Background: Gradient

2. **Video Player Section:**
   - Embedded video (YouTube/Vimeo)
   - veya placeholder video

3. **Category Grid:**
   - Mock data: 6 kategori
   - Card component kullan
   - Grid: 2 col mobile, 3 col desktop

4. **Registration Form:**
   - Fields: Ad Soyad, Email, Telefon, Kategori (select), Mesaj
   - Input component kullan
   - Submit button (disabled - backend henüz yok)
   - Form validation (client-side)

5. **Back Button:**
   - Sol üst köşe
   - Navigate: "/" (home)

MOCK DATA:
```typescript
const categories = [
  { id: 1, name: "Kategori 1", description: "Açıklama", icon: "📚" },
  { id: 2, name: "Kategori 2", description: "Açıklama", icon: "🎓" },
  // ... 4 tane daha
]
```

ANIMATION: Scroll reveal (fadeIn, slideUp)

ÇIKTI: `app/module-a/page.tsx` dosyası.
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
