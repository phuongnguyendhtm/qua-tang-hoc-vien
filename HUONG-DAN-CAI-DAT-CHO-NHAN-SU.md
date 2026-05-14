# 📋 HƯỚNG DẪN CÀI ĐẶT CHO NHÂN SỰ
## Cài quà tặng lên máy học viên — Cực kỳ đơn giản

> Nhân sự chỉ cần làm **2 việc**: tải quà tặng về máy học viên, rồi dán prompt vào Antigravity.

---

## Bước 1: Tải quà tặng về máy học viên

Mở CMD/Terminal và gõ:
```
git clone https://github.com/phuongnguyendhtm/qua-tang-hoc-vien.git
```

> Nếu máy chưa có Git → vào https://github.com/phuongnguyendhtm/qua-tang-hoc-vien → bấm **Code** → **Download ZIP** → giải nén.

---

## Bước 2: Mở Antigravity và dán prompt bên dưới

Mở CMD tại thư mục `qua-tang-hoc-vien`, gõ `gemini` (hoặc mở bằng Cursor IDE), rồi **copy và dán nguyên văn prompt dưới đây** vào Antigravity:

---

### 🤖 PROMPT CÀI ĐẶT (Copy nguyên khối dưới đây)

```
Tôi là nhân sự đang cài đặt quà tặng cho học viên. Hãy giúp tôi chạy quy trình cài đặt theo đúng thứ tự sau:

1. KIỂM TRA MÔI TRƯỜNG:
   - Chạy "node --version" kiểm tra Node.js đã cài chưa (cần v18+)
   - Nếu chưa có, hướng dẫn tôi tải tại https://nodejs.org (chọn LTS)
   - Đợi tôi cài xong rồi mới tiếp tục

2. CÀI ĐẶT CONTENT AGENT:
   - Di chuyển vào thư mục "02-freeup-content-agent"
   - Chạy "npm install" và đợi hoàn tất
   - Tạo file .env từ .env.example
   - Hỏi tôi từng API key để điền vào .env:
     + ANTHROPIC_API_KEY (bắt buộc)
     + PEXELS_API_KEY (tùy chọn, bỏ qua nếu chưa có)
     + ELEVENLABS_API_KEY (tùy chọn, bỏ qua nếu chưa có)

3. TEST THỬ:
   - Kiểm tra thư mục "01-bo-12-skill/freeup-plugins/" có đủ 12+ skill không
   - Kiểm tra thư mục "02-freeup-content-agent/node_modules/" đã có chưa
   - Kiểm tra file "02-freeup-content-agent/.env" đã có API key chưa

4. BÁO CÁO KẾT QUẢ:
   Sau khi xong, in ra bảng tóm tắt:
   - Node.js: ✅/❌
   - Content Agent: ✅/❌
   - API Key: ✅/❌
   - Bộ 12 Skill: ✅/❌

Bắt đầu từ bước 1 ngay bây giờ.
```

---

## Xong!

Sau khi Antigravity báo tất cả ✅, máy học viên đã sẵn sàng sử dụng.

Học viên có thể bắt đầu dùng ngay bằng cách:
- **Bộ 12 Skill:** Mở thư mục `01-bo-12-skill`, gõ `gemini`, rồi yêu cầu chạy skill
- **Content Agent:** Mở thư mục `02-freeup-content-agent`, gõ `gemini`, rồi gõ `/setup`

---

## 🚨 Lỗi thường gặp

| Lỗi | Cách xử lý |
|-----|-----------|
| `'node' is not recognized` | Cài Node.js tại nodejs.org, restart CMD |
| `'git' is not recognized` | Cài Git tại git-scm.com hoặc tải ZIP từ GitHub |
| `npm install` bị treo | Kiểm tra mạng, thử lại |
| `'gemini' is not recognized` | Cài Gemini CLI: `npm install -g @anthropic-ai/gemini-cli` |
