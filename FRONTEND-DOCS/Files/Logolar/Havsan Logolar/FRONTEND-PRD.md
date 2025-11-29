# FRONTEND-PRD

## 1. EXECUTIVE SUMMARY

- **Proje Adı & Elevator Pitch:** Havsan Group Çok Modüllü Kurumsal Microsite, tek landing üzerinden üç iştirakın (Robotik Kodlama, Havsan AI, Havsan Enerji) hikâyesini anlatan ve preloader ile Google tarzı kart navigasyonunu vurgulayan deneyim.
- **Hedef & Stack:** Next.js 14 App Router + TypeScript + Tailwind CSS + Framer Motion + Embla Carousel (referans slider) kullanarak modüler, hızlı ve animasyon odaklı bir arayüz sağlamak; tüm içerikler CMS bağımsız mock verilerle başlatılacak.
- **Zaman Çizelgesi (1-2 Hafta):** Hafta 1 (bilgi mimarisi, tasarım sistemi, landing + preloader + kart animasyonları). Hafta 2 (modül içerikleri, formlar, referans slider, QA + Lighthouse/AXE raporları).

## 2. USER PERSONAS

### Persona 1 – Elif Arslan (Robotik Velisi)

- Demografik: 35 yaş, Elazığlı, çalışan anne, mobil ağırlıklı kullanıcı.
- Hedefler: Çocuğu için STEM odaklı güvenilir kurs bulmak, ücretsiz deneme dersine hızlı kayıt olmak.
- Pain Points: Detaylı bilgiye erişmek için uzun formlar, güncel fotoğraf/video eksikliği, iletişim kanallarına hızla ulaşamamak.
- Kullanım Senaryosu: Landing preloader sonrası Robotik kartına tıklar, yaş grubu ve deneme dersi bilgilerini okur, formu doldurup WhatsApp linkinden ek sorular sorar.

### Persona 2 – Mert Keskin (Kurumsal İK & Eğitim Satın Alıcısı)

- Demografik: 42 yaş, Ankara, teknoloji şirketinde İK müdürü, masaüstü kullanır.
- Hedefler: Havsan AI’in kurumsal yapay zeka eğitim paketlerini, Google Workspace referanslarını ve ISO danışmanlığını tek ekranda görmek.
- Pain Points: Kurumsal referans doğrulama, tek tıklamada PDF doküman indirme ihtiyacı, form gönderimi sonrası belirsizlik.
- Kullanım Senaryosu: Havsan AI kartına tıklar, hizmet gridini inceler, referans slider’dan logolara bakar, formu doldurur, başarı mesajı ile PDF linklerini indirir.

### Persona 3 – Zeynep Duran (GES Operasyon Müdürü)

- Demografik: 38 yaş, Adana, enerji santrali işletiyor, tablet kullanan saha yöneticisi.
- Hedefler: Bakım-onarım paketlerini, drone termal izleme kabiliyetini ve WhatsApp destek hattını görmek.
- Pain Points: Uzun PDF’ler, teknik terminoloji, geri dönüş süresi belirsizliği.
- Kullanım Senaryosu: Havsan Enerji kartına tıklar, hizmet kartlarından "Drone Termal İzleme"ye bakar, formu doldurur, success state sonrası +90 534 785 5957 WhatsApp linki ile görüşme başlatır.

## 3. SAYFA YAPISI

### 3.1 Landing Page

- Preloader & Intro: TemperGroup benzeri animasyon; HAVSAN yazısı üstten, Grup alttan gelir, 1 sn boyunca WhatsApp/Instagram/LinkedIn ikonları görünür, ardından fade ile kart gridine geçilir.
- Hero: Google FX tarzı üç kart (Robotik, Havsan AI, Havsan Enerji). Masaüstünde yatay, mobilde üst üste ancak scroll olmadan görünür. Hover’da renk canlanması ve çizgi animasyonu.
- Video Showcase: Kartların altında üçlü video grid; mouse hover’da önizleme oynar, YouTube Shorts embed kullanılır.
- Footer & Contact: Sosyal linkler (WhatsApp, Instagram, LinkedIn, YouTube) + tel/mail; tel linkleri tıklanabilir, alt satırda © Havsan Group.

### 3.2 Havsan Robotik Kodlama Sayfası

- Hero Section: Konum (Elazığ Ataşehir Akademi, 38.656075, 39.167103), başlık, "Ücretsiz 2 Saat Deneme" CTA, Apple font tipografi, kademeli gradient.
- Content Grid: Hedef yaş grubu, program modülleri, 3 video preview kartı, sosyal linkler ve Google Maps embed. Grid 2x2 masaüstü, 1xN mobil.
- Form: Deneme dersi formu (Bkz. Bölüm 7) sol tarafta sticky; sağ tarafta foto slider. Form valid değilse CTA kapalı.
- Back Button: Sol üstte "← Tüm Modüller" ghost butonu, focus ring ile klavye erişilebilir.

### 3.3 Havsan AI (Yapay Zeka ve Yazılım)

- Hero Section: Google ürün görselleri, Ankara/Yenimahalle koordinatları ve iframe map’i; gradient (mavi-mor-mercan).
- Content Grid: 3 sütun (Eğitimler, Google Workspace, Yazılım & Danışmanlık). Her kartta ikon, kısa açıklama, "Detay PDF" butonu. ISO sertifika görselleri alt satır carousel.
- Form: Kurumsal talep formu (Bkz. Bölüm 7) + "Google Partner" rozeti. Form submit sonrası referans slider’a scroll.
- Back Button: Sağ üstte, modül logosu yanında ghost buton.

### 3.4 Havsan Enerji

- Hero Section: Sıcak turuncu gradient, güneş paneli illüstrasyonu, "Drone Termal İzleme" highlight.
- Content Grid: 2 satır x 3 kart (Bakım, Drone Thermal, Panel Temizliği, Güç Takibi, Depolamalı GES, Yapay Zeka Destekli Arıza). Her kartta kısa KPI.
- Form: Bakım talep formu (Bkz. Bölüm 7) + "Saha Tipi" dropdown. Form success sonrası WhatsApp CTA.
- Back Button: Sol alt sticky, long-press ile haptic (mobilde).

> Varsayım: Havsan AI müşteri yorumları ve Havsan Enerji saha fotoğrafları müşteri tarafından teslim edilene kadar placeholder görsel kullanılacak.

## 4. DESIGN SYSTEM

- **Colors:** Primary #4285F4 (Google Mavi), Secondary #EA4335, Accent #FBBC05, Support #34A853, Robotik nötr #E3E5E8, AI gradient (#4E85EB → #8875D6 → #D9666F), Enerji spektrumu (#F3C242, #F99F1B, #E87D25, #EE5F26, #F15B24, #00A786, #009CC9).
- **Typography:** `SF Pro Display` (hero & sayısal veriler), `Inter` (body). Type scale: H1 48/56 bold, H2 36/44 semi-bold, H3 24/32 medium, Body 16/24 regular, Caption 14/20.
- **Components:** Button (primary filled, secondary outlined, ghost; sm/md/lg; focus ring 2px #4285F4, disabled opacity 60%). Card (elevation md, hover scale 1.02, glow border). Input (floating label, error text 12px, success icon). Modal/Drawer (AI form uses right drawer, Enerji form sticky block). Preloader (split text, 0.8s easeInOut, brand links fade). Carousel (Embla slider için referanslar, auto-play 5s, hover’da duraklar).

## 5. İNTERAKTİF ÖZELLİKLER

- Animasyonlar: Page transitions 0.3s easeInOut, scroll reveal (Framer Motion, 60px offset, 0.25s delay), hover glow + gradient shift, preloader timeline 2.5s maksimum.
- Form Validations: Email RFC 5322 regex, telefon +90 5XX XXX XX XX maskesi, required alanlarda realtime error state, consent checkbox zorunlu; submit disabled state.
- Responsive Davranış: sm (<=640) kartlar üst üste, md (768) iki kolon, lg (1024) üç kart yan yana, xl (1280) geniş boşluk + 12 kolon layout; video grid aspect 16:9, form drawers tam ekran mobilde.
- Scroll & Focus: Back to landing butonu 200px scroll sonrası görünür, klavye tab order preloader → kartlar → footer.

## 6. MOCK DATA

- Landing Videos: Havsan Robotik Shorts (OFbR8CATsVE, 4oRs3L9Gia4, 5wUXXJfoVOE) hover preview.
- Modül A Kategoriler: Lego Spike, Arduino Başlangıç, Yapay Zeka Atölyesi, 3D Yazıcı, STEAM Kampı, Mentorluk Kulübü.
- Modül B Çözümler/Sertifikalar/Referanslar: Kurumsal Yapay Zeka Eğitimi, Google Workspace Kurulum, ISO 42001, ISO 27001, KVKK Eğitimi, referans logoları (Fırat Teknokent, Google Partner, SabancıDx).
- Modül C Hizmet & Projeler: Bakım-Onarım, Drone Termal, Panel Temizliği, Güç Takibi, Depolamalı GES, Yapay Zeka Arıza; örnek projeler (Elazığ OSB Rooftop 5MW, Ankara Çankaya Depolamalı 2MW).

```ts
interface LandingVideo {
  title: string;
  youtubeId: string;
  duration: string;
  thumbnail: string;
}
interface RobotikCategory {
  name: string;
  ageRange: string;
  highlight: string;
}
interface AISolution {
  name: string;
  description: string;
  badge?: string;
}
interface AIReference {
  company: string;
  logo: string;
  url: string;
}
interface EnergyService {
  name: string;
  benefit: string;
}
interface EnergyProject {
  title: string;
  capacityMw: number;
  location: string;
  status: 'bakim' | 'devrede';
}

export const landingVideos: LandingVideo[] = [
  { title: 'Havsan Robotik Showcase 01', youtubeId: 'OFbR8CATsVE', duration: '00:37', thumbnail: '/videos/robotik-01.jpg' },
  { title: 'Öğrenci Projesi 02', youtubeId: '4oRs3L9Gia4', duration: '00:44', thumbnail: '/videos/robotik-02.jpg' },
  { title: 'Drone Yarışı 03', youtubeId: '5wUXXJfoVOE', duration: '00:41', thumbnail: '/videos/robotik-03.jpg' }
];

export const robotikCategories: RobotikCategory[] = [
  { name: 'LEGO Spike Prime', ageRange: '7-11', highlight: 'Sensörlü robotlar ile algoritma temelleri' },
  { name: 'Arduino Başlangıç', ageRange: '10-14', highlight: 'Servo kontrollü mini projeler' },
  { name: 'Yapay Zeka Atölyesi', ageRange: '12-16', highlight: 'Teachable Machine + Python giriş' },
  { name: '3D Yazıcı Laboratuvarı', ageRange: '10-16', highlight: 'CAD tasarım + baskı döngüsü' },
  { name: 'STEAM Kampı', ageRange: '8-12', highlight: 'Bilim deneyleri ve oyun tabanlı öğrenme' },
  { name: 'Mentorluk Kulübü', ageRange: '12-17', highlight: 'Uluslararası yarışma hazırlığı' }
];

export const aiSolutions: AISolution[] = [
  { name: 'Kurumsal Yapay Zeka Eğitimi', description: '40 saatlik sprint, canlı laboratuvar', badge: 'Yeni' },
  { name: 'Google Workspace Kurulum', description: 'Kurulum + eğitim + yönetim', badge: 'Google Partner' },
  { name: 'Yazılım Geliştirme', description: 'Web, mobil, özel entegrasyon' },
  { name: 'ISO 42001 Danışmanlığı', description: 'Hazırlık + audit simülasyonu' },
  { name: 'ISO 27001 Eğitimleri', description: 'Belge ve süreç danışmanlığı' },
  { name: 'KVKK Uyumluluk', description: 'Farkındalık eğitimi + roadmap' }
];

export const aiReferences: AIReference[] = [
  { company: 'Fırat Teknokent', logo: '/logos/firat.svg', url: 'https://www.firatteknokent.com' },
  { company: 'Google Partner', logo: '/logos/google-partner.svg', url: 'https://workspace.google.com' },
  { company: 'SabancıDx', logo: '/logos/sabancidx.svg', url: 'https://www.sabancidx.com' }
];

export const energyServices: EnergyService[] = [
  { name: 'GES Bakım ve Onarım', benefit: '%15 performans artışı' },
  { name: 'Drone Termal İzleme', benefit: '1 günde saha taraması' },
  { name: 'Panel Temizliği', benefit: 'Su tasarruflu robotikler' },
  { name: 'Güç Takibi', benefit: 'Canlı SCADA dashboardu' },
  { name: 'Depolamalı GES Danışmanlığı', benefit: 'Lisans süreci eşlik' },
  { name: 'Yapay Zeka Arıza Tahmini', benefit: 'Anormali alarmı < 5 dk' }
];

export const energyProjects: EnergyProject[] = [
  { title: 'Elazığ OSB Rooftop', capacityMw: 5, location: 'Elazığ', status: 'bakim' },
  { title: 'Ankara Çankaya Depolamalı', capacityMw: 2, location: 'Ankara', status: 'devrede' }
];
```

> Varsayım: Referans logolarının kesin listesi müşteri tarafından paylaşılana kadar mevcut iş ortakları (Fırat Teknokent vb.) kullanılacak.

## 7. FORM YAPILARI

### Havsan Robotik Deneme Dersi Formu

- Fields: studentName (text, min 2, required), guardianEmail (email, RFC 5322, required), guardianPhone (tel +90 5XX XXX XX XX maskesi), studentAge (number 6-16 arası), preferredSlot (select sabah/öğlen/hafta sonu), consent (checkbox KVKK).
- Validation: Realtime kontrol, telefon maskesi, yaş aralığı dışı değer uyarısı, checkbox işaretlenmeden submit kapalı.
- Submit davranışı: CTA `Deneme Dersi Planla` disabled state, mock POST /api/forms/robotic (timeout 1 s) sonrası success, hatada inline error.
- Success state: Yeşil banner + confetti animasyonu + WhatsApp derin link butonu.

### Havsan AI Kurumsal Talep Formu

- Fields: companyName, contactName, contactEmail, phone, teamSize (select 10-50, 50-200, 200+), serviceInterest (multi-select), message (textarea 500 karakter).
- Validation: Email regex + domain whitelist opsiyonu, teamSize zorunlu, message otomatik karakter sayaçlı, multi-select minimum 1.
- Submit davranışı: Drawer içinde sticky CTA, submit sonrası referans slider’a scroll, backend henüz yok → POST /api/forms/ai stub, response yoksa toast ile bilgilendirme.
- Success state: "Talebinizi aldık" mesajı + PDF linkleri (Eğitim Broşürü, Google Workspace Broşürü) + CTA "Landing’e dön".

### Havsan Enerji Bakım Talep Formu

- Fields: plantName, city, contactEmail, contactPhone, plantCapacity (MW numeric), serviceType (radio: bakım, drone, depolamalı), preferredDate (date picker), notes.
- Validation: Capacity 0.1-100 MW aralığı, tarih bugünden ileri, phone maskesi, email regex, radio zorunlu.
- Submit davranışı: Sticky form, submit disabled until valid, mock POST /api/forms/energy; offline durumunda form cached ve kullanıcıya "WhatsApp’tan devam" önerisi.
- Success state: Enerji turuncu gradientli modal, WhatsApp linki ve "Saha tipini indir" PDF aksiyonu.

## 8. NAVIGATION FLOW

```text
[Landing Grid]
      |
      v (Kart CTA)
[Modül Hero]
      |
      v (Form Bölümü)
[Submit]
      |
      v
[Success Toast] --(Back CTA)--> [Landing Grid]
```

## 9. NON-FUNCTIONAL REQUIREMENTS

- Performance: Next.js Image + font optimization, code-splitting, Lighthouse Desktop/Mobile 90+ hedefi, prefetch ile kart geçişlerinde <100ms interaktiflik.
- Accessibility: WCAG 2.1 AA, kontrast > 4.5:1, tüm butonlara aria-label, keyboard trap yok, video önizlemelerinde pause/play kontrolü.
- SEO: Semantik section/aside/article etiketleri, dinamik `<head>` meta (title 60 karakter, description 155), OpenGraph + Twitter kartları, JSON-LD ile Organization + LocalBusiness şeması.

## 10. FUTURE CONSIDERATIONS

- API uçları: POST /api/forms/robotic, POST /api/forms/ai, POST /api/forms/energy (spam koruması, rate limit); GET /api/content/modules (modül kartları), GET /api/content/references (logo slider) ile CMS entegrasyonu.
- CDN ve Cache: Video thumb’ları ve logo sprite’ları için edge cache; formlar için server actions + revalidation stratejisi.
- Analitik & A/B: Hero CTA için GA4 event’leri ve enerji formu varyasyon testi, ileride HubSpot CRM’e webhook.
