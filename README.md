# Blog tối giản

Blog tĩnh, không backend, không build step. Bài viết là file Markdown.

## Cấu trúc

```
blog/
├── index.html          # Toàn bộ trang (HTML + CSS + JS)
└── posts/
    ├── posts.json      # Danh sách bài viết
    └── *.md            # Nội dung bài viết
```

## Thêm bài viết mới

1. Tạo file `.md` trong `posts/` (ví dụ `bai-moi.md`)
2. Thêm entry vào `posts/posts.json`:

```json
{
  "slug": "bai-moi",
  "file": "bai-moi.md",
  "title": "Tiêu đề",
  "date": "2026-07-06",
  "tags": ["tag1"],
  "description": "Mô tả ngắn."
}
```

Bài viết tự động sắp xếp theo ngày mới nhất.

## Chạy thử local

Trang cần chạy qua HTTP (không mở trực tiếp file `index.html`):

```bash
cd blog
python3 -m http.server 8000
# Mở http://localhost:8000
```

## Deploy miễn phí lên GitHub Pages

```bash
cd blog
git init && git add . && git commit -m "init blog"
# Tạo repo trên GitHub tên <username>.github.io rồi:
git remote add origin https://github.com/<username>/<username>.github.io.git
git push -u origin main
```

Vào Settings → Pages → chọn branch `main`. Trang sẽ có tại `https://<username>.github.io`.

Các lựa chọn khác: Netlify, Vercel, Cloudflare Pages — chỉ cần kéo thả thư mục `blog/`.

## Tùy chỉnh

- Đổi tên/tiêu đề: sửa `Gavin` và `<title>` trong `index.html`
- Đổi font, màu, độ rộng: sửa biến CSS trong `:root` ở đầu `index.html`
# simple-blog
