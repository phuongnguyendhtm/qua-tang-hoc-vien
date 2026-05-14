# 📋 HƯỚNG DẪN CÀI ĐẶT CHO NHÂN SỰ
## Quy trình setup quà tặng cho học viên — Từ A đến Z

> File này dành cho **đội ngũ nội bộ**. Nhân sự đọc và làm theo từng bước để cài đặt 2 bộ quà tặng lên máy học viên.

---

## TỔNG QUAN

| Bước | Việc cần làm | Thời gian |
|------|-------------|-----------|
| 1 | Cài Node.js | 5 phút |
| 2 | Cài Antigravity (Gemini CLI) | 5 phút |
| 3 | Tải bộ quà tặng về máy học viên | 3 phút |
| 4 | Cài đặt Content Agent | 5 phút |
| 5 | Cấu hình API Key | 5 phút |
| 6 | Test thử | 5 phút |
| **Tổng** | | **~30 phút** |

---

## BƯỚC 1: CÀI NODE.JS

1. Mở trình duyệt, vào: **https://nodejs.org**
2. Bấm nút **Download LTS** (nút xanh to bên trái)
3. Mở file vừa tải → Next → Next → Install → Finish
4. **Kiểm tra:** Mở CMD (gõ `cmd` ở thanh Start) rồi gõ:
   ```
   node --version
   ```
   → Nếu hiện `v18.x.x` hoặc cao hơn → ✅ OK

---

## BƯỚC 2: CÀI ANTIGRAVITY (GEMINI CLI)

1. Mở CMD và gõ:
   ```
   npm install -g @anthropic-ai/gemini-cli
   ```
   > Nếu lệnh trên không hoạt động, thử cách khác:
   > Vào https://ai.google.dev/gemini-api/docs/gemini-cli và làm theo hướng dẫn trên trang.

2. **Kiểm tra:** Gõ trong CMD:
   ```
   gemini --version
   ```
   → Nếu hiện số phiên bản → ✅ OK

---

## BƯỚC 3: TẢI BỘ QUÀ TẶNG VỀ MÁY HỌC VIÊN

**Cách 1 — Clone từ GitHub (khuyên dùng):**
```
git clone https://github.com/phuongnguyendhtm/qua-tang-hoc-vien.git
```

**Cách 2 — Tải ZIP từ GitHub (không cần cài Git):**
1. Vào https://github.com/phuongnguyendhtm/qua-tang-hoc-vien
2. Bấm nút xanh **Code** → **Download ZIP**
3. Giải nén ra thư mục bất kỳ

**Cách 3 — Copy USB:**
Copy toàn bộ thư mục `qua-tang-hoc-vien/` từ USB sang máy học viên.

---

## BƯỚC 4: CÀI ĐẶT CONTENT AGENT

1. Mở CMD
2. Di chuyển đến thư mục Content Agent:
   ```
   cd đường-dẫn\qua-tang-hoc-vien\02-freeup-content-agent
   ```
   > **Mẹo:** Mở thư mục `02-freeup-content-agent` trong File Explorer, click vào thanh địa chỉ, gõ `cmd` rồi Enter → CMD sẽ mở đúng vị trí.

3. Gõ lệnh cài đặt:
   ```
   npm install
   ```
4. Đợi 2-5 phút cho đến khi thấy dòng `added xxx packages`
5. **Kiểm tra:** Thư mục `node_modules/` xuất hiện → ✅ OK

---

## BƯỚC 5: CẤU HÌNH API KEY

1. Trong thư mục `02-freeup-content-agent`, tạo file `.env`:
   ```
   copy .env.example .env
   ```

2. Mở file `.env` bằng Notepad:
   ```
   notepad .env
   ```

3. Điền API key vào (thay `xxxxx` bằng key thật):
   ```
   ANTHROPIC_API_KEY=sk-ant-xxxxx
   PEXELS_API_KEY=xxxxx
   ELEVENLABS_API_KEY=xxxxx
   ```

4. Lưu file (Ctrl+S) → Đóng Notepad

> **Lấy API key ở đâu?**
> | API | Đăng ký tại | Ghi chú |
> |-----|------------|---------|
> | Anthropic (BẮT BUỘC) | https://console.anthropic.com | Cần thẻ VISA, ~$5/tháng |
> | Pexels (tùy chọn) | https://www.pexels.com/api | Miễn phí |
> | ElevenLabs (tùy chọn) | https://elevenlabs.io | Có gói miễn phí |

---

## BƯỚC 6: TEST THỬ

### Test bộ 12 Skill

1. Mở CMD tại thư mục `01-bo-12-skill`:
   ```
   cd đường-dẫn\qua-tang-hoc-vien\01-bo-12-skill
   ```

2. Gõ `gemini` để mở Antigravity

3. Dán câu test:
   > Hãy đọc file `freeup-plugins/freeup-avatar-builder/SKILL.md` và cho tôi biết skill này làm gì.

4. Nếu AI trả lời mô tả về Avatar Builder → ✅ OK

### Test Content Agent

1. Mở CMD tại thư mục `02-freeup-content-agent`:
   ```
   cd đường-dẫn\qua-tang-hoc-vien\02-freeup-content-agent
   ```

2. Gõ `gemini` để mở Antigravity

3. Dán câu test:
   > Hãy chạy `/setup` để bắt đầu thiết lập Brand DNA.

4. Nếu AI bắt đầu hỏi về thương hiệu → ✅ OK

---

## ✅ CHECKLIST SAU KHI CÀI XONG

Đánh dấu từng mục khi hoàn thành:

```
[ ] Node.js đã cài (node --version hiện v18+)
[ ] Antigravity đã cài (gemini --version hoạt động)
[ ] Bộ quà tặng đã có trên máy học viên
[ ] npm install trong 02-freeup-content-agent thành công
[ ] File .env đã tạo và điền API key
[ ] Test bộ 12 Skill: AI đọc được file SKILL.md
[ ] Test Content Agent: AI chạy được /setup
```

---

## 🚨 XỬ LÝ LỖI THƯỜNG GẶP

### Lỗi: `'node' is not recognized`
→ Node.js chưa cài hoặc chưa restart CMD. Đóng CMD, mở lại.

### Lỗi: `'git' is not recognized`
→ Git chưa cài. Tải tại https://git-scm.com → cài mặc định.

### Lỗi: `npm install` bị treo
→ Kiểm tra kết nối mạng. Thử chạy lại.

### Lỗi: `ANTHROPIC_API_KEY invalid`
→ Kiểm tra lại key trong file `.env`. Không có dấu cách thừa.

### Lỗi: `'gemini' is not recognized`
→ Antigravity chưa cài. Quay lại Bước 2.

### Lỗi: `The editor could not be opened`
→ Bảo AI: *"Hãy kiểm tra lại thư mục và tạo mới trước khi ghi file nhé"*

---

## 📞 HỖ TRỢ

Nếu gặp lỗi không xử lý được:
1. Chụp màn hình lỗi
2. Gửi kèm thông tin: Windows mấy? Node version? Lỗi ở bước nào?
3. Gửi cho team leader để hỗ trợ
