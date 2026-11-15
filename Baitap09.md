# Bài 9: Trích xuất Phiếu báo hỏng Thiết bị thành Markdown Table 4 Cột.
## Vấn đề :
> Công ty techshop hàng ngày nhận trăm thông báo khiếu nại,cần cách tối ưu.
- Yêu cầu: **Thiết kế Prompt trích xuất bảng chuẩn**
- **Mô phỏng Output chuẩn**       
###  Giải quyết bài toán. 
> Phần 1 : Thiết kế Prompt trích xuất bảng chuẩn.
```text
Role: Data Extraction Expert.
Task: Đọc tin nhắn báo hỏng của khách hàng, trích xuất thông tin và định dạng thành bảng Markdown chính xác 4 cột.

Cấu trúc cột yêu cầu:
| Mã đơn hàng | Khách hàng & Khu vực | Thiết bị & Lỗi phát sinh | Mức độ ưu tiên |

Ràng buộc (Rules):
1. Cột "Mức độ ưu tiên" bắt buộc chỉ chọn một trong ba giá trị: Gấp, Bình thường, Thấp.
2. Negative Constraint: Chỉ trả về bảng Markdown hoàn chỉnh, tuyệt đối không kèm câu chào hỏi hay giải thích bên ngoài.

[DATA_START]
Tin 1: Anh là Hoàng bên Q7, máy tính laptop Asus TUF mã đơn #DH-8812 hôm qua chơi game tự nhiên màn hình xanh lè sập nguồn liên tục, cần sửa gấp trong hôm nay!
Tin 2: Em tên Linh ở Bình Thạnh, tai nghe Sony mua tuần trước #DH-9921 bên tai phải nghe nhỏ hơn tai trái, em không vội tuần sau lấy cũng được.
Tin 3: Chuột Logitech #DH-7734 bị double click bấm 1 thành 2 lần khó chịu quá shop ơi, tôi là Minh bên Tân Bình.
[DATA_END]
```
> Phần 2 : Mô phỏng OutPut chuẩn.

| Mã đơn hàng | Khách hàng & Khu vực | Thiết bị & Lỗi phát sinh | Mức độ ưu tiên |
| :--- | :--- | :--- | :--- |
| #DH-8812 | Hoàng (Q7) | Laptop Asus TUF - Màn hình xanh, sập nguồn liên tục khi chơi game | Gấp |
| #DH-9921 | Linh (Bình Thạnh) | Tai nghe Sony - Tai phải nghe nhỏ hơn tai trái | Thấp |
| #DH-7734 | Minh (Tân Bình) | Chuột Logitech - Lỗi double click (bấm 1 thành 2 lần) | Bình thường |
