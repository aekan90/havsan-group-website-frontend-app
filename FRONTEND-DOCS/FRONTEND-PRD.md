# 🎯 FRONTEND PRODUCT REQUIREMENTS DOCUMENT

## 1. 📋 EXECUTIVE SUMMARY

- **Proje Adı:** Havsan Group Corporate Website
- **Elevator Pitch:** Havsan Group'un 3 ana iş kolu (Robotik Kodlama, AI & Yazılım Çözümleri, Enerji) için modern, animasyonlu ve kullanıcı dostu kurumsal web platformu.
- **Hedef:** Potansiyel müşterilerin 3 tıklamada istedikleri bilgiye ulaşması, her iş kolunun profesyonel tanıtımı ve lead generation.
- **Teknoloji Stack:** Next.js 14 (App Router), TypeScript, Tailwind CSS, Framer Motion
- **Zaman Çizelgesi:** 1-2 hafta (Frontend-Only, mock data ile)

## 2. 👥 USER PERSONAS

### Persona 1: "Kurumsal Karar Verici"
- **Demografik:** 35-55 yaş, C-level/departman müdürü, orta-yüksek teknik bilgi
- **Hedefler:** Şirket için yapay zeka eğitimi, yazılım çözümü veya enerji danışmanlığı almak
- **Pain Points:** Güvenilir, deneyimli partner bulamama, hizmet kalitesi belirsizliği
- **Kullanım Senaryosu:** Ana sayfa → İlgili modül → Hizmet detayları → İletişim formu

### Persona 2: "Veli/Ebeveyn"
- **Demografik:** 28-45 yaş, çocuk sahibi, düşük-orta teknik bilgi
- **Hedefler:** Çocuğu için kaliteli robotik kodlama eğitimi bulmak
- **Pain Points:** Eğitim kalitesi endişesi, maliyet kaygısı, lokasyon uygunluğu
- **Kullanım Senaryosu:** Ana sayfa → Robotik Kodlama → Video izleme → Ücretsiz deneme başvurusu

### Persona 3: "Teknoloji Meraklısı Öğrenci"
- **Demografik:** 16-25 yaş, öğrenci/mezun, yüksek teknik bilgi
- **Hedefler:** Kendini geliştirmek için yapay zeka, kodlama eğitimleri almak
- **Pain Points:** Bütçe kısıtı, pratik odaklı eğitim bulamama
- **Kullanım Senaryosu:** Ana sayfa → AI Eğitimleri → Eğitim programları → Kayıt formu

### Persona 4: "GES Yatırımcısı/İşletmecisi"
- **Demografik:** 40-60 yaş, enerji sektörü profesyoneli, yüksek teknik bilgi
- **Hedefler:** GES bakım, arıza tespiti, performans optimizasyonu hizmeti
- **Pain Points:** Verimsiz bakım süreçleri, arıza tespitinde gecikme
- **Kullanım Senaryosu:** Ana sayfa → Enerji → Hizmet detayları → Teklif talebi

## 3. 🏗️ SAYFA YAPISI VE WIREFRAME AÇIKLAMALARI

### 3.1 Landing Page (Ana Sayfa)
**URL:** `/`

**Bölümler (Top to Bottom):**

1. **Preloader (İlk Yükleme):**
   - Animasyon: "HAVSAN" ve "Grup" yazıları üstten-alttan birleşme
   - Süre: 2-3 saniye
   - Referans: Tempergroup.com.au stili (Bkz: PDF Sayfa 2)
   - Sosyal medya linkleri: WhatsApp, Instagram, LinkedIn (1 saniye sonra kaybolur)

2. **Hero Section:**
   - İçerik: "HAVSAN Grup" ana başlığı
   - Layout: Full-screen, centered
   - Animasyon: Fade-in + slide-up efektleri
   - CTA: Scroll indicator (aşağı ok animasyonu)

3. **Modül Kartları Showcase:**
   - İçerik: 3 ana iş kolu kartı
     1. **Havsan Robotik Kodlama Merkezi** (Elazığ)
     2. **Havsan AI** (Yapay Zeka & Yazılım)
     3. **Havsan Enerji** (GES Çözümleri)
   - Layout: 
     - Desktop: 3 kart yan yana (Google FX stili - PDF Sayfa 3)
     - Mobile: 3 kart alt alta, scroll'suz görünür (Sabancı stili - PDF Sayfa 5)
   - Hover Efektleri: Renk canlanma, gölge artışı, hafif scale (PDF Sayfa 4)
   - CTA: Kartlara tık → ilgili modül sayfasına yönlendirme

4. **Footer:**
   - İçerik: Copyright, sosyal medya linkleri
   - Layout: Minimal, dark theme

**Wireframe:**
```
┌─────────────────────────┐
│      PRELOADER          │
│   [HAVSAN] [Grup]       │
│  [Social Links - 1s]    │
└─────────────────────────┘
            ↓
┌─────────────────────────┐
│       HERO SECTION      │
│                         │
│      HAVSAN GRUP        │
│   [Scroll Indicator]    │
│                         │
└─────────────────────────┘
            ↓
┌─────────────────────────┐
│    [CARD 1]  [CARD 2]   │
│   Robotik     AI &      │
│   Kodlama   Yazılım     │
│                         │
│      [CARD 3]           │
│       Enerji            │
└─────────────────────────┘
            ↓
┌─────────────────────────┐
│        FOOTER           │
│   © HAVSAN | [Social]   │
└─────────────────────────┘
```

### 3.2 Havsan Robotik Kodlama Sayfası
**URL:** `/robotik-kodlama`
**Başlık:** "Havsan Robotik Kodlama Merkezi - Elazığ"

**Bölümler:**
1. **Hero Section:**
   - İçerik: "Çocuklar için Robotik Kodlama Eğitimi"
   - Alt başlık: "Elazığ Ataşehir Akademi"
   - Lokasyon: 38.656075, 39.167103
   - CTA: "Ücretsiz 2 Saat Deneme Dersi"

2. **Video Showcase:**
   - İçerik: 3 adet YouTube video
   - URLs: 
     - https://www.youtube.com/shorts/OFbR8CATsVE
     - https://www.youtube.com/shorts/4oRs3L9Gia4  
     - https://www.youtube.com/shorts/5wUXXJfoVOE
   - Özellik: Hover'da auto-preview
   - Layout: Grid 1x3 desktop, 1x1 mobile

3. **Eğitim Kategorileri:**
   - İçerik: Yaş grupları ve program detayları (mock data)
   - Layout: Grid 2x2 mobile, 3x2 desktop
   - Cards: Yaş grubu, süre, kazanımlar

4. **Kayıt Formu:**
   - Form Adı: "Ücretsiz Deneme Dersi Kayıt"
   - Email hedef: bilgi@havsanrobotik.com.tr
   - Fields: Öğrenci adı, yaşı, veli adı, telefon, email

5. **Back Button:** Sol üst köşe

### 3.3 Havsan AI Sayfası
**URL:** `/yapay-zeka-yazilim`
**Başlık:** "Havsan AI - Yapay Zeka & Yazılım Çözümleri"

**Bölümler:**
1. **Hero Section:**
   - İçerik: "Kurumsal Yapay Zeka ve Yazılım Çözümleri"
   - Alt başlık: "Google Partner - Ankara Yenimahalle"
   - Lokasyon: 39°57'14.1"N 32°47'08.0"E

2. **Hizmet Kategorileri:**
   - **Kurumsal AI Eğitimi:** Eğitim programları, takvim
   - **Google Workspace:** Kurulum, eğitim, danışmanlık
   - **Yazılım Geliştirme:** Mobile (iOS/Android), Web
   - **Danışmanlık:** ISO 42001, ISO 27001, KVKK

3. **Sertifikalar & Sosyal Kanıt:**
   - ISO sertifika görselleri (Modal'da büyük gösterim)
   - Müşteri referans logoları (carousel)

4. **İletişim Formu:**
   - Form Adı: "Proje Teklifi Talebi"
   - Fields: Firma, yetkili, email, telefon, proje türü, bütçe

5. **Back Button:** Sol üst köşe

### 3.4 Havsan Enerji Sayfası
**URL:** `/enerji-cozumleri`
**Başlık:** "Havsan Enerji - GES Çözümleri"

**Bölümler:**
1. **Hero Section:**
   - İçerik: "Güneş Enerjisi Santrali Çözümleri"
   - Alt başlık: "Yapay Zeka Destekli Arıza Tespiti"

2. **Hizmet Kategorileri:**
   - **GES Bakım:** Bakım, onarım, takip
   - **Drone İzleme:** Termal görüntüleme
   - **Panel Temizliği:** Profesyonel temizlik
   - **Performans Analizi:** Güç takibi, optimizasyon
   - **Depolamalı GES:** Danışmanlık

3. **Teknoloji Vurgusu:**
   - AI destekli arıza tespiti
   - Sahaya özel hızlı tanı

4. **Teklif Formu:**
   - Form Adı: "GES Hizmet Talebi"
   - Fields: Firma, yetkili, santral lokasyonu, kurulu güç, hizmet türü

5. **Back Button:** Sol üst köşe

## 4. 🎨 DESIGN SYSTEM

### 4.1 Color Palette

**Global Brand Colors (Google Palette):**
- **Primary:** #4285F4 (Yaban Mersini/Google Blue)
- **Secondary:** #34A853 (Deniz Yeşili/Google Green)  
- **Accent:** #EA4335 (Zincifre/Google Red)
- **Warning:** #FBBC05 (Seçici Sarı/Google Yellow)

**Modül Özel Renk Paletleri:**

**Robotik Kodlama:**
- Primary: #4285F4 (Teknoloji Mavisi)
- Secondary: #E3E5E8 (Platin Gümüş)
- Accent: #FBBC05 (Devre Sarısı)
- Dark: #1A237E (Derin Uzay Laciverti)

**Havsan AI (Gradient):**
- Start: #4E85EB (Mavi)
- Middle: #8875D6 (Mor)
- End: #D9666F (Mercan)

**Havsan Enerji (Solar Spectrum):**
- Primary: #F3C242 (Polisilikon)
- Secondary: #F99F1B (Külçe)
- Tertiary: #E87D25 (Gofret)
- Quaternary: #EE5F26 (Hücre)
- Quinary: #F15B24 (Modül)
- Success: #00A786 (Montaj)
- Info: #009CC9 (Güç Çevirici)

**Semantic Colors:**
- Success: #10B981
- Error: #EF4444  
- Warning: #F59E0B
- Info: #3B82F6
- Neutral: Gray scale (50-950)

### 4.2 Typography

**Font Family:**
- Heading: -apple-system, BlinkMacSystemFont, "San Francisco" (Apple fonts talebi)
- Body: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif

**Type Scale:**
- H1: 3rem (48px), font-weight-700, line-height-1.2
- H2: 2.25rem (36px), font-weight-600, line-height-1.3  
- H3: 1.875rem (30px), font-weight-600, line-height-1.4
- H4: 1.5rem (24px), font-weight-500, line-height-1.4
- Body: 1rem (16px), font-weight-400, line-height-1.6
- Caption: 0.875rem (14px), font-weight-400, line-height-1.5

### 4.3 Spacing System
Tailwind default spacing + custom values:
- xs: 2px
- sm: 4px  
- md: 8px
- lg: 16px
- xl: 24px
- 2xl: 32px
- 3xl: 48px

### 4.4 Component Library

**Gerekli Component'ler:**

1. **Button**
   - Variants: primary, secondary, outline, ghost, danger
   - Sizes: sm (32px), md (40px), lg (48px)
   - States: default, hover, active, disabled, loading

2. **Card**
   - Props: image, title, description, link, badge, gradient
   - Hover: scale(1.02), shadow-lg, border glow
   - Variants: default, gradient (AI modülü için)

3. **Input**
   - Types: text, email, tel, textarea, select
   - States: default, focus, error, disabled
   - Validation: Real-time error display

4. **Modal**
   - Props: isOpen, onClose, title, children, size
   - Use cases: Sertifika büyütme, video player
   - Backdrop: Click to close, ESC support

5. **Carousel**
   - Use case: Referans logoları showcase
   - Features: Auto-play, navigation dots, swipe support

6. **Preloader**
   - Animation: "HAVSAN" + "Grup" merge effect
   - Duration: 2-3 saniye, localStorage control

7. **VideoPlayer**
   - Props: videoUrl, thumbnail, autoPlay
   - Features: Hover preview, YouTube integration

## 5. ⚡ İNTERAKTİF ÖZELLİKLER

### 5.1 Animasyonlar (Framer Motion)

**Page Transitions:**
- Enter: fadeIn + slideUp (0.4s ease-out)
- Exit: fadeOut + slideDown (0.3s ease-in)

**Scroll Reveal:**
- Cards: fadeIn + slideUp (stagger 0.1s)
- Sections: fadeIn + slideUp (0.5s delay)

**Hover Effects:**
- Buttons: scale(1.05) + shadow glow
- Cards: scale(1.02) + shadow-xl + border glow
- Videos: scale(1.1) + play overlay

**Preloader Sequence:**
1. "HAVSAN" slide from top (0.5s)
2. "Grup" slide from bottom (0.5s, 0.2s delay)  
3. Social links fade-in (0.3s, 1s delay)
4. All fade-out (0.5s, 2s delay)

### 5.2 Form Validations (Client-Side)

**Validation Rules:**
- **Name:** Required, min 2 characters, only letters
- **Email:** Required, valid email format
- **Phone:** Required, Turkish format (0XXX XXX XX XX)
- **Age (Robotik):** Required, number 6-18
- **Company (AI/Enerji):** Required for B2B forms
- **Message:** Optional, max 500 characters

**Error States:**
- Real-time validation on blur
- Red border + error message below field
- Submit disabled until all required fields valid

### 5.3 Responsive Breakpoints (Tailwind)

- **Mobile:** 640px (sm) - 1 column grid
- **Tablet:** 768px (md) - 2 column grid  
- **Desktop:** 1024px (lg) - 3-4 column grid
- **Large Desktop:** 1280px (xl) - Max-width container

**Responsive Davranışlar:**
- **Grid Cards:** 1 col → 2 col → 3 col → 4 col
- **Typography:** Responsive font scaling
- **Spacing:** Mobile padding 16px, Desktop 24px
- **Images:** Responsive sizing with aspect ratio

## 6. 📊 İÇERİK GEREKSİNİMLERİ (MOCK DATA)

### 6.1 Landing Page Mock Data

```typescript
interface ModuleCard {
  id: string;
  title: string;
  description: string;
  image: string;
  color: string;
  route: string;
}

const moduleCards: ModuleCard[] = [
  {
    id: 'robotik',
    title: 'Havsan Robotik Kodlama Merkezi',
    description: 'Çocuklar için interaktif robotik kodlama eğitimleri',
    image: '/images/robotik-hero.jpg',
    color: '#4285F4',
    route: '/robotik-kodlama'
  },
  {
    id: 'ai',
    title: 'Havsan AI',
    description: 'Yapay Zeka ve Yazılım Çözümleri',
    image: '/images/ai-hero.jpg', 
    color: 'linear-gradient(135deg, #4E85EB, #8875D6, #D9666F)',
    route: '/yapay-zeka-yazilim'
  },
  {
    id: 'enerji',
    title: 'Havsan Enerji',
    description: 'Güneş Enerjisi Santrali Çözümleri',
    image: '/images/enerji-hero.jpg',
    color: '#F3C242',
    route: '/enerji-cozumleri'
  }
];
```

### 6.2 Robotik Kodlama Mock Data

```typescript
interface AgeGroup {
  id: string;
  name: string;
  ageRange: string;
  duration: string;
  description: string;
  skills: string[];
}

const ageGroups: AgeGroup[] = [
  {
    id: 'junior',
    name: 'Junior Robotikçi',
    ageRange: '6-8 yaş',
    duration: '12 hafta',
    description: 'Temel robot kontrolü ve görsel programlama',
    skills: ['Scratch Jr', 'Temel robot hareketleri', 'Problem çözme']
  },
  {
    id: 'intermediate', 
    name: 'Genç Mucit',
    ageRange: '9-12 yaş',
    duration: '16 hafta', 
    description: 'Orta seviye robotik ve sensör kullanımı',
    skills: ['Scratch', 'Sensör programlama', 'Proje geliştirme']
  }
  // ... daha fazla yaş grubu
];

const videos = [
  {
    id: 1,
    title: 'Robot Futbol Turnuvası',
    youtubeId: 'OFbR8CATsVE',
    thumbnail: '/images/video1-thumb.jpg'
  }
  // ... diğer videolar
];
```

### 6.3 Havsan AI Mock Data

```typescript
interface Service {
  id: string;
  category: string;
  title: string;
  description: string;
  features: string[];
  icon: string;
}

const aiServices: Service[] = [
  {
    id: 'ai-education',
    category: 'Eğitim',
    title: 'Kurumsal Yapay Zeka Eğitimi',
    description: 'Çalışanlarınız için özelleştirilmiş AI eğitim programları',
    features: ['Temel AI kavramları', 'ChatGPT kullanımı', 'AI araçları'],
    icon: '🎓'
  },
  {
    id: 'google-workspace',
    category: 'Danışmanlık',
    title: 'Google Workspace Çözümleri', 
    description: 'Google Partner olarak profesyonel kurulum ve eğitim',
    features: ['Kurulum', 'Migrate', 'Eğitim', 'Destek'],
    icon: '🚀'
  }
  // ... diğer hizmetler
];

const certificates = [
  {
    id: 'iso42001',
    name: 'ISO 42001 - AI Yönetim Sistemi',
    image: '/images/iso42001.jpg',
    issueDate: '2024'
  }
  // ... diğer sertifikalar
];
```

### 6.4 Havsan Enerji Mock Data

```typescript
interface EnergyService {
  id: string;
  title: string;
  description: string;
  color: string;
  icon: string;
  features: string[];
}

const energyServices: EnergyService[] = [
  {
    id: 'maintenance',
    title: 'GES Bakım & Onarım',
    description: 'Düzenli bakım ve arıza giderme hizmetleri',
    color: '#F3C242',
    icon: '⚙️',
    features: ['Düzenli kontrole', 'Arıza tespiti', 'Parça değişimi']
  },
  {
    id: 'drone-monitoring', 
    title: 'Drone ile Termal İzleme',
    description: 'AI destekli termal kamera ile arıza tespiti',
    color: '#009CC9',
    icon: '🚁',
    features: ['Termal görüntüleme', 'AI analizi', 'Detaylı rapor']
  }
  // ... diğer hizmetler
];
```

## 7. 📝 FORM YAPILARI

### 7.1 Robotik Kodlama Formu

**Form Adı:** "Ücretsiz Deneme Dersi Kayıt"

```typescript
interface RoboticsFormData {
  studentName: string;        // Required, min 2 char
  studentAge: number;         // Required, 6-18 range
  parentName: string;         // Required, min 2 char  
  parentEmail: string;        // Required, email format
  parentPhone: string;        // Required, Turkish format
  ageGroup: string;           // Required, select dropdown
  message?: string;           // Optional, max 500 char
}
```

**Submit Davranışı:**
- Validation: Zod schema
- Button: "Ücretsiz Deneme Başvurusu Gönder" (disabled)
- Success: Toast "Başvurunuz alındı! En kısa sürede dönüş yapacağız."

### 7.2 Havsan AI Formu

**Form Adı:** "Proje Teklifi Talebi"

```typescript
interface AIFormData {
  companyName: string;        // Required, min 2 char
  contactName: string;        // Required, min 2 char
  email: string;              // Required, email format
  phone: string;              // Required, Turkish format
  serviceType: string;        // Required, select dropdown
  projectBudget: string;      // Required, select range
  projectDescription: string;  // Required, min 20 char
  timeline: string;           // Required, select
}
```

### 7.3 Havsan Enerji Formu

**Form Adı:** "GES Hizmet Talebi"

```typescript
interface EnergyFormData {
  companyName: string;        // Required
  contactName: string;        // Required  
  email: string;              // Required
  phone: string;              // Required
  plantLocation: string;      // Required, city/district
  installedPower: string;     // Required, kW/MW
  serviceType: string[];      // Required, multiple select
  urgency: string;            // Required, select
  description: string;        // Required
}
```

## 8. 🔄 NAVIGATION FLOW

**User Journey Haritaları:**

```
Ana Akış:
Landing Page (/)
├── Preloader (2-3s) → LocalStorage check
├── Hero Section 
└── Module Cards
    ├── Click "Robotik Kodlama" → /robotik-kodlama
    │   ├── Video izleme
    │   ├── Yaş grupları inceleme  
    │   ├── Form doldurma (mock submit)
    │   └── Back Button → /
    │
    ├── Click "Havsan AI" → /yapay-zeka-yazilim
    │   ├── Hizmet kategorileri
    │   ├── Sertifika Modal açma
    │   ├── Referans carousel
    │   ├── Form doldurma (mock submit)
    │   └── Back Button → /
    │
    └── Click "Havsan Enerji" → /enerji-cozumleri  
        ├── Hizmet detayları
        ├── Form doldurma (mock submit)
        └── Back Button → /

Error Handling:
- 404 Page → "Sayfa Bulunamadı" + Ana Sayfaya Dön
- Form Validation Errors → Real-time display
- Network Errors → Toast notification
```

## 9. 🔧 NON-FUNCTIONAL REQUIREMENTS

### 9.1 Performance
- **Lighthouse Performance Score:** 90+
- **First Contentful Paint:** < 1.5s
- **Time to Interactive:** < 3.5s  
- **Bundle Size:** < 500KB initial
- **Image Optimization:** Next.js Image, WebP format
- **Code Splitting:** Route-based lazy loading

### 9.2 Accessibility (WCAG 2.1 AA)
- **Keyboard Navigation:** Full tab order support
- **Screen Reader:** ARIA labels, semantic HTML
- **Color Contrast:** 4.5:1 minimum ratio
- **Focus Management:** Visible focus indicators
- **Alt Text:** All images descriptive alt attributes
- **Form Labels:** Explicit label associations

### 9.3 SEO
- **Metadata:** Unique title/description per page
- **Open Graph:** Social sharing optimization  
- **Structured Data:** Organization, LocalBusiness schema
- **Sitemap:** Auto-generate XML sitemap
- **Robots.txt:** Search engine guidelines
- **Page Speed:** Core Web Vitals optimization

### 9.4 Browser Support
- **Chrome:** Son 2 versiyon (95%+ kullanım)
- **Firefox:** Son 2 versiyon  
- **Safari:** Son 2 versiyon
- **Edge:** Son 2 versiyon
- **Mobile:** iOS Safari 14+, Chrome Mobile 90+

## 10. 🚀 FUTURE CONSIDERATIONS (Backend Entegrasyon)

### 10.1 API Endpoint İhtiyaçları

```typescript
// Form submissions
POST /api/robotics/register     // Robotik kodlama kayıt
POST /api/ai/project-inquiry    // AI proje talebi  
POST /api/energy/service-request // Enerji hizmet talebi

// Content management
GET /api/content/videos         // Video listesi
GET /api/content/certificates   // Sertifika görselleri
GET /api/content/testimonials   // Müşteri yorumları

// Analytics
POST /api/analytics/event       // User interaction tracking
GET /api/analytics/dashboard    // Admin dashboard data
```

### 10.2 Database Schema (Gelecek)

```sql
-- Form submissions table
CREATE TABLE form_submissions (
  id UUID PRIMARY KEY,
  form_type VARCHAR(50) NOT NULL,
  data JSONB NOT NULL,
  created_at TIMESTAMP DEFAULT NOW(),
  status VARCHAR(20) DEFAULT 'pending'
);

-- Content management  
CREATE TABLE content_items (
  id UUID PRIMARY KEY,
  type VARCHAR(50) NOT NULL,
  title VARCHAR(255),
  data JSONB NOT NULL,
  is_active BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT NOW()
);
```

### 10.3 Admin Panel Requirements

- Form submission management
- Content management (videos, certificates)
- Analytics dashboard
- User inquiry tracking
- Email notification system

---

## ✅ FRONTEND DEVELOPMENT READY

Bu PRD dokümanı frontend geliştirme için tüm gerekli bilgileri içermektedir. Backend entegrasyonu ayrı bir faz olarak planlanmıştır.

**Geliştirici Notları:**
- Tüm renkler ve ölçüler Tailwind CSS utility classes ile uyumlu
- Component'ler tamamen bağımsız ve tekrar kullanılabilir  
- Mock data gerçek API response format'ında hazırlanmış
- Form validasyon kuralları production-ready
- Animasyonlar performans odaklı (60fps hedef)

**Son Güncelleme:** 29.11.2025