# Kế hoạch triển khai — Vườn Hoa Rực Rỡ 20/10

## Định hướng sản phẩm
Microsite kỷ niệm Ngày Phụ nữ Việt Nam 20/10 dành cho tập thể 30 bạn nữ, được đóng gói thành một tệp `index.html` duy nhất để có thể mở trực tiếp trong trình duyệt. Trải nghiệm đi từ một màn hình mở quà giàu cảm xúc vào không gian photobook, thiệp tập thể và trò chơi bốc thăm lời chúc.

## Quyết định thiết kế
- **Design movement:** Romantic editorial glassmorphism — kết hợp cảm giác của một photobook cao cấp với lớp kính mờ, glow mềm và chi tiết kim loại champagne.
- **Core principles:** cảm xúc trước tính năng; chuyển động nhẹ như cánh hoa; cá nhân hóa rõ ràng; mọi tương tác đều có phản hồi hữu hình.
- **Color philosophy:** hồng phấn tạo sự dịu dàng và gần gũi, rose gold/champagne trao cảm giác trân trọng, ivory giữ nền ấm và giúp ảnh chân dung nổi bật.
- **Layout paradigm:** bố cục kể chuyện theo dòng dọc, hero lệch trục với các khối nội dung nổi như trang album; thư viện dùng masonry-like responsive grid thay vì các khối đồng đều đơn điệu.
- **Signature elements:** nhãn số thứ tự dạng con dấu champagne, viền glow quanh ảnh, cánh hoa rơi và hạt bụi ánh sáng trên toàn trang.
- **Interaction philosophy:** click để mở, kéo để khám phá, hover để thấy chiều sâu; các hiệu ứng đều ngắn, có chủ đích và tôn trọng `prefers-reduced-motion`.
- **Animation:** intro dùng typewriter + float + tilt; cards dùng rise/scale; modal dùng zoom/fade; canvas chạy `requestAnimationFrame` và giảm mật độ trên màn hình nhỏ.
- **Typography system:** Playfair Display cho tiêu đề cảm xúc; Be Vietnam Pro cho nội dung tiếng Việt; Montserrat cho nhãn viết hoa, số thứ tự và CTA.
- **Brand essence:** một khu vườn số để 30 cô gái được gọi tên, được nhìn thấy và được gửi lời thương riêng. Tính cách: dịu dàng, lấp lánh, chân thành.
- **Brand voice:** trang trọng nhưng gần gũi, có hình ảnh và không sáo rỗng. Ví dụ: “Mỗi bạn là một cánh hoa làm nên mùa rực rỡ này.” / “Chạm để mở một lời thương dành riêng cho bạn.”
- **Wordmark & logo:** huy hiệu tròn “20 / 10” với nét vẽ cánh hoa và chữ `Vườn Hoa` serif, dùng ở intro và header.
- **Signature brand color:** `#d98f9a` — dusty rose, màu hồng trầm vừa đủ riêng để làm dấu nhận diện.

## Kiến trúc triển khai
- `index.html`: toàn bộ markup, CSS inline, dữ liệu 30 hồ sơ, canvas animation, lightbox/localStorage, âm thanh và mini-game.
- `manus-routes.json`: khai báo route `/` cho preview/published serving.
- `app.config.ts`: metadata logo tối thiểu cho project WebDev, không chứa logic ứng dụng.
- `TODO.md`: các outcome và tiêu chí chấp nhận bám sát yêu cầu gốc.

## Luồng chức năng
1. Intro overlay khởi tạo typewriter, bó hoa CSS 3D, tilt theo con trỏ và nút mở quà.
2. Sau khi mở, canvas hoa rơi/hạt sáng tiếp tục chạy; người xem có thể bật/tắt FX và nhạc.
3. Thư viện render đúng 30 card từ một mảng dữ liệu duy nhất; click card mở photobook modal.
4. Modal hỗ trợ prev/next, phím mũi tên, swipe cảm ứng, thả tim và lưu `likedMembers` vào localStorage.
5. Thiệp tập thể lật 3D bằng nút mở thiệp.
6. Hộp quà bí mật chọn một lời chúc, kích hoạt fireworks canvas + canvas-confetti và cập nhật câu trả lời.

## Giới hạn vật liệu
- Ảnh mẫu dùng URL Unsplash khác nhau để người dùng dễ thay bằng ảnh thật sau này; vị trí thay dữ liệu được chú thích trực tiếp trong file.
- Audio nền là một bản instrumental CDN, chỉ phát sau thao tác người dùng để tuân thủ autoplay policy.
- Không cần server/database vì microsite là static frontend; preview chạy bằng HTTP server tối giản trên port 3000.
