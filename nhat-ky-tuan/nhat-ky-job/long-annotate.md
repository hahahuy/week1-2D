# Person-bit Annotate — @Long — 2026-09-15

> Copy file này thành `long-annotate-YYYY-MM-DD.md` trong `nhat-ky-job/`.
> Viết cuối ngày, **trước 16:00** (deadline annotate). Làm nhiêu nộp bấy.

## Metadata

- **Ngày:** 2026-09-15 (T3)
- **Annotator:** @Long
- **Reviewer (vòng cố định):** @PHuy — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** `phuy-review-long.md` (điền `chưa có` nếu chưa xong)

## Numbers

- Task A (Seg): _ / 25 (lũy kế: _ / 25)
- Task B (BBox/Poly): _ / 25 (lũy kế: _ / 25)
- **Total: _ / 50**

## What happened

- tại w1/bbox_polygon/G02/G02_B074.jpg trong ảnh chỉ nhìn thấy ánh đèn của xe phía trước, có thể xác định là có phương tiện nhưng không nhìn rõ thân xe và ranh giới của vehicle. Trường hợp này có cần tạo bounding box không, hay bỏ qua vì không đủ thông tin để xác định box chính xác? 
- w1/bbox_polygon/G02/G02_B062.jpg trong trường hợp không nhìn thấy rõ lề đường/vỉa hè nên không thể xác định được ranh giới ngoài của area/drivable, thì nên annotation như thế nào? Có nên chỉ vẽ đến vùng mà mình chắc chắn là xe có thể chạy, hay vẫn phải suy đoán phần ranh giới bị khuất/không thể nhận biết?
- w1/bbox_polygon/G02/G02_B061.jpg có phần cầu vượt thì nên đánh bouding box và tên label là gì ?

## Terrible frames

[Free prose. List each frame with link, why it's terrible, and your proposal (keep / drop / ask mentor). Example:
"Frame 142 — blurred car behind pillar, ~30% visible. Propose keep, occlusion is key edge case. Frame 201 — person sitting on motorcycle, guideline §3.2 ambiguous, propose ask mentor."]

## Blocker

- [ ] No blocker
- [ ] Yes — `P-xxx`: [short link or description]

## Cross-link verification

- [ ] Reviewer field above matches `phan-cong-review.md` rotation
- [ ] Cross-link to review file is correct

---
*Reviewer will cross-link back to this file from `phuy-review-long.md`.*
