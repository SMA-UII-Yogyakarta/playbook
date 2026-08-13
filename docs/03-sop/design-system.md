# SOP Design System & Storybook Development

> **Standard Operating Procedure (SOP) Pengelolaan Design System, Storybook, dan Aksesibilitas WCAG 2.1 AA SMA UII Yogyakarta**

---

## 🎯 1. Prinsip Utama Design System SMA UII

1. **Figma as Design Source of Truth:** Semua komponen harus berakar dari spesifikasi Figma SMA UII (warna, tipografi `Urbanist`/`Inter`, radius, dan elevasi bayangan).
2. **Storybook as Implementation Showcase:** Setiap komponen visual di `resources/js/Components/` wajib memiliki file story (`*.stories.tsx`) di `resources/js/stories/`.
3. **A11y & WCAG 2.1 AA Compliance:** Tidak boleh ada komponen yang gagal uji kontras warna atau navigasi keyboard pada panel `@storybook/addon-a11y`.
4. **Resilient Selectors for QA & Automation:** Semua tombol, input form, dan drawer wajib menyertakan atribut `dusk="..."` dan `data-testid="..."`.

---

## 🛠️ 2. Alur Kerja Pembuatan Komponen Baru

```
[ 1. Ambil Desain di Figma ] 
            │
            ▼
[ 2. Buat Komponen di resources/js/Components/ui/ atau common/ ]
   • Gunakan Tailwind tokens (bg-primary, text-success, dll)
   • Tambahkan dusk & data-testid attributes
            │
            ▼
[ 3. Buat Story di resources/js/stories/[Name].stories.tsx ]
   • Definisikan varian (Primary, Secondary, Outline, Danger, Loading)
            │
            ▼
[ 4. Verifikasi di Storybook & A11y Panel ]
   • bun run storybook
   • Cek tab "Accessibility" -> 0 violations
            │
            ▼
[ 5. Validasi Build & Testing ]
   • bun run build-storybook
   • bun run test
   • php artisan test
```

---

## 📖 3. Perintah Eksekusi Storybook

```bash
# Menjalankan Storybook Server (Port 6006)
bun run storybook

# Membangun Bundle Statis Storybook
bun run build-storybook
```

Dokumentasi arsitektur dan peta jalan porting multi-platform lengkap dapat dibaca pada:  
👉 **[DESIGN-SYSTEM-STORYBOOK.md](../../../../core/docs/DESIGN-SYSTEM-STORYBOOK.md)**
