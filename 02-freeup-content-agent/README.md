# 🎁 Quà 2: FreeUp Content Agent — Cỗ Máy Sản Xuất Nội Dung Tự Động

## Cỗ máy này làm gì?

| Lệnh | Chức năng |
|-------|-----------|
| `/vietbai` | 🧠 Viết bài Facebook chuyên nghiệp theo giọng văn của bạn |
| `/tao_anh` | 🎨 Thiết kế ảnh quote, layout đẹp |
| `/tao_slide` | 🖼️ Tạo carousel 10 slide |
| `/tao_video` | 🎬 Tạo video Reels với voice-over AI |
| `/publish` | 🚀 Tự động đăng bài lên Facebook |
| `/auto_mode` | 🤖 Chạy từ ý tưởng → đăng bài (Zero-Touch) |
| `/research_ideas` | 🕵️ Nghiên cứu ý tưởng viral |
| `/add_template` | 🌟 Thêm mẫu thiết kế từ ảnh Canva |

---

## 🛠️ HƯỚNG DẪN CÀI ĐẶT (10 phút)

### Cần chuẩn bị

| Thứ | Cách lấy |
|-----|----------|
| **Node.js 18+** | Tải tại https://nodejs.org → chọn LTS → cài mặc định |
| **Antigravity** | [Hướng dẫn cài](https://ai.google.dev/gemini-api/docs/gemini-cli) |
| **API Key Anthropic** | Đăng ký tại https://console.anthropic.com → API Keys → Create Key |

### Bước 1: Mở thư mục này trong Terminal

```bash
cd đường-dẫn-tới/qua-tang-hoc-vien/02-freeup-content-agent
```

### Bước 2: Cài đặt

```bash
npm install
```
Đợi 2-5 phút.

### Bước 3: Tạo file cấu hình

**Windows (CMD):**
```bash
copy .env.example .env
```

**Mac/Linux:**
```bash
cp .env.example .env
```

### Bước 4: Điền API Key

Mở file `.env` bằng Notepad (hoặc bất kỳ text editor) và điền:

```env
# BẮT BUỘC — Bộ não AI viết bài
ANTHROPIC_API_KEY=sk-ant-xxxxx

# TÙY CHỌN — Video B-Roll miễn phí (đăng ký tại pexels.com/api)
PEXELS_API_KEY=xxxxx

# TÙY CHỌN — Giọng nói AI (đăng ký tại elevenlabs.io)
ELEVENLABS_API_KEY=xxxxx
```

### Bước 5: Mở Antigravity và bắt đầu!

```bash
gemini
```

Dán câu này vào chat:

> Chào Antigravity, tôi là Quản trị viên mới. Hãy chạy `/setup` để bắt đầu thiết lập Brand DNA cho doanh nghiệp tôi.

AI sẽ hỏi bạn về thương hiệu, giọng văn, Facebook → Thiết lập xong là sẵn sàng!

---

## 🎮 Cách sử dụng hàng ngày

### Viết bài + đăng Facebook (3 bước)

```
Bước 1: Gõ /vietbai --topic "chủ đề bạn muốn"
Bước 2: Gõ /tao_anh (hoặc /tao_slide, /tao_video)
Bước 3: Gõ /publish
```

### Chế độ tự động hoàn toàn

```
Gõ /auto_mode
```
→ AI tự viết bài, tạo media, và đăng Facebook. Bạn không cần làm gì!

---

## 📁 Cấu trúc thư mục

```
02-freeup-content-agent/
├── database/        ← Dữ liệu thương hiệu của bạn
├── media-input/     ← Đặt avatar.png, logo, video nền vào đây
├── media_output/    ← Thành phẩm (ảnh, video) sẽ xuất ra đây
├── scripts/         ← Các engine xử lý (không cần động vào)
├── skills/          ← Bộ não AI (không cần động vào)
├── .env             ← API keys của bạn (KHÔNG CHIA SẺ!)
├── GUIDE.md         ← Cẩm nang vận hành chi tiết
└── README.md        ← File gốc của dự án
```

---

## ⚠️ Lưu ý

> [!WARNING]
> **Bảo mật:** File `.env` chứa API key. KHÔNG chia sẻ cho ai.

> [!CAUTION]
> **Khi máy đang đăng bài:** Thả tay khỏi chuột và bàn phím. Để AI tự thao tác.

> [!TIP]
> **Không cần biết code!** Mọi tùy chỉnh đều có thể nhờ Antigravity làm bằng chat tiếng Việt. Ví dụ: *"Antigravity, hãy thêm tính năng chèn nhạc nền vào video"* — AI sẽ tự sửa code cho bạn.

---

## ❓ Câu hỏi thường gặp

**Chạy trên Windows được không?**
→ Được. Windows, Mac, Linux đều OK.

**Cần Docker không?**
→ Không. Chỉ cần Node.js.

**Chi phí API bao nhiêu?**
→ Anthropic: ~$5-10/tháng. Pexels: miễn phí. ElevenLabs: có gói miễn phí.

**Đăng bài có bị Facebook khóa không?**
→ Hệ thống dùng trình duyệt riêng biệt (Profile Isolation), rất an toàn.

**Muốn xem hướng dẫn chi tiết hơn?**
→ Mở file `GUIDE.md` trong thư mục này.
