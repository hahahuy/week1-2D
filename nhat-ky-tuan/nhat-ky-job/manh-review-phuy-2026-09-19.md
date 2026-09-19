# Person-bit Review — @Mạnh review @PHuy — 2026-09-16
## Metadata

- **Ngày:** 2026-09-15
- **Reviewer:** @Mạnh
- **Annotator:** @PHuy
- **Vòng cố định:** xem [`phan-cong-review.md`](../../phan-cong-review.md) — `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
- **Source annotate file:** `phuy-annotate.md` 

## Numbers

- Task A (Seg): _ / 25 reviewed (sample check: _%) — 
- Task B (BBox/Poly): 25 / 25 reviewed (sample check: 100%) — G02_B076 → G02_B100
- **Total: 25 / 50** *(Task A còn thiếu số liệu)*

## What you found

Chất lượng annotate Task B nhìn chung còn nhiều lỗi hệ thống, tỷ lệ frame có vấn đề khá cao (16/25 frame, ~64%). Lỗi lặp lại nhiều nhất là **thiếu gán object bị truncated** (B082, B083, B092, B094 — ô tô/biển/xe cảnh sát bị cắt cạnh nhưng không được gán) và **thiếu gán alternative area / làn đỗ xe** (B078, B080, B081) — có thể do annotator chưa nắm rõ định nghĩa "alternative area" trong guideline (xem thêm B085, B093 — nhầm lẫn giữa vỉa hè và alternative area). Đáng chú ý là lỗi **nhầm ô tô thành đèn giao thông (traffic light)** xuất hiện liên tiếp ở B089 và B090 — đây là lỗi hệ thống về phân loại class chứ không phải lỗi ngẫu nhiên, cần review lại guideline phân biệt 2 class này với annotator. B100 cũng có vấn đề: chỉ gán 1 bbox cho nhiều người (person/pedestrian) — cần nhắc lại quy tắc tách bbox theo từng cá thể. Điểm annotator làm tốt: các frame không có vật thể phức tạp (B077, B079, B084, B088, B095–B099) được gán chính xác, sạch, không cần sửa.

## Terrible frames — agree / disagree with annotator

*(Chưa có danh sách "terrible" từ `phuy-annotate.md` để đối chiếu. Liệt kê trực tiếp các frame lỗi nghiêm trọng phát hiện được trong quá trình review — cần merge với danh sách của annotator khi có file.)*

- **G02_B089, G02_B090** — lỗi nghiêm trọng, gán nhầm ô tô thành đèn/traffic light 2 frame liên tiếp → nghi ngờ lỗi hệ thống, không phải one-off.
- **G02_B082, G02_B083, G02_B092, G02_B094** — object bị truncated (ô tô, biển, xe cảnh sát) nhưng chưa được gán — vi phạm quy tắc gán vật thể truncated (cần link section guideline cụ thể).
- **G02_B078, G02_B080, G02_B081** — thiếu gán alternative area / làn đỗ xe.
- **G02_B085, G02_B093** — cần check lại ranh giới vỉa hè vs. alternative area, annotator có vẻ nhầm lẫn 2 khái niệm.
- **G02_B100** — chỉ bb 1 người trong khi có nhiều người/pedestrian, cần tách bbox theo cá thể.
- **G02_B076, G02_B086, G02_B087, G02_B091** — các câu hỏi/nghi vấn cần annotator xác nhận lại (truncated car, biển vàng chưa gán, phần đường đối diện, ô tô vàng chưa gán) — chưa đủ căn cứ để kết luận đúng/sai, cần trao đổi trực tiếp.

## Verdict

- [ ] **Pass** — under 10% sample checked wrong
- [x] **Return whole job** — over 10% sample wrong (per QĐ-002) *(~64% frame Task B có lỗi, vượt xa ngưỡng 10%)*
- [ ] **Pass with conditions** — fix _ specific frames

## Escalate to P-xxx?

- [ ] No
- [x] Yes — `P-xxx`: [to create] — Lỗi hệ thống nhầm lẫn ô tô ↔ traffic light (B089, B090) và ranh giới vỉa hè/alternative area (B085, B093) có thể ảnh hưởng nhiều batch khác, cần escalate để review lại guideline với cả team, không chỉ riêng PHuy.

## Suggestion for tomorrow

Tập trung nhắc annotator 2 điểm: (1) luôn gán object dù bị truncated (theo guideline truncated object), và (2) rà lại định nghĩa alternative area / làn đỗ xe vs. vỉa hè trước khi làm tiếp batch mới. Ưu tiên trao đổi trực tiếp các frame còn nghi vấn (B076, B086, B087, B091) trước khi tính vào tỷ lệ lỗi cuối cùng.

---
*Cross-link: this file must be referenced from `phuy-annotate.md` same day.*
