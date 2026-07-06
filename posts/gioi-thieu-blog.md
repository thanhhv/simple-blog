# Chào mừng đến blog của tôi

Đây là bài viết đầu tiên. Blog này được xây dựng theo phong cách **tối giản**: không backend, không framework, không build step — chỉ HTML, CSS và một chút JavaScript.

## Cách hoạt động

Mỗi bài viết là một file Markdown trong thư mục `posts/`. Trình duyệt tải file `.md` và render bằng thư viện [marked](https://marked.js.org/).

Để thêm bài viết mới:

1. Tạo file `.md` trong thư mục `posts/`
2. Thêm một entry vào `posts/posts.json`:

```json
{
  "slug": "bai-viet-moi",
  "file": "bai-viet-moi.md",
  "title": "Tiêu đề bài viết",
  "date": "2026-07-06",
  "tags": ["tag1", "tag2"],
  "description": "Mô tả ngắn hiển thị ở trang chủ."
}
```

Xong. Không cần build, không cần deploy lại gì phức tạp.

## Ví dụ code block

```python
def hello(name: str) -> str:
    return f"Xin chào, {name}!"

print(hello("thế giới"))
```

> Trích dẫn cũng được hỗ trợ, cùng với bảng, danh sách, và mọi cú pháp Markdown chuẩn.

Cảm ơn bạn đã ghé thăm!
