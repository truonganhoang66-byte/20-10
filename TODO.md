# TODO — Vườn Hoa Rực Rỡ 20/10

## 1. Nền tảng và trải nghiệm mở đầu
- [ ] Toàn bộ sản phẩm được đóng gói trong một file HTML duy nhất `index.html`, gồm HTML, CSS nhúng/Tailwind và JavaScript nhúng, mở trực tiếp bằng trình duyệt để chạy.
- [ ] Sử dụng Tailwind CSS qua CDN, Google Fonts gồm Playfair Display, Montserrat và Be Vietnam Pro, Lucide Icons hoặc FontAwesome, canvas-confetti và JavaScript thuần kết hợp HTML5 Canvas.
- [ ] Màn hình mở đầu hiển thị hộp quà hoặc bó hoa 3D ở trung tâm với hiệu ứng float và phản hồi tilt/parallax theo chuyển động rê chuột.
- [ ] Thông điệp mở đầu có hiệu ứng gõ chữ; nút “Mở quà ngay” có pulse/glow và khi click tạo chuyển cảnh fade-out/zoom-in mượt mà vào không gian chính.
- [ ] Giao diện dùng tone hồng pastel, rose gold/champagne, trắng ngà, glimmer/sparkles và soft shadow/glow; responsive mobile-first, không tràn màn hình.

## 2. Canvas, âm thanh và phản hồi tương tác
- [ ] Canvas nền chạy bằng requestAnimationFrame, mô phỏng cánh hoa hồng/cánh hoa anh đào rơi có gió và hạt sáng tương tác theo con trỏ; mật độ được tối ưu cho mobile và có nút bật/tắt hiệu ứng.
- [ ] Có nút bật/tắt nhạc với trạng thái trực quan, sử dụng nhạc nền không lời từ CDN và chỉ phát sau tương tác người dùng.
- [ ] Có micro-SFX cho thao tác nút và pháo hoa bằng Web Audio API hoặc nguồn âm thanh CDN phù hợp.

## 3. Dữ liệu 30 bạn nữ và thư viện ký ức
- [ ] JavaScript có đúng 30 phần tử trong một mảng hồ sơ; mỗi phần tử có đủ id, name, nickname/trait, URL ảnh chân dung Unsplash khác nhau và lời chúc riêng biệt.
- [ ] Có chú thích tiếng Việt rõ ràng chỉ vị trí người dùng thay tên và ảnh thật của 30 bạn.
- [ ] Thư viện hiển thị đủ 30 hồ sơ trong lưới responsive tương tác; card dùng glassmorphism, hover/touch phóng to, nghiêng nhẹ 3D và phát sáng viền.
- [ ] Click một card mở lightbox photobook với ảnh lớn và khung thiệp lời chúc cá nhân hóa.
- [ ] Lightbox có Next/Prev, phím mũi tên, đóng modal, hỗ trợ vuốt chạm trên mobile và không khóa thao tác ngoài ý muốn.
- [ ] Nút “Thả tim / Gửi yêu thương” tạo floating heart particles và lưu trạng thái đã thích trong localStorage để còn sau khi reload.

## 4. Thiệp tập thể và mini-game
- [ ] Có thiệp chúc mừng tập thể 20/10 dạng thiệp mở 3D với nội dung chân thành, trang trọng, ca ngợi vẻ đẹp, trí tuệ, tài năng và năng lượng tích cực của 30 bạn nữ.
- [ ] Có khu vực “Hộp quà bí mật / Vòng quay lời chúc may mắn” và nút “Nhận lộc / Bốc thăm lời chúc ngày 20/10”.
- [ ] Khi bốc thăm, hệ thống ngẫu nhiên một danh ngôn/lời chúc ngọt ngào/hài hước, trình diễn pháo hoa trên canvas và confetti đa sắc màu.

## 5. Chất lượng mã nguồn
- [ ] Code được phân tách rõ theo các khối dữ liệu 30 người, Canvas hoa rơi, lightbox/localStorage, audio, thiệp 3D và mini-game pháo hoa; có chú thích tiếng Việt ở từng khối chức năng.
- [ ] Route manifest tĩnh phục vụ `GET /manus-routes.json` khai báo route `/` và không dùng SPA fallback để che mất asset hoặc endpoint.
- [ ] Preview lắng nghe trên `0.0.0.0:3000`, HTML được kiểm tra cú pháp và dự án được lưu checkpoint trên nhánh main của repository WebDev.
