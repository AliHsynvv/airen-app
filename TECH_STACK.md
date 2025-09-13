# Airen.app - Technology Stack Documentation

## 🛠️ Core Technologies

### Frontend Framework
**Next.js 14 (App Router)**
- **Versiyon:** 14.0.0+
- **Neden seçildi:**
  - Server-side rendering (SSR) ve static generation (SSG)
  - App Router ile modern routing sistemi
  - Built-in optimization (images, fonts, scripts)
  - API routes ile backend functionality
  - Excellent developer experience

### UI & Styling
**Tailwind CSS + Shadcn/ui**
- **Tailwind CSS:** Utility-first CSS framework
- **Shadcn/ui:** Radix UI tabanlı component library
- **Framer Motion:** Animations ve micro-interactions
- **Lucide React:** Modern icon library
- **@tailwindcss/typography:** Rich content styling

### State Management
**Zustand**
- Hafif ve performanslı state management
- TypeScript desteği
- React hooks pattern
- Minimal boilerplate

### Backend & Database
**Supabase**
- **PostgreSQL:** Production-ready database
- **Authentication:** Built-in auth system
- **Real-time:** WebSocket connections
- **Storage:** File upload ve management
- **Edge Functions:** Serverless functions
- **Row Level Security (RLS):** Database güvenliği

### Programming Language
**TypeScript**
- Type safety ve developer experience
- Better IDE support
- Compile-time error detection
- Enhanced code documentation

## 🔌 Third-party Integrations

### AI & Interactive Features
**Heygen API**
- AI avatar generation ve interaction
- Real-time conversation capabilities
- Custom avatar training
- Voice synthesis

### Social Media
**Instagram Basic Display API**
- Instagram posts synchronization
- User media access
- Engagement metrics
- Auto-content sync

### Media Management
**Cloudinary**
- Image/video optimization
- Automatic format conversion
- CDN delivery
- Responsive images
- Media transformations

### Analytics & Monitoring
**Google Analytics 4**
- User behavior tracking
- Conversion tracking
- Custom events
- Performance monitoring

## 📦 Package Dependencies

### Production Dependencies

#### Core Framework
```json
{
  "next": "^14.0.0",
  "react": "^18.2.0",
  "react-dom": "^18.2.0",
  "typescript": "^5.2.2"
}
```

#### Database & Authentication
```json
{
  "@supabase/supabase-js": "^2.38.4",
  "@supabase/auth-helpers-nextjs": "^0.8.7",
  "@supabase/auth-helpers-react": "^0.4.2"
}
```

#### UI & Styling
```json
{
  "tailwindcss": "^3.3.6",
  "@tailwindcss/forms": "^0.5.7",
  "@tailwindcss/typography": "^0.5.10",
  "clsx": "^2.0.0",
  "tailwind-merge": "^2.0.0",
  "class-variance-authority": "^0.7.0"
}
```

#### UI Components (Radix UI)
```json
{
  "@radix-ui/react-avatar": "^1.0.4",
  "@radix-ui/react-button": "^0.1.0",
  "@radix-ui/react-card": "^0.1.0",
  "@radix-ui/react-dialog": "^1.0.5",
  "@radix-ui/react-dropdown-menu": "^2.0.6",
  "@radix-ui/react-form": "^0.0.3",
  "@radix-ui/react-toast": "^1.1.5",
  "@radix-ui/react-select": "^2.0.0",
  "@radix-ui/react-textarea": "^1.0.4",
  "@radix-ui/react-label": "^2.0.2",
  "@radix-ui/react-switch": "^1.0.3",
  "@radix-ui/react-tabs": "^1.0.4",
  "@radix-ui/react-tooltip": "^1.0.7"
}
```

#### Icons & Media
```json
{
  "lucide-react": "^0.291.0",
  "react-player": "^2.13.0",
  "react-intersection-observer": "^9.5.2"
}
```

#### State Management & Forms
```json
{
  "zustand": "^4.4.6",
  "react-hook-form": "^7.47.0",
  "@hookform/resolvers": "^3.3.2",
  "zod": "^3.22.4"
}
```

#### Animations
```json
{
  "framer-motion": "^10.16.4"
}
```

#### Utilities & Date Handling
```json
{
  "date-fns": "^2.30.0",
  "slugify": "^1.6.6",
  "sharp": "^0.32.6"
}
```

#### Rich Text Editor
```json
{
  "@tiptap/react": "^2.1.13",
  "@tiptap/starter-kit": "^2.1.13",
  "@tiptap/extension-placeholder": "^2.1.13",
  "@tiptap/extension-image": "^2.1.13"
}
```

### Development Dependencies

#### TypeScript & Linting
```json
{
  "@types/node": "^20.8.10",
  "@types/react": "^18.2.37",
  "@types/react-dom": "^18.2.15",
  "eslint": "^8.52.0",
  "eslint-config-next": "^14.0.0",
  "@typescript-eslint/eslint-plugin": "^6.9.1",
  "@typescript-eslint/parser": "^6.9.1"
}
```

#### Code Formatting
```json
{
  "prettier": "^3.0.3",
  "prettier-plugin-tailwindcss": "^0.5.6"
}
```

#### Build Tools
```json
{
  "autoprefixer": "^10.4.16",
  "postcss": "^8.4.31"
}
```

#### Testing (Optional)
```json
{
  "jest": "^29.7.0",
  "jest-environment-jsdom": "^29.7.0",
  "@testing-library/react": "^13.4.0",
  "@testing-library/jest-dom": "^6.1.4",
  "@types/jest": "^29.5.7"
}
```

#### Development Tools
```json
{
  "supabase": "^1.100.0"
}
```

## ⚙️ Configuration Files

### Next.js Configuration (`next.config.js`)
```javascript
/** @type {import('next').NextConfig} */
const nextConfig = {
  experimental: {
    appDir: true,
  },
  images: {
    remotePatterns: [
      {
        protocol: 'https',
        hostname: '**.supabase.co',
      },
      {
        protocol: 'https',
        hostname: 'res.cloudinary.com',
      },
      {
        protocol: 'https',
        hostname: 'scontent.cdninstagram.com',
      }
    ],
  },
  env: {
    CUSTOM_KEY: process.env.CUSTOM_KEY,
  }
}

module.exports = nextConfig
```

### Tailwind CSS Configuration (`tailwind.config.js`)
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  darkMode: ["class"],
  content: [
    './pages/**/*.{ts,tsx}',
    './components/**/*.{ts,tsx}',
    './app/**/*.{ts,tsx}',
    './src/**/*.{ts,tsx}',
  ],
  theme: {
    container: {
      center: true,
      padding: "2rem",
      screens: {
        "2xl": "1400px",
      },
    },
    extend: {
      colors: {
        border: "hsl(var(--border))",
        input: "hsl(var(--input))",
        ring: "hsl(var(--ring))",
        background: "hsl(var(--background))",
        foreground: "hsl(var(--foreground))",
        primary: {
          DEFAULT: "hsl(var(--primary))",
          foreground: "hsl(var(--primary-foreground))",
        },
        secondary: {
          DEFAULT: "hsl(var(--secondary))",
          foreground: "hsl(var(--secondary-foreground))",
        },
        destructive: {
          DEFAULT: "hsl(var(--destructive))",
          foreground: "hsl(var(--destructive-foreground))",
        },
        muted: {
          DEFAULT: "hsl(var(--muted))",
          foreground: "hsl(var(--muted-foreground))",
        },
        accent: {
          DEFAULT: "hsl(var(--accent))",
          foreground: "hsl(var(--accent-foreground))",
        },
        popover: {
          DEFAULT: "hsl(var(--popover))",
          foreground: "hsl(var(--popover-foreground))",
        },
        card: {
          DEFAULT: "hsl(var(--card))",
          foreground: "hsl(var(--card-foreground))",
        },
        airen: {
          blue: '#3B82F6',
          orange: '#F59E0B',
          green: '#10B981',
          purple: '#8B5CF6',
        }
      },
      borderRadius: {
        lg: "var(--radius)",
        md: "calc(var(--radius) - 2px)",
        sm: "calc(var(--radius) - 4px)",
      },
      keyframes: {
        "accordion-down": {
          from: { height: 0 },
          to: { height: "var(--radix-accordion-content-height)" },
        },
        "accordion-up": {
          from: { height: "var(--radix-accordion-content-height)" },
          to: { height: 0 },
        },
        "fade-in": {
          from: { opacity: 0 },
          to: { opacity: 1 },
        },
        "slide-in": {
          from: { transform: "translateY(20px)", opacity: 0 },
          to: { transform: "translateY(0)", opacity: 1 },
        }
      },
      animation: {
        "accordion-down": "accordion-down 0.2s ease-out",
        "accordion-up": "accordion-up 0.2s ease-out",
        "fade-in": "fade-in 0.3s ease-out",
        "slide-in": "slide-in 0.4s ease-out",
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        mono: ['JetBrains Mono', 'monospace'],
      }
    },
  },
  plugins: [
    require("tailwindcss-animate"),
    require("@tailwindcss/forms"),
    require("@tailwindcss/typography")
  ],
}
```

### TypeScript Configuration (`tsconfig.json`)
```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["dom", "dom.iterable", "es6"],
    "allowJs": true,
    "skipLibCheck": true,
    "strict": true,
    "noEmit": true,
    "esModuleInterop": true,
    "module": "esnext",
    "moduleResolution": "bundler",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "jsx": "preserve",
    "incremental": true,
    "plugins": [
      {
        "name": "next"
      }
    ],
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"],
      "@/components/*": ["./src/components/*"],
      "@/lib/*": ["./src/lib/*"],
      "@/types/*": ["./src/types/*"],
      "@/app/*": ["./src/app/*"]
    }
  },
  "include": [
    "next-env.d.ts", 
    "**/*.ts", 
    "**/*.tsx", 
    ".next/types/**/*.ts"
  ],
  "exclude": ["node_modules"]
}
```

### ESLint Configuration (`.eslintrc.json`)
```json
{
  "extends": [
    "next/core-web-vitals",
    "@typescript-eslint/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "rules": {
    "@typescript-eslint/no-unused-vars": "error",
    "@typescript-eslint/no-explicit-any": "warn",
    "prefer-const": "error",
    "no-var": "error"
  },
  "ignorePatterns": ["node_modules/", ".next/", "out/"]
}
```

### Prettier Configuration (`.prettierrc`)
```json
{
  "semi": false,
  "trailingComma": "es5",
  "singleQuote": true,
  "tabWidth": 2,
  "useTabs": false,
  "printWidth": 80,
  "bracketSpacing": true,
  "arrowParens": "avoid",
  "endOfLine": "lf",
  "plugins": ["prettier-plugin-tailwindcss"]
}
```

## 🌍 Environment Variables

### Required Environment Variables
```env
# Supabase Configuration
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key

# Authentication
NEXTAUTH_SECRET=your-nextauth-secret
NEXTAUTH_URL=http://localhost:3000

# Heygen API (AI Avatar)
HEYGEN_API_KEY=your-heygen-api-key
NEXT_PUBLIC_HEYGEN_AVATAR_ID=your-avatar-id

# Social Media APIs
INSTAGRAM_ACCESS_TOKEN=your-instagram-token
INSTAGRAM_APP_ID=your-instagram-app-id
INSTAGRAM_APP_SECRET=your-instagram-app-secret

# Cloudinary (Media Management)
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

# Google Analytics
NEXT_PUBLIC_GA_MEASUREMENT_ID=your-ga-measurement-id

# Email Services (Optional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
```

### Optional Environment Variables
```env
# Development
NODE_ENV=development
ANALYZE=false

# Rate Limiting
RATE_LIMIT_MAX=100

# File Upload Limits
MAX_FILE_SIZE=10485760 # 10MB

# Redis (for caching - optional)
REDIS_URL=redis://localhost:6379

# Sentry (Error monitoring - optional)
SENTRY_DSN=your-sentry-dsn
```

## 🚀 Performance Optimizations

### Next.js Optimizations
- **Image Optimization:** next/image component
- **Font Optimization:** next/font
- **Script Optimization:** next/script
- **Bundle Analysis:** @next/bundle-analyzer
- **Compression:** Built-in gzip compression

### Database Optimizations
- **Connection Pooling:** Supabase built-in
- **Query Optimization:** Proper indexing
- **Caching Strategy:** React Query + Supabase cache
- **Real-time Subscriptions:** Optimized listeners

### Frontend Optimizations
- **Code Splitting:** Next.js automatic splitting
- **Lazy Loading:** React.lazy ve Suspense
- **Virtual Scrolling:** react-window (büyük listeler için)
- **Memoization:** React.memo, useMemo, useCallback

## 🔒 Security Measures

### Authentication & Authorization
- **Row Level Security (RLS):** Database level security
- **JWT Tokens:** Secure authentication
- **Role-based Access:** Admin/User/Moderator roles
- **Session Management:** Supabase Auth

### Data Protection
- **Input Validation:** Zod schemas
- **SQL Injection Protection:** Parameterized queries
- **XSS Protection:** Content sanitization
- **CSRF Protection:** Next.js built-in

### API Security
- **Rate Limiting:** API route protection
- **CORS Configuration:** Proper domain restrictions
- **API Key Management:** Environment variables
- **Secure Headers:** Next.js security headers

Bu teknoloji stack, Airen.app projesinin modern, ölçeklenebilir ve performanslı bir şekilde geliştirilmesi için optimize edilmiştir.
