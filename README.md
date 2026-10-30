# CampusPay – Lựa chọn công cụ giao tiếp nhóm

## Phần 1. Phân tích và đề xuất

### 1. Đầu vào / Đầu ra (I/O)

- **Đầu vào:** Nhóm startup 4–5 người; tin quan trọng bị trôi, khó tìm quyết định cũ, cần giao việc và theo dõi deadline. Một số người chỉ dùng điện thoại, đối tác quen Zalo.
- **Đầu ra:** Công cụ giúp phân loại trao đổi, tìm tin/file, giao việc rõ người–hạn chót, giảm họp và vẫn dễ sử dụng.

### 2. Ưu và nhược điểm

- **Zalo:** Dễ dùng, miễn phí, ai cũng quen, tiện liên hệ đối tác. Nhược điểm: nhiều chủ đề dễ lẫn trong một nhóm; ghim tin và tìm kiếm chưa thay thế được quy trình quản lý dự án.
- **Lark:** Có nhóm trò chuyện theo chủ đề, Thread, tìm kiếm, Task, Docs và Calendar; phù hợp quản lý công việc. Nhược điểm: mất thời gian làm quen, cần thiết lập quy tắc và chú ý giới hạn gói miễn phí.

## Phần 2. So sánh và lựa chọn

### 3. Bảng so sánh 5 tiêu chí

| Tiêu chí | Zalo | Lark |
|---|---|---|
| Chống trôi thông báo | ⚠️ Có ghim, nhưng dễ lẫn với trò chuyện | ✅ Nhóm riêng, ghim tin, Thread |
| Quản lý công việc | ⚠️ Có hỗ trợ giao việc cơ bản, ít tích hợp quy trình | ✅ Tạo Task từ chat, giao người và deadline |
| Miễn phí, dễ bắt đầu | ✅ Quen thuộc, gần như không cần học | ⚠️ Có gói miễn phí nhưng phải làm quen |
| Tìm lại lịch sử 2 tháng | ⚠️ Có tìm kiếm, phụ thuộc lịch sử/file còn lưu | ✅ Tìm kiếm trong môi trường làm việc có tổ chức |
| Giao tiếp bất đồng bộ | ⚠️ Có thể viết rõ nhưng dễ lạc ngữ cảnh | ✅ Thread, Task và tài liệu giữ ngữ cảnh |

*Chú thích: ✅ Tốt · ⚠️ Trung bình · ❌ Kém. Đánh giá theo nhu cầu CampusPay, không phải kết luận tuyệt đối.*

### 4. Lựa chọn và xử lý 3 bẫy

**Chọn mô hình kết hợp: Lark cho nội bộ, Zalo cho đối tác bên ngoài.**

1. **Chỉ có điện thoại:** Lark có ứng dụng di động nên vẫn nhắn tin, theo dõi công việc được.
2. **Deadline gần:** Không bắt cả nhóm học toàn bộ Lark ngay. Giữ Zalo cho việc gấp; chuyển dần sang Lark sau deadline hoặc dành khoảng 30–60 phút học các thao tác cần thiết.
3. **Đối tác chỉ dùng Zalo:** Tiếp tục trao đổi với họ qua Zalo. Người phụ trách ghi lại quyết định và tạo Task trên Lark; không chuyển dữ liệu mật tùy tiện.

**Đánh đổi:** Mất ít thời gian thiết lập ban đầu để về lâu dài giảm tìm kiếm, nhắc việc và họp lại các nội dung đã thống nhất.

## Phần 3. Thiết kế và triển khai

### 5. Cấu trúc nhóm trò chuyện Lark

*Lark dùng **group chat**; các tên bắt đầu bằng `#` dưới đây là quy ước đặt tên giống channel, không phải loại kênh riêng như Slack.*

| Nhóm | Mục đích | Người được đăng |
|---|---|---|
| `#thong-bao` | Deadline, quyết định chính thức | Chỉ trưởng nhóm/quản trị viên |
| `#dev` | Code, API, lỗi kỹ thuật | Ban Kỹ thuật |
| `#design` | UI/UX, hình ảnh, phản hồi thiết kế | Ban Thiết kế |
| `#kinh-doanh` | Business Plan, đối tác | Ban Kinh doanh |
| `#lien-ban` | Phối hợp giữa các ban | Thành viên nội bộ liên quan |
| `#cong-viec` | Task, tiến độ, người phụ trách | Trưởng nhóm và thành viên được phân công |

*Ba ban chuyên môn được nêu trong đề; trưởng nhóm phụ trách điều phối chung. Chỉ mời đúng người cần tham gia từng nhóm.*

### Quy tắc chống spam `@all` (cờ đỏ)

- Cài quyền `@all` **chỉ cho chủ nhóm/quản trị viên**; chỉ dùng khi có deadline gấp, sự cố hoặc thông báo quan trọng.
- `#thong-bao`: đặt quyền gửi tin **chỉ chủ nhóm/quản trị viên**, ghim thông báo chính thức.
- Trả lời bằng **Thread** để không đẩy nội dung quan trọng trôi đi; việc cần làm phải có **người phụ trách + deadline**.
- Không thêm người ngoài hoặc chia sẻ dữ liệu khách hàng vào nhóm nội bộ khi chưa được phép.

**Kết luận:** CampusPay nên dùng **Lark để quản lý nội bộ**, **Zalo để liên hệ đối tác**. Đây là giải pháp cân bằng giữa hiệu quả và chi phí chuyển đổi.

### Tham khảo

- [Lark – Messenger, Thread và Task](https://www.larksuite.com/hc/en-US/articles/191742533872-get-started-with-messenger)
- [Lark – Phân quyền gửi tin trong nhóm](https://www.larksuite.com/hc/vi-VN/articles/821318680124-thi%E1%BA%BFt-l%E1%BA%ADp-ai-c%C3%B3-th%E1%BB%83-%C4%91%C4%83ng-tin-nh%E1%BA%AFn-trong-nh%C3%B3m)
- [Lark – Gói dịch vụ](https://www.larksuite.com/hc/vi-VN/articles/497171699982-t%E1%BB%95ng-quan-v%E1%BB%81-c%C3%A1c-g%C3%B3i-d%E1%BB%8Bch-v%E1%BB%A5-lark)
