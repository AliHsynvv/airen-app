# Airen.app - Development Plan & Project Structure

## 📁 Proje Yapısı

```
airen-app/
├── README.md
├── PRD_Airen_App.md
├── DEVELOPMENT_PLAN.md
├── package.json
├── next.config.js
├── tailwind.config.js
├── tsconfig.json
├── .env.local
├── .env.example
├── .gitignore
├── 
├── public/
│   ├── images/
│   │   ├── airen-avatar/
│   │   ├── countries/
│   │   ├── articles/
│   │   └── media/
│   ├── icons/
│   ├── videos/
│   └── favicon.ico
│
├── src/
│   ├── app/ (Next.js 14 App Router)
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   ├── loading.tsx
│   │   ├── error.tsx
│   │   ├── not-found.tsx
│   │   │
│   │   ├── globals.css
│   │   │
│   │   ├── (routes)/
│   │   │   ├── news/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── [slug]/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── layout.tsx
│   │   │   │
│   │   │   ├── articles/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── [slug]/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── layout.tsx
│   │   │   │
│   │   │   ├── media/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── videos/
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── podcasts/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── layout.tsx
│   │   │   │
│   │   │   ├── countries/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── [slug]/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── layout.tsx
│   │   │   │
│   │   │   ├── community/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── stories/
│   │   │   │   │   ├── page.tsx
│   │   │   │   │   └── submit/
│   │   │   │   │       └── page.tsx
│   │   │   │   └── layout.tsx
│   │   │   │
│   │   │   ├── interaction/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── avatar/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── social/
│   │   │   │       └── page.tsx
│   │   │   │
│   │   │   ├── about/
│   │   │   │   └── page.tsx
│   │   │   │
│   │   │   ├── contact/
│   │   │   │   └── page.tsx
│   │   │   │
│   │   │   ├── auth/
│   │   │   │   ├── login/
│   │   │   │   │   └── page.tsx
│   │   │   │   ├── register/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── callback/
│   │   │   │       └── route.ts
│   │   │   │
│   │   │   └── profile/
│   │   │       ├── page.tsx
│   │   │       ├── edit/
│   │   │       │   └── page.tsx
│   │   │       └── layout.tsx
│   │   │
│   │   ├── admin/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx (Dashboard)
│   │   │   ├── articles/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── create/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── [id]/
│   │   │   │       ├── page.tsx
│   │   │   │       └── edit/
│   │   │   │           └── page.tsx
│   │   │   ├── media/
│   │   │   │   ├── page.tsx
│   │   │   │   └── upload/
│   │   │   │       └── page.tsx
│   │   │   ├── users/
│   │   │   │   ├── page.tsx
│   │   │   │   └── [id]/
│   │   │   │       └── page.tsx
│   │   │   ├── countries/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── create/
│   │   │   │   │   └── page.tsx
│   │   │   │   └── [id]/
│   │   │   │       └── edit/
│   │   │   │           └── page.tsx
│   │   │   ├── stories/
│   │   │   │   └── page.tsx
│   │   │   └── settings/
│   │   │       └── page.tsx
│   │   │
│   │   └── api/ (API Routes)
│   │       ├── auth/
│   │       │   └── callback/
│   │       │       └── route.ts
│   │       ├── articles/
│   │       │   ├── route.ts
│   │       │   └── [id]/
│   │       │       └── route.ts
│   │       ├── comments/
│   │       │   ├── route.ts
│   │       │   └── [id]/
│   │       │       └── route.ts
│   │       ├── media/
│   │       │   ├── route.ts
│   │       │   └── upload/
│   │       │       └── route.ts
│   │       ├── countries/
│   │       │   └── route.ts
│   │       ├── social/
│   │       │   └── instagram/
│   │       │       └── route.ts
│   │       ├── stories/
│   │       │   └── route.ts
│   │       └── admin/
│   │           ├── users/
│   │           │   └── route.ts
│   │           └── analytics/
│   │               └── route.ts
│   │
│   ├── components/ (React Components)
│   │   ├── ui/ (Shadcn/ui base components)
│   │   │   ├── button.tsx
│   │   │   ├── input.tsx
│   │   │   ├── card.tsx
│   │   │   ├── dialog.tsx
│   │   │   ├── dropdown-menu.tsx
│   │   │   ├── form.tsx
│   │   │   ├── toast.tsx
│   │   │   ├── avatar.tsx
│   │   │   └── ...
│   │   │
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   ├── Footer.tsx
│   │   │   ├── Sidebar.tsx
│   │   │   ├── Navigation.tsx
│   │   │   └── MobileMenu.tsx
│   │   │
│   │   ├── home/
│   │   │   ├── HeroSection.tsx
│   │   │   ├── FeaturedContent.tsx
│   │   │   ├── TrendingDestinations.tsx
│   │   │   ├── QuickAccess.tsx
│   │   │   └── CommunityHighlights.tsx
│   │   │
│   │   ├── articles/
│   │   │   ├── ArticleCard.tsx
│   │   │   ├── ArticleList.tsx
│   │   │   ├── ArticleDetail.tsx
│   │   │   ├── CategoryFilter.tsx
│   │   │   └── ArticleSearch.tsx
│   │   │
│   │   ├── media/
│   │   │   ├── VideoPlayer.tsx
│   │   │   ├── VideoCard.tsx
│   │   │   ├── VideoGrid.tsx
│   │   │   ├── PodcastPlayer.tsx
│   │   │   ├── PodcastEpisode.tsx
│   │   │   └── MediaGallery.tsx
│   │   │
│   │   ├── countries/
│   │   │   ├── CountryCard.tsx
│   │   │   ├── CountryDetail.tsx
│   │   │   ├── CountryHeader.tsx
│   │   │   ├── VisaInfo.tsx
│   │   │   ├── TopPlaces.tsx
│   │   │   └── AirenAdvice.tsx
│   │   │
│   │   ├── community/
│   │   │   ├── CommentSection.tsx
│   │   │   ├── Comment.tsx
│   │   │   ├── VoteButtons.tsx
│   │   │   ├── UserStories.tsx
│   │   │   ├── StoryCard.tsx
│   │   │   ├── StorySubmission.tsx
│   │   │   └── CommunityWall.tsx
│   │   │
│   │   ├── interaction/
│   │   │   ├── AirenAvatar.tsx
│   │   │   ├── HeygenEmbed.tsx
│   │   │   ├── ChatInterface.tsx
│   │   │   ├── SocialFeed.tsx
│   │   │   └── InstagramEmbed.tsx
│   │   │
│   │   ├── auth/
│   │   │   ├── LoginForm.tsx
│   │   │   ├── RegisterForm.tsx
│   │   │   ├── AuthButton.tsx
│   │   │   └── ProtectedRoute.tsx
│   │   │
│   │   ├── admin/
│   │   │   ├── AdminLayout.tsx
│   │   │   ├── Dashboard.tsx
│   │   │   ├── UserTable.tsx
│   │   │   ├── ArticleEditor.tsx
│   │   │   ├── MediaUpload.tsx
│   │   │   ├── Analytics.tsx
│   │   │   └── Settings.tsx
│   │   │
│   │   └── common/
│   │       ├── Loading.tsx
│   │       ├── ErrorBoundary.tsx
│   │       ├── BackButton.tsx
│   │       ├── SearchBar.tsx
│   │       ├── Pagination.tsx
│   │       ├── ShareButtons.tsx
│   │       ├── LazyImage.tsx
│   │       └── SeoMeta.tsx
│   │
│   ├── lib/ (Utilities & Configurations)
│   │   ├── supabase/
│   │   │   ├── client.ts
│   │   │   ├── server.ts
│   │   │   ├── middleware.ts
│   │   │   ├── auth.ts
│   │   │   └── database.types.ts
│   │   │
│   │   ├── api/
│   │   │   ├── articles.ts
│   │   │   ├── comments.ts
│   │   │   ├── media.ts
│   │   │   ├── countries.ts
│   │   │   ├── users.ts
│   │   │   └── social.ts
│   │   │
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useArticles.ts
│   │   │   ├── useComments.ts
│   │   │   ├── useMedia.ts
│   │   │   ├── useCountries.ts
│   │   │   └── useLocalStorage.ts
│   │   │
│   │   ├── utils/
│   │   │   ├── cn.ts (clsx + tailwind-merge)
│   │   │   ├── date.ts
│   │   │   ├── formatters.ts
│   │   │   ├── validators.ts
│   │   │   ├── constants.ts
│   │   │   ├── slugify.ts
│   │   │   └── image.ts
│   │   │
│   │   ├── stores/ (Zustand)
│   │   │   ├── authStore.ts
│   │   │   ├── articlesStore.ts
│   │   │   ├── mediaStore.ts
│   │   │   └── uiStore.ts
│   │   │
│   │   └── validations/ (Zod Schemas)
│   │       ├── auth.ts
│   │       ├── articles.ts
│   │       ├── comments.ts
│   │       ├── media.ts
│   │       └── users.ts
│   │
│   └── types/
│       ├── database.ts
│       ├── api.ts
│       ├── user.ts
│       ├── article.ts
│       ├── media.ts
│       ├── country.ts
│       └── global.ts
│
├── supabase/ (Database & Configuration)
│   ├── migrations/
│   │   ├── 001_initial_schema.sql
│   │   ├── 002_countries_table.sql
│   │   ├── 003_media_table.sql
│   │   ├── 004_comments_system.sql
│   │   ├── 005_user_stories.sql
│   │   ├── 006_social_posts.sql
│   │   └── 007_admin_features.sql
│   │
│   ├── functions/
│   │   ├── get-trending-articles/
│   │   ├── sync-instagram-posts/
│   │   ├── moderate-comments/
│   │   └── generate-analytics/
│   │
│   └── config.toml
│
├── docs/
│   ├── API.md
│   ├── DEPLOYMENT.md
│   ├── CONTRIBUTING.md
│   └── CHANGELOG.md
│
└── tests/
    ├── __mocks__/
    ├── components/
    ├── pages/
    ├── api/
    └── utils/
```

## 🚀 Detaylı Geliştirme Etapları

### Phase 1: Foundation Setup (5 gün)

#### Gün 1: Project Initialization
- [ ] Next.js 14 kurulumu (App Router)
- [ ] TypeScript konfigürasyonu
- [ ] Tailwind CSS + Shadcn/ui setup
- [ ] ESLint, Prettier konfigürasyonu
- [ ] Git repository setup

#### Gün 2: Supabase Configuration  
- [ ] Supabase projesi oluşturma
- [ ] Database connection kurma
- [ ] Authentication yapılandırması
- [ ] Environment variables setup
- [ ] Initial database schema

#### Gün 3: Basic Layout & Components
- [ ] App layout oluşturma
- [ ] Header/Footer components
- [ ] Navigation system
- [ ] Basic UI components (Button, Card, Input)
- [ ] Loading/Error states

#### Gün 4: Authentication System
- [ ] Login/Register pages
- [ ] Supabase Auth integration
- [ ] Protected routes
- [ ] User session management
- [ ] Auth middleware

#### Gün 5: Routing & Structure
- [ ] All route pages (basic)
- [ ] Dynamic routing setup
- [ ] 404 page
- [ ] Basic SEO meta tags
- [ ] Testing foundation

### Phase 2: Core Content Pages (5 gün)

#### Gün 6-7: Ana Sayfa (Home Page)
- [ ] Hero section with Airen avatar
- [ ] Featured content section
- [ ] Trending destinations
- [ ] Quick access links
- [ ] Community highlights preview
- [ ] Responsive design

#### Gün 8-9: Articles System
- [ ] Article listing page
- [ ] Article detail page
- [ ] Category filtering
- [ ] Search functionality
- [ ] Article CRUD operations
- [ ] Rich text editor (admin)

#### Gün 10: News Section
- [ ] News listing page
- [ ] News detail page
- [ ] News categories
- [ ] News admin interface
- [ ] RSS feed generation

### Phase 3: Media Hub & AI Integration (5 gün)

#### Gün 11-12: Video System
- [ ] Video listing page
- [ ] Video player component
- [ ] Video categories (Airen Vlogs)
- [ ] Video upload interface
- [ ] Video metadata management
- [ ] Video SEO optimization

#### Gün 13: Podcast System
- [ ] Podcast listing page
- [ ] Audio player component
- [ ] Episode management
- [ ] Podcast RSS feed
- [ ] Episode transcripts

#### Gün 14-15: AI Avatar Integration
- [ ] Heygen API integration
- [ ] Interactive chat interface
- [ ] Avatar embed component
- [ ] Voice response system
- [ ] Real-time interaction

### Phase 4: User Engagement Features (5 gün)

#### Gün 16-17: Comment System
- [ ] Comment display component
- [ ] Comment submission form
- [ ] Upvote/Downvote functionality
- [ ] Comment moderation
- [ ] Reply system
- [ ] Comment notifications

#### Gün 18-19: User Stories
- [ ] Story submission form
- [ ] Image upload functionality
- [ ] Story approval workflow
- [ ] Story display components
- [ ] Story categories
- [ ] Community stories page

#### Gün 20: Community Features
- [ ] Community wall
- [ ] User profiles
- [ ] Activity feed
- [ ] User achievements
- [ ] Social features

### Phase 5: Admin System (5 gün)

#### Gün 21-22: Admin Dashboard
- [ ] Admin layout
- [ ] Analytics dashboard
- [ ] User statistics
- [ ] Content statistics
- [ ] System health monitoring
- [ ] Admin authentication

#### Gün 23: Content Management
- [ ] Article management interface
- [ ] Media library
- [ ] Content approval workflow
- [ ] Bulk operations
- [ ] Content scheduling

#### Gün 24-25: User Management
- [ ] User listing and search
- [ ] User profile management
- [ ] Role-based permissions
- [ ] Comment moderation tools
- [ ] Story approval system

### Phase 6: Country Pages & Social Integration (5 gün)

#### Gün 26-27: Country System
- [ ] Country data model
- [ ] Dynamic country pages
- [ ] Country template system
- [ ] Country information forms
- [ ] Country image galleries

#### Gün 28: Social Media Integration
- [ ] Instagram API integration
- [ ] Auto-sync social posts
- [ ] Social media feed display
- [ ] Engagement metrics
- [ ] Social sharing buttons

#### Gün 29-30: Final Polish
- [ ] Performance optimization
- [ ] SEO improvements
- [ ] Accessibility features
- [ ] Mobile responsiveness
- [ ] Bug fixes and testing

## 📦 Package Dependencies

### Core Dependencies
```json
{
  "dependencies": {
    "next": "^14.0.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0",
    "typescript": "^5.0.0",
    "@supabase/supabase-js": "^2.38.0",
    "@supabase/auth-helpers-nextjs": "^0.8.0",
    "@supabase/auth-helpers-react": "^0.4.0",
    "tailwindcss": "^3.3.0",
    "@tailwindcss/forms": "^0.5.7",
    "@tailwindcss/typography": "^0.5.10",
    "clsx": "^2.0.0",
    "tailwind-merge": "^2.0.0",
    "class-variance-authority": "^0.7.0",
    "lucide-react": "^0.291.0",
    "@radix-ui/react-avatar": "^1.0.4",
    "@radix-ui/react-button": "^0.1.0",
    "@radix-ui/react-card": "^0.1.0",
    "@radix-ui/react-dialog": "^1.0.5",
    "@radix-ui/react-dropdown-menu": "^2.0.6",
    "@radix-ui/react-form": "^0.0.3",
    "@radix-ui/react-toast": "^1.1.5",
    "framer-motion": "^10.16.0",
    "zustand": "^4.4.0",
    "zod": "^3.22.0",
    "@hookform/resolvers": "^3.3.0",
    "react-hook-form": "^7.47.0",
    "date-fns": "^2.30.0",
    "@tiptap/react": "^2.1.0",
    "@tiptap/starter-kit": "^2.1.0",
    "react-player": "^2.13.0",
    "react-intersection-observer": "^9.5.0",
    "sharp": "^0.32.0"
  },
  "devDependencies": {
    "@types/node": "^20.0.0",
    "@types/react": "^18.0.0",
    "@types/react-dom": "^18.0.0",
    "eslint": "^8.0.0",
    "eslint-config-next": "^14.0.0",
    "prettier": "^3.0.0",
    "prettier-plugin-tailwindcss": "^0.5.0",
    "autoprefixer": "^10.4.0",
    "postcss": "^8.4.0",
    "@types/jest": "^29.0.0",
    "jest": "^29.0.0",
    "jest-environment-jsdom": "^29.0.0",
    "@testing-library/react": "^13.0.0",
    "@testing-library/jest-dom": "^6.0.0",
    "supabase": "^1.100.0"
  }
}
```

## 🌐 Environment Variables

```env
# .env.local
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# Heygen API
HEYGEN_API_KEY=your_heygen_api_key
NEXT_PUBLIC_HEYGEN_AVATAR_ID=your_avatar_id

# Social Media APIs
INSTAGRAM_ACCESS_TOKEN=your_instagram_token
INSTAGRAM_APP_ID=your_instagram_app_id

# Cloudinary
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Google Analytics
NEXT_PUBLIC_GA_MEASUREMENT_ID=your_ga_id

# Other
NEXTAUTH_SECRET=your_nextauth_secret
NEXTAUTH_URL=http://localhost:3000
```

## 🔄 Git Workflow

```bash
# Branch naming convention
feature/hero-section
fix/authentication-bug
hotfix/security-patch
refactor/component-structure

# Commit message format
feat: add hero section component
fix: resolve authentication redirect issue
docs: update API documentation
style: improve button component styling
refactor: optimize database queries
test: add unit tests for auth system
```

## 📝 Development Checklist

### Her Feature İçin Kontrol Listesi
- [ ] TypeScript tip güvenliği
- [ ] Responsive design (mobile-first)
- [ ] Accessibility (a11y) compliance
- [ ] SEO optimization
- [ ] Error handling
- [ ] Loading states
- [ ] Empty states
- [ ] Performance optimization
- [ ] Unit tests (önemli components için)
- [ ] Documentation

### Code Quality Standards
- [ ] ESLint rules compliance
- [ ] Prettier formatting
- [ ] Component prop validation
- [ ] Proper error boundaries
- [ ] Performance monitoring
- [ ] Bundle size optimization
- [ ] Core Web Vitals scores

Bu geliştirme planı, Airen.app projesinin sistematik ve organize bir şekilde geliştirilmesi için hazırlanmıştır.
