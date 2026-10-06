# FREEUP Content 9B — Quà tặng học viên 1.1

Hệ thống content độc lập cho 9BizClaw, gồm 31 skill và 30 lệnh tiếng Việt. Học viên không cần có thư mục `02-freeup-content-agent` hoặc bộ Antigravity trước đây.

**Cách dùng nhanh:** sao chép toàn bộ [CAI-DAT-9B.txt](./CAI-DAT-9B.txt) vào chat 9B. Sau khi cài, dùng `/caidat`, `/vietbai`, `/minhhoa`, `/anhchu`, `/boanh`, `/tudong`, `/xem`, `/mothumuc`.

- [Tải ZIP 1.1](./distribution/FREEUP-CONTENT-9B-HOC-VIEN-v1.1.zip?raw=true)
- [Hướng dẫn học viên](./HUONG-DAN-HOC-VIEN.md)
- [Mã nguồn đầy đủ](./package/) — thư mục này giữ nguyên checksum của gói cài.

# Tải và cài hệ thống content từ GitHub

Gói học viên 1.1 hoạt động độc lập, không cần thư mục Antigravity của giảng viên. Máy cần có 9BizClaw v3 đã mở và hoàn tất khởi tạo. Internet dùng để tải gói và bộ công cụ xuất ảnh/video trong lần cài đầu.

## Cài bằng PowerShell trên máy chạy 9B

Tải script về tệp, xem script trước khi chạy. Script đối chiếu SHA-256 của bản 1.1 trước khi giải nén và cài. Có thể dùng `main` hoặc mã commit đầy đủ 40 ký tự ở biến `$contentRef`; mã commit cố định cả script và ZIP tại một bản đã xuất bản.

```powershell
$contentRepo = 'phuongnguyendhtm/qua-tang-hoc-vien'
$contentRef = 'main'
$contentInstaller = Join-Path $env:TEMP 'freeup-content-install.ps1'
Invoke-WebRequest "https://raw.githubusercontent.com/$contentRepo/$contentRef/03-freeup-content-9b/install-from-github.ps1" -OutFile $contentInstaller -UseBasicParsing
Get-Content -LiteralPath $contentInstaller
& $contentInstaller -Repository $contentRepo -Ref $contentRef -Apply -InstallDependencies
```

Nếu máy có nhiều agent, thêm `-Agent ten-agent` cho agent muốn dùng. Nếu bộ cài yêu cầu chọn agent, chạy lại với lựa chọn đó. Nếu máy đã có phiên bản cũ của đúng bộ quà tặng và bộ cài xác minh receipt, thêm `-Upgrade`; dữ liệu và hồ sơ riêng được giữ lại. Dừng khi có xung đột skill khác hoặc chính sách native từ chối.

Nếu tệp bị đánh dấu tải từ Internet, mở tệp để xem trước rồi dùng `Unblock-File -LiteralPath $contentInstaller` nếu bạn đã tin cậy bản phát hành. Lệnh này chỉ bỏ dấu trên đúng tệp đó. Nếu chính sách chạy script vẫn chặn, dùng cách cài trong chat 9B bên dưới hoặc quy trình được tổ chức cho phép; không tự đổi chính sách toàn máy.

Chỉ kiểm tra kế hoạch, chưa cài:

```powershell
& $contentInstaller -Repository $contentRepo -Ref $contentRef
```

Các tùy chọn:

| Tùy chọn | Ý nghĩa |
|---|---|
| `-Apply` | Cài qua bộ cài native sau khi kế hoạch thành công |
| `-InstallDependencies` | Tải công cụ ảnh/video; dùng cùng `-Apply` |
| `-Agent ten-agent` | Chọn agent của 9B |
| `-Upgrade` | Nâng phiên bản cùng gói đã được xác minh |
| `-InstallRoot 'đường-dẫn-9B'` | Chỉ định thư mục runtime nếu không tự tìm được |
| `-Destination 'thư-mục-tải'` | Đổi nơi lưu bản tải; không đổi kho thành phẩm của agent |
| `-Ref main` hoặc `-Ref mã-commit` | Chọn nhánh main hoặc commit cố định; `-Commit` cũng được hiểu |

Sau khi cài, mở chat 9B và chạy `/caidat`. Hệ thống đọc hồ sơ có sẵn, chỉ hỏi phần còn thiếu. Dùng `/vietbai`, `/minhhoa`, `/anhchu`, `/boanh`, `/tudong`, `/xem` và `/mothumuc`.

Thành phẩm nằm trong `freeup-content-data/media_output/ngày/ID-bài/` bên trong workspace của agent. `/mothumuc` mở thư mục trên máy chạy 9B. Điện thoại xem qua kênh đã kết nối hỗ trợ gửi tệp, khi việc gửi được xác minh thành công.

## Cài bằng câu lệnh trong chat 9B

Người dùng có thể dán yêu cầu này vào chat 9B có quyền đọc/tải tệp và chạy công cụ. Có thể thay `main` trong URL bằng commit đầy đủ của bản phát hành để cố định URL:

> Hãy tải bộ hệ thống content học viên 1.1 từ `https://raw.githubusercontent.com/phuongnguyendhtm/qua-tang-hoc-vien/main/03-freeup-content-9b/distribution/FREEUP-CONTENT-9B-HOC-VIEN-v1.1.zip`. Tôi cho phép cài các skill của gói qua bộ cài native và tải công cụ xuất ảnh/video cần thiết cho agent đang dùng. Kiểm SHA-256 phải là `450CB4B06548CCABAA7E0AF7473BCB30083567D959CA8337143B9E35747CD0B4`; nếu khác thì dừng. Giải nén an toàn vào thư mục mới, đọc `CAI-DAT-9B.txt` và `INSTALLER.md`, rồi thực hiện quy trình cài được mô tả theo quyền tôi vừa cấp. Chạy kế hoạch trước khi cài, giữ nguyên hồ sơ và dữ liệu riêng; khi cần nâng phiên bản cùng gói đã được xác minh, tôi cho phép dùng chế độ nâng. Không đổi chính sách bảo mật hoặc ghi đè skill khác. Khi cài và kiểm tra thành công, thực hiện `/caidat`, tái sử dụng hồ sơ doanh nghiệp đã có và chỉ hỏi phần còn thiếu.

Kho private yêu cầu đăng nhập được GitHub cho phép. Không đặt access token trong câu lệnh, URL, hồ sơ doanh nghiệp hoặc gói phát hành. Lệnh tải trực tiếp ở trên dành cho kho public.
