# Bánh Bao Mini Quảng Đông — Salepage

Sale page tĩnh cho khoá học **Bánh Bao Mini Quảng Đông** (Bao Lành Academy).

## Cấu trúc

```
.
├── index.html              # Trang chính (dùng cho production, ref ảnh .webp)
├── inputs/
│   ├── logo.webp           # Logo (đã tối ưu)
│   ├── ref/                # Ảnh sale page (cả .png/.jpg gốc và .webp tối ưu)
│   └── all-media-brand/    # Brand assets gốc (font, logo SVG, ảnh hi-res)
└── README.md
```

## Deploy lên Netlify (auto từ GitHub)

1. Vào https://app.netlify.com → **Add new site** → **Import an existing project**
2. Chọn **Deploy with GitHub** → authorise → chọn repo `banh-bao-mini-quang-dong`
3. Build settings:
   - **Base directory**: (để trống)
   - **Build command**: (để trống — site tĩnh, không cần build)
   - **Publish directory**: `.` (root)
4. **Deploy site**

Sau lần setup đầu, mỗi `git push` lên `main` Netlify sẽ tự pull + redeploy.

## Workflow chỉnh sửa

1. Sửa `index.html` trực tiếp
2. Khi thêm ảnh mới:
   - Bỏ ảnh gốc vào `inputs/ref/`
   - Convert sang webp:
     ```bash
     cwebp -q 80 -m 6 inputs/ref/ten-anh.jpg -o inputs/ref/ten-anh.webp
     ```
   - Tham chiếu trong `index.html` dùng đường dẫn `.webp`
3. Commit + push:
   ```bash
   git add .
   git commit -m "<mô tả>"
   git push
   ```

## Cài cwebp (1 lần)

```bash
brew install webp
```
