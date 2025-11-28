# Studio Alessandra Lima - Landing Page

A modern, high-conversion landing page designed for a Beauty & Wellness Studio ("Studio Alessandra Lima"). Built with **Vue.js 3** and **Tailwind CSS**, focusing on aesthetics, performance, and mobile responsiveness.

![Project Preview](https://images.unsplash.com/photo-1570172619644-dfd03ed5d881?q=80&w=2070&auto=format&fit=crop)
_(Placeholder image representing the hero section)_

## 🚀 Features

- **Modern Design**: Clean, elegant aesthetic with a "Soft Pink / Rose Gold" color palette.
- **Mobile-First**: Fully responsive layout that looks great on all devices.
- **Smooth Animations**: Subtle fade-in and scroll animations for a premium feel.
- **Sections**:
  - **Hero**: Impactful introduction with CTA.
  - **Services**: Grid of treatments with hover details.
  - **About**: Professional bio and experience highlights.
  - **Testimonials**: Social proof with client reviews.
  - **Gallery**: Visual portfolio of results.
  - **Contact**: Functional layout for booking/inquiries.
- **Performance**: Optimized build using Vite.

## 🛠️ Tech Stack

- **Framework**: [Vue.js 3](https://vuejs.org/) (Composition API + `<script setup>`)
- **Build Tool**: [Vite](https://vitejs.dev/)
- **Styling**: [Tailwind CSS v4](https://tailwindcss.com/)
- **Icons**: [Lucide Vue](https://lucide.dev/guide/packages/lucide-vue-next)

## 📦 Installation & Setup

1. **Clone the repository** (or download source):

   ```bash
   git clone <repository-url>
   cd studio-alessandra-lima
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Run development server**:

   ```bash
   npm run dev
   ```

   Access the site at `http://localhost:5173`.

4. **Build for production**:
   ```bash
   npm run build
   ```
   The output will be in the `dist` directory.

## 🎨 Customization

### Colors & Theme

The project uses CSS variables for theming, configured in `src/style.css`.
To change the color scheme, edit the `@theme` block:

```css
/* src/style.css */
@theme {
  --color-primary: #e0b0b0; /* Change this hex code */
  --color-secondary: #f5f5f5;
  --color-dark: #333333;
}
```

### Content

All content (text, images, links) is located in `src/App.vue`.

- **Navigation**: Update the `navItems` array.
- **Services**: Update the `Services Section` grid.
- **Images**: Replace `src="..."` URLs with your own images (local or remote).

## 🚀 Deployment

This project is ready for deployment on Vercel, Netlify, or any static hosting service.

**Vercel (Recommended):**

```bash
npx vercel deploy --prod
```

## 📄 License

MIT License. Feel free to use and modify for your own projects.
