# 📋 HƯỚNG DẪN CÀI ĐẶT CHO NHÂN SỰ
## Cài quà tặng lên máy học viên

> Nhân sự làm **3 việc chuẩn bị**, rồi dán prompt vào Antigravity — AI tự cài hết.

---

## Chuẩn bị trước

### 1️⃣ Cài Antigravity (Gemini CLI)
Xem hướng dẫn tại: https://ai.google.dev/gemini-api/docs/gemini-cli

### 2️⃣ Cài Node.js
Tải tại https://nodejs.org → chọn **LTS** → cài mặc định (Next → Next → Install)

### 3️⃣ Lấy 3 mã API Key

| Mã | Cách lấy | Ghi chú |
|----|----------|---------|
| `GEMINI_API_KEY` | https://aistudio.google.com/apikey | **Bắt buộc** — Miễn phí |
| `PEXELS_API_KEY` | https://www.pexels.com/api | Tùy chọn — Video B-Roll miễn phí |
| `ELEVENLABS_API_KEY` | https://elevenlabs.io | Tùy chọn — Giọng đọc AI |

---

## Cài đặt

### Bước 1: Tải quà tặng về máy

Mở CMD/Terminal và gõ:
```
git clone https://github.com/phuongnguyendhtm/qua-tang-hoc-vien.git
```

> Không có Git? → vào https://github.com/phuongnguyendhtm/qua-tang-hoc-vien → bấm **Code** → **Download ZIP** → giải nén.

### Bước 2: Mở Antigravity tại thư mục quà tặng

```
cd qua-tang-hoc-vien
gemini
```

Dán **nguyên văn prompt bên dưới** vào Antigravity:

---

### 🤖 PROMPT CÀI ĐẶT (Copy nguyên khối)

```
Tôi là nhân sự đang cài đặt quà tặng cho học viên. Hãy giúp tôi chạy quy trình cài đặt theo đúng thứ tự sau:

1. KIỂM TRA MÔI TRƯỜNG:
   - Chạy "node --version" kiểm tra Node.js (cần v18+)
   - Nếu chưa có, nhắc tôi cài tại https://nodejs.org
   - Đợi tôi xong rồi mới tiếp

2. CÀI ĐẶT CONTENT AGENT:
   - Di chuyển vào thư mục "02-freeup-content-agent"
   - Chạy "npm install" và đợi hoàn tất
   - Tạo file .env từ .env.example
   - Hỏi tôi từng API key để điền vào .env:
     + GEMINI_API_KEY (bắt buộc)
     + PEXELS_API_KEY (tùy chọn, bỏ qua nếu chưa có)
     + ELEVENLABS_API_KEY (tùy chọn, bỏ qua nếu chưa có)

3. TEST THỬ:
   - Kiểm tra "01-bo-12-skill/freeup-plugins/" có đủ 12+ skill
   - Kiểm tra "02-freeup-content-agent/node_modules/" đã có
   - Kiểm tra "02-freeup-content-agent/.env" đã có API key

4. BÁO CÁO:
   In bảng tóm tắt:
   - Node.js: ✅/❌
   - Content Agent: ✅/❌
   - API Key: ✅/❌
   - Bộ 12 Skill: ✅/❌

Bắt đầu ngay.
```

---

## Xong!

Khi Antigravity báo tất cả ✅ → máy học viên đã sẵn sàng.

**Học viên bắt đầu dùng:**
- **Bộ 12 Skill:** Mở `01-bo-12-skill` → `gemini` → yêu cầu chạy skill
- **Content Agent:** Mở `02-freeup-content-agent` → `gemini` → gõ `/setup`

---

## 🚨 Lỗi thường gặp

| Lỗi | Xử lý |
|-----|-------|
| `'node' is not recognized` | Cài Node.js, restart CMD |
| `'git' is not recognized` | Tải ZIP từ GitHub thay vì clone |
| `npm install` treo | Kiểm tra mạng, thử lại |
| `'gemini' is not recognized` | Cài lại Antigravity theo link ở trên |
