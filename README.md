<!-- Header -->
<div align="center">

# 🌍 Hello, World! - Next.js App

Một website đơn giản và hiện đại được xây dựng bằng **Next.js 14** với **App Router** và **CSS thuần**.

![Next.js](https://img.shields.io/badge/Next.js-14+-black?logo=next.js)
![React](https://img.shields.io/badge/React-18+-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5+-blue?logo=typescript)
![CSS3](https://img.shields.io/badge/CSS-3-blue?logo=css3)

</div>

---

## 📋 Mục lục

- [✨ Tính năng](#-tính-năng)
- [📂 Cấu trúc dự án](#-cấu-trúc-dự-án)
- [📦 Cài đặt](#-cài-đặt)
- [🚀 Khởi động](#-khởi-động)
- [📖 Giải thích từng file](#-giải-thích-từng-file)
- [🎨 Styling](#-styling)
- [📱 Responsive Design](#-responsive-design)
- [🌐 Dark Mode](#-dark-mode)
- [🔧 Build cho Production](#-build-cho-production)

---

## ✨ Tính năng

✅ **Next.js 14** với App Router (thư mục `app/`)  
✅ **TypeScript** để tăng tính bảo mật loại (type safety)  
✅ **CSS Thuần** (không dùng Tailwind hay CSS-in-JS)  
✅ **CSS Variables** cho dễ dàng tùy chỉnh  
✅ **Responsive Design** - tương thích mobile, tablet, desktop  
✅ **Dark Mode Support** - hỗ trợ chế độ tối  
✅ **Accessibility** - tôn trọng cài đặt animation của người dùng  
✅ **Animations** - Fade-in effect khi tải trang  
✅ **SEO Optimized** - Metadata được cấu hình sẵn  

---

## 📂 Cấu trúc dự án

```
Hello-World/
├── app/
│   ├── globals.css          # CSS toàn cục
│   ├── layout.tsx           # Root layout component
│   └── page.tsx             # Trang chủ (/)
├── package.json             # Dependencies và scripts
├── next.config.js           # Cấu hình Next.js
├── tsconfig.json            # Cấu hình TypeScript
├── .gitignore               # Git ignore patterns
└── README.md                # File này
```

---

## 📦 Cài đặt

### Yêu cầu
- **Node.js** 16.8+ hoặc cao hơn
- **npm**, **yarn**, hoặc **pnpm**

### Các bước cài đặt

1. **Clone repository** (nếu chưa có):
   ```bash
   git clone https://github.com/uruchimangu/Hello-World.git
   cd Hello-World
   ```

2. **Cài đặt dependencies**:
   ```bash
   npm install
   # hoặc
   yarn install
   # hoặc
   pnpm install
   ```

---

## 🚀 Khởi động

### Chế độ development (phát triển)
Chạy ứng dụng ở chế độ phát triển với hot-reload:
```bash
npm run dev
```

Sau đó, mở trình duyệt và truy cập:
```
http://localhost:3000
```

### Xem thay đổi
- Mỗi khi bạn thay đổi file `.tsx`, `.css`, etc., trang sẽ tự động cập nhật.
- Mở **DevTools** (F12) để xem console và inspect CSS.

---

## 📖 Giải thích từng file

### 📄 `package.json`
```json
{
  "name": "hello-world-nextjs",
  "scripts": {
    "dev": "next dev",              // Chạy server dev
    "build": "next build",          // Build cho production
    "start": "next start",          // Chạy production build
    "lint": "next lint"             // Check linting
  },
  "dependencies": {
    "next": "^14.0.0",              // Framework Next.js
    "react": "^18.2.0",             // React library
    "react-dom": "^18.2.0"          // React DOM
  }
}
```

**Giải thích:**
- `dev` script dùng để chạy server phát triển
- `build` script biên dịch ứng dụng cho sản xuất
- `dependencies` chứa các thư viện cần thiết

---

### ⚙️ `next.config.js`
```javascript
const nextConfig = {
  reactStrictMode: true,  // Kiểm tra lỗi React ở development
};
module.exports = nextConfig;
```

**Giải thích:**
- Cấu hình Next.js
- `reactStrictMode` giúp phát hiện vấn đề tiềm ẩn

---

### 🔧 `tsconfig.json`
```json
{
  "compilerOptions": {
    "target": "es2020",           // Target JavaScript version
    "jsx": "react-jsx",           // Sử dụng JSX transform mới
    "strict": true,               // Bật tất cả kiểm tra type
    "baseUrl": ".",               // Base path cho imports
    "paths": {
      "@/*": ["./*"]              // Path alias @ = root
    }
  }
}
```

**Giải thích:**
- Cấu hình TypeScript compiler
- `strict: true` bắt buộc type-checking nghiêm ngặt
- Path alias `@/*` cho phép import sạch hơn

---

### 🎨 `app/globals.css`
Tệp CSS chính chứa:

**CSS Variables (Biến CSS):**
```css
:root {
  --color-primary: #1a73e8;       /* Màu xanh chính */
  --color-background: #ffffff;    /* Nền trắng */
  --color-text: #202124;          /* Chữ đen */
  --font-size-large: 48px;        /* Font lớn */
}
```

**Styling:**
- Reset CSS cơ bản
- Kiểu cho `h1`, `p`, `button`
- Animations (fade-in)
- Dark mode support

**Responsive:**
- Tablet: 768px trở xuống
- Mobile: 480px trở xuống

**Accessibility:**
- `prefers-reduced-motion`: Tôn trọng cài đặt animation của OS
- `prefers-color-scheme`: Hỗ trợ dark mode

---

### 📐 `app/layout.tsx`
```typescript
export const metadata: Metadata = {
  title: 'Hello, World! - Next.js App',
  description: 'A simple Hello World website built with Next.js',
};

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="vi">
      <body>{children}</body>
    </html>
  );
}
```

**Giải thích:**
- `metadata`: SEO metadata cho trang
- `RootLayout`: Layout gốc bọc tất cả các trang
- `children`: Nơi các trang con được render
- `lang="vi"`: Ngôn ngữ tiếng Việt

---

### 🏠 `app/page.tsx`
```typescript
export default function Home() {
  return (
    <main>
      <h1>Hello, World! 👋</h1>
      <p>Chào mừng bạn...</p>
      <button>Nhấn vào đây</button>
    </main>
  );
}
```

**Giải thích:**
- `page.tsx` trong thư mục `app/` là trang chủ (route `/`)
- Chứa tiêu đề, mô tả, và nút CTA
- JSX được render thành HTML

---

## 🎨 Styling

### CSS Thuần (Vanilla CSS)
Dự án này sử dụng **CSS thuần**, không phụ thuộc:
- ❌ Tailwind CSS
- ❌ CSS-in-JS (styled-components, emotion)
- ✅ CSS file truyền thống (`globals.css`)

### CSS Variables
Sử dụng CSS variables để dễ tùy chỉnh:

```css
:root {
  --color-primary: #1a73e8;
  --font-size-large: 48px;
}

h1 {
  color: var(--color-primary);
  font-size: var(--font-size-large);
}
```

### Cách thay đổi màu sắc
1. Mở `app/globals.css`
2. Tìm section `:root { ... }`
3. Thay đổi giá trị màu:
   ```css
   :root {
     --color-primary: #FF5733;  /* Đổi thành đỏ cam */
   }
   ```
4. Lưu file và trang sẽ cập nhật tự động

---

## 📱 Responsive Design

Trang web tự động điều chỉnh trên các kích thước màn hình:

| Thiết bị | Kích thước | Font size | Padding |
|---------|----------|-----------|---------|
| Desktop | > 768px  | 48px      | 32px    |
| Tablet  | 481-768px| 36px      | 16px    |
| Mobile  | ≤ 480px  | 28px      | 8px     |

**Test responsive:**
1. Mở DevTools (F12)
2. Nhấn Ctrl+Shift+M (hoặc Cmd+Shift+M trên Mac)
3. Thay đổi kích thước màn hình để thử nghiệm

---

## 🌐 Dark Mode

Trang web tự động hỗ trợ chế độ tối dựa trên cài đặt hệ thống:

```css
@media (prefers-color-scheme: dark) {
  :root {
    --color-background: #202124;
    --color-text: #e8eaed;
  }
}
```

**Bật/Tắt Dark Mode:**
- **Windows/Linux**: Cài đặt > Hiển thị > Chế độ tối/sáng
- **macOS**: System Preferences > General > Appearance
- **Browser DevTools**: Nhấn F12 > Rendering > Emulate CSS media feature prefers-color-scheme

---

## 🔧 Build cho Production

### Build ứng dụng
```bash
npm run build
```

Lệnh này sẽ:
- Biên dịch TypeScript sang JavaScript
- Tối ưu hóa code
- Tạo thư mục `.next/` chứa production build

### Chạy production build
```bash
npm run start
```

Ứng dụng sẽ chạy ở chế độ production tại `http://localhost:3000`

---

## 🎯 Tiếp theo (Next Steps)

Dưới đây là những gợi ý để phát triển tiếp:

1. **Thêm Pages:**
   - Tạo `app/about/page.tsx` cho trang About
   - Tạo `app/contact/page.tsx` cho trang Contact

2. **Styling nâng cao:**
   - Thêm CSS animations phức tạp hơn
   - Tạo CSS grid/flexbox layout

3. **API Routes:**
   - Tạo `app/api/hello/route.ts` để xử lý API requests

4. **Database:**
   - Kết nối với MongoDB, PostgreSQL, etc.

5. **Deployment:**
   - Deploy lên Vercel (tự động)
   - Deploy lên Netlify, GitHub Pages (manual)

---

## 📝 License

Dự án này là miễn phí và mở cho mục đích học tập.

---

## 👨‍💻 Tác giả

Created by **uruchimangu**

---

## 💬 Hỗ trợ

Nếu bạn gặp vấn đề:

1. Kiểm tra **Node.js version**: `node --version` (phải ≥ 16.8)
2. Xóa `node_modules` và cài đặt lại: `rm -rf node_modules && npm install`
3. Xóa `.next` folder: `rm -rf .next`
4. Chạy lại: `npm run dev`

---

<div align="center">

**Happy Coding! 🚀**

</div>
