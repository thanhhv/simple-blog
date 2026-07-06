# Tối ưu truy vấn SQL: những điều cơ bản

Bài viết mẫu về technical để bạn xem cách hiển thị.

## Dùng EXPLAIN trước khi tối ưu

Đừng đoán. Hãy để database nói cho bạn biết nó đang làm gì:

```sql
EXPLAIN ANALYZE
SELECT u.name, COUNT(o.id) AS total_orders
FROM users u
JOIN orders o ON o.user_id = u.id
WHERE o.created_at > '2026-01-01'
GROUP BY u.name;
```

## Index không phải thuốc tiên

| Tình huống | Index có giúp? |
|---|---|
| `WHERE` trên cột có độ chọn lọc cao | Có |
| `WHERE` trên cột boolean | Hầu như không |
| `LIKE '%abc'` | Không |
| `LIKE 'abc%'` | Có |

## Lỗi thường gặp

- `SELECT *` khi chỉ cần vài cột
- Hàm bọc quanh cột trong `WHERE` (ví dụ `WHERE YEAR(created_at) = 2026`) làm index vô dụng
- N+1 query trong ORM

---

Đây chỉ là bài mẫu — bạn có thể xóa và thay bằng nội dung của mình.
