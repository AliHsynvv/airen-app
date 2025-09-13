# Airen.app - Product Requirements Document (PRD)

## 📋 Proje Özeti

**Proje Adı:** Airen.app  
**Platform:** Turizm Yapay Zekâ Influencer Sosyal Platformu  
**Teknoloji Stack:** Next.js, Supabase, TypeScript  
**Geliştirme Dili:** Türkçe/İngilizce  

## 🎯 Vizyon ve Misyon

### Vizyon
Yapay zekâ destekli kişiselleştirilmiş turizm deneyimleri sunan dünya çapında lider platform olmak.

### Misyon
Airen AI influencer aracılığıyla kullanıcılara özelleştirilmiş seyahat içerikleri, rehberlik ve topluluk deneyimi sunmak.

## 👥 Hedef Kitle

### Primer Hedef
- 25-45 yaş arası seyahat severleri
- Orta-üst gelir seviyesi
- Teknoloji savvy kullanıcılar
- Sosyal medya aktif kullanıcıları

### Sekonder Hedef
- 18-25 yaş genç seyahat severleri
- Seyahat bloggerları ve içerik üreticileri
- Turizm sektörü profesyonelleri

## 🏗️ Sistem Mimarisi

### Frontend
- **Framework:** Next.js 14 (App Router)
- **Styling:** Tailwind CSS + Shadcn/ui
- **State Management:** Zustand
- **Animation:** Framer Motion
- **Icons:** Lucide React

### Backend & Database
- **Backend:** Supabase (PostgreSQL)
- **Authentication:** Supabase Auth
- **File Storage:** Supabase Storage
- **Real-time:** Supabase Realtime

### Third-party Integrations
- **AI Avatar:** Heygen API
- **Media Management:** Cloudinary
- **Social Media:** Instagram Basic Display API
- **Analytics:** Google Analytics 4

## 📱 Ana Özellikler ve Sayfalar

### 1. Ana Sayfa (/)
```
🏠 Ana Sayfa Bileşenleri:
├── Hero Section
│   ├── Airen Avatar (Animated)
│   ├── Slogan: "Discover the World with AI"
│   └── CTA Butonları
├── Öne Çıkanlar
│   ├── Son Video (Featured)
│   ├── Trending Şehirler
│   └── Popular Articles
├── Trendler
│   ├── En Çok Okunan Şehirler
│   ├── Popüler Makaleler
│   └── Yeni Destinasyonlar
└── Hızlı Erişim
    ├── Son Haberler
    ├── Podcast Links
    └── Kısa Video Gallery
```

### 2. Haberler & Makaleler (/news, /articles)
```
🌍 İçerik Kategorileri:
├── Dünya Haberleri
├── Şehir Makaleleri
│   ├── "Bakü 48 saatte"
│   ├── "İstanbul'un gizli hazineleri"
│   └── Diğer şehir rehberleri
├── Kültür & Yemek
├── Trend Konular
│   ├── Vize Bilgileri
│   ├── Yeni Destinasyonlar
│   └── Seyahat Teknolojileri
└── Airen Insight
    ├── AI Analitik Notlar
    ├── "En iyi yaz şehirleri"
    └── "Bütçe dostu ipuçları"
```

### 3. Medya Hub (/media)
```
🎥 Medya İçerikleri:
├── Airen Vlogları
│   ├── Şehir Sunumları (Paris, Dubai, Bakü)
│   ├── Video Player Component
│   └── Related Videos
└── Airen Talks (Podcast)
    ├── Podcast Episodes
    ├── Audio Player
    └── Episode Transcripts
```

### 4. Etkileşim (/interaction)
```
📱 Etkileşim Özellikleri:
├── Airen Canlı Avatar
│   ├── Heygen Embed
│   ├── Chat Interface
│   └── Voice Responses
└── Sosyal Medya Akışı
    ├── Instagram Feed
    ├── Auto-sync Posts
    └── Engagement Metrics
```

### 5. Ülke Sayfaları (/countries/[country])
```
🌍 Ülke Bilgi Şablonu:
├── Header (Bayrak + Ülke Adı)
├── Genel Bilgiler
├── Vize & Seyahat Kuralları
├── Kültür & Tarih
├── Yemek & İçecekler
├── En Çok Ziyaret Edilen 5 Yer
├── Airen'in Tavsiyesi (Video)
├── Kullanıcı Hikayeleri
└── Geri Bildirim Bölümü
```

### 6. Kullanıcı Katılımı (/community)
```
📝 Topluluk Özellikleri:
├── Geri Bildirim Sistemi
│   ├── Upvote/Downvote
│   ├── Comment System
│   └── Rating System
├── Hikayeni Paylaş
│   ├── Photo Upload
│   ├── Story Submission
│   └── Community Approval
└── Topluluk Duvarı
    ├── All User Content
    ├── Community Highlights
    └── Q&A Section
```

### 7. Admin Panel (/admin)
```
👩‍💻 Admin Özellikleri:
├── Dashboard & Analytics
├── Content Management
│   ├── News & Articles CRUD
│   ├── Media Management
│   └── Country Pages
├── User Management
│   ├── User Profiles
│   ├── Comment Moderation
│   └── Story Approval
└── System Settings
    ├── Site Configuration
    ├── API Settings
    └── Backup Management
```

## 🗄️ Database Schema (Supabase)

### Core Tables
```sql
-- Users (extends Supabase auth.users)
users_profiles (
  id UUID PRIMARY KEY,
  username VARCHAR UNIQUE,
  full_name VARCHAR,
  avatar_url VARCHAR,
  bio TEXT,
  location VARCHAR,
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- Articles & News
articles (
  id UUID PRIMARY KEY,
  title VARCHAR NOT NULL,
  slug VARCHAR UNIQUE,
  content TEXT,
  excerpt TEXT,
  featured_image VARCHAR,
  category VARCHAR,
  tags VARCHAR[],
  author_id UUID REFERENCES users_profiles(id),
  status VARCHAR DEFAULT 'draft',
  published_at TIMESTAMP,
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- Countries
countries (
  id UUID PRIMARY KEY,
  name VARCHAR NOT NULL,
  slug VARCHAR UNIQUE,
  flag_icon VARCHAR,
  capital VARCHAR,
  population BIGINT,
  official_language VARCHAR,
  currency VARCHAR,
  timezone VARCHAR,
  visa_info TEXT,
  culture_info TEXT,
  food_info TEXT,
  top_places JSONB,
  airen_advice TEXT,
  airen_video_url VARCHAR,
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- Media (Videos & Podcasts)
media (
  id UUID PRIMARY KEY,
  title VARCHAR NOT NULL,
  description TEXT,
  type VARCHAR, -- 'video' | 'podcast'
  url VARCHAR,
  thumbnail VARCHAR,
  duration INTEGER,
  category VARCHAR,
  tags VARCHAR[],
  view_count BIGINT DEFAULT 0,
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- Comments
comments (
  id UUID PRIMARY KEY,
  content TEXT NOT NULL,
  user_id UUID REFERENCES users_profiles(id),
  article_id UUID REFERENCES articles(id),
  parent_id UUID REFERENCES comments(id),
  upvotes INTEGER DEFAULT 0,
  downvotes INTEGER DEFAULT 0,
  status VARCHAR DEFAULT 'approved',
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- User Stories
user_stories (
  id UUID PRIMARY KEY,
  title VARCHAR NOT NULL,
  content TEXT,
  image_url VARCHAR,
  location VARCHAR,
  user_id UUID REFERENCES users_profiles(id),
  category VARCHAR,
  status VARCHAR DEFAULT 'pending', -- pending | approved | rejected
  likes_count INTEGER DEFAULT 0,
  created_at TIMESTAMP,
  updated_at TIMESTAMP
)

-- Social Media Posts (Instagram sync)
social_posts (
  id UUID PRIMARY KEY,
  platform VARCHAR, -- 'instagram'
  external_id VARCHAR UNIQUE,
  content TEXT,
  image_url VARCHAR,
  post_url VARCHAR,
  engagement_count INTEGER,
  posted_at TIMESTAMP,
  synced_at TIMESTAMP
)
```

## 🚀 Development Phases

### Phase 1: Foundation & Setup (Week 1-2)
- [ ] Next.js 14 project setup
- [ ] Supabase project configuration
- [ ] Database schema creation
- [ ] Basic authentication system
- [ ] Project structure and routing

### Phase 2: Core Pages (Week 3-4)
- [ ] Ana sayfa (Hero + Öne çıkanlar)
- [ ] Haberler & Makaleler sayfası
- [ ] Article detail pages
- [ ] Basic navigation and layout

### Phase 3: Media & Interaction (Week 5-6)
- [ ] Video & Podcast hub
- [ ] Heygen AI avatar integration
- [ ] Social media feed integration
- [ ] Media player components

### Phase 4: User Features (Week 7-8)
- [ ] User registration/login
- [ ] Comment system
- [ ] User stories submission
- [ ] Community wall
- [ ] Upvote/downvote system

### Phase 5: Admin & Advanced (Week 9-10)
- [ ] Admin panel
- [ ] Content management system
- [ ] User management
- [ ] Analytics dashboard
- [ ] Performance optimization

### Phase 6: Country Pages & Polish (Week 11-12)
- [ ] Dynamic country pages
- [ ] Country template system
- [ ] Final UI/UX polish
- [ ] Testing and bug fixes
- [ ] Deployment optimization

## 🔧 Technical Requirements

### Performance
- Core Web Vitals optimization
- Image optimization (Next.js Image)
- Lazy loading for media content
- CDN integration for static assets

### SEO
- Meta tags optimization
- Structured data (JSON-LD)
- Sitemap generation
- Open Graph tags

### Security
- Row Level Security (Supabase)
- Input validation and sanitization
- Rate limiting
- CORS configuration

### Accessibility
- WCAG 2.1 AA compliance
- Keyboard navigation
- Screen reader support
- Color contrast optimization

## 📊 Success Metrics

### User Engagement
- Monthly Active Users (MAU)
- Session duration
- Page views per session
- Comment and interaction rates

### Content Metrics
- Article read completion rate
- Video watch time
- Podcast listen duration
- User-generated content submissions

### Technical Metrics
- Page load speed < 3s
- Core Web Vitals scores
- Error rate < 1%
- 99.9% uptime

## 🎨 Design System

### Color Palette
```css
:root {
  /* Primary Colors */
  --primary-blue: #3B82F6;
  --primary-dark: #1E40AF;
  --primary-light: #DBEAFE;
  
  /* Secondary Colors */
  --secondary-orange: #F59E0B;
  --secondary-green: #10B981;
  --secondary-purple: #8B5CF6;
  
  /* Neutral Colors */
  --gray-900: #111827;
  --gray-800: #1F2937;
  --gray-700: #374151;
  --gray-600: #4B5563;
  --gray-500: #6B7280;
  --gray-400: #9CA3AF;
  --gray-300: #D1D5DB;
  --gray-200: #E5E7EB;
  --gray-100: #F3F4F6;
  --gray-50: #F9FAFB;
  
  /* Background */
  --bg-primary: #FFFFFF;
  --bg-secondary: #F8FAFC;
  --bg-accent: #F1F5F9;
}
```

### Typography
- **Headings:** Inter (700, 600, 500)
- **Body:** Inter (400, 500)
- **Code:** JetBrains Mono

### Components
- Consistent spacing system (4px base)
- Rounded corners (4px, 8px, 12px)
- Shadow system (sm, md, lg, xl)
- Animation durations (150ms, 200ms, 300ms)

## 📅 Milestone Timeline

| Milestone | Week | Deliverables |
|-----------|------|--------------|
| Project Setup | 1-2 | Foundation, Auth, Basic Structure |
| Core Features | 3-4 | Home Page, Articles, Navigation |
| Media Integration | 5-6 | Video Hub, AI Avatar, Social Feed |
| User Features | 7-8 | Comments, Stories, Community |
| Admin System | 9-10 | CMS, User Management, Analytics |
| Final Polish | 11-12 | Country Pages, Testing, Deployment |

---

**Proje Başlangıç Tarihi:** [Bugünün Tarihi]  
**Tahmini Tamamlanma:** 12 hafta  
**Proje Durumu:** Planning & Setup Phase

Bu PRD, Airen.app projesinin kapsamlı bir kılavuzu olarak hazırlanmıştır ve geliştirme sürecinde referans alınacaktır.
