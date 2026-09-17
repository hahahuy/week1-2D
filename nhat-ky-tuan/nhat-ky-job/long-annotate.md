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

- w1/bbox_polygon/G02/G02_B051.jpg: UNCERTAIN_SCOPE: Không xác định rõ biển trong ảnh là bảng tên đường hay traffic sign. Trường hợp này có cần annotate dưới class traffic sign không?
- w1/bbox_polygon/G02/G02_B061.jpg có phần cầu vượt thì nên đánh bouding box và tên label là gì ?
- w1/bbox_polygon/G02/G02_B062.jpg: trong trường hợp không nhìn thấy rõ lề đường/vỉa hè nên không thể xác định được ranh giới ngoài của area/drivable, thì nên annotation như thế nào? Có nên chỉ vẽ đến vùng mà mình chắc chắn là xe có thể chạy, hay vẫn phải suy đoán phần ranh giới bị khuất/không thể nhận biết?
- w1/bbox_polygon/G02/G02_B063.jpg: có hàng rào thì vẽ polygon như thế nào, chọn label nào ?
- w1/bbox_polygon/G02/G02_B067.jpg: UNCERTAIN_SCOPE: Bảng tên đường như trong ảnh có được annotate là traffic sign không?
- w1/bbox_polygon/G02/G02_B074.jpg: trong ảnh chỉ nhìn thấy ánh đèn của xe phía trước, có thể xác định là có phương tiện nhưng không nhìn rõ thân xe và ranh giới của vehicle. Trường hợp này có cần tạo bounding box không, hay bỏ qua vì không đủ thông tin để xác định box chính xác? 

- w1/bbox_polygon/G02/G02_B052.jpg: bình thường
- w1/bbox_polygon/G02/G02_B053.jpg: bình thường
- w1/bbox_polygon/G02/G02_B054.jpg: bình thường
- w1/bbox_polygon/G02/G02_B055.jpg: bình thường
- w1/bbox_polygon/G02/G02_B056.jpg: bình thường
- w1/bbox_polygon/G02/G02_B057.jpg: bình thường
- w1/bbox_polygon/G02/G02_B058.jpg: bình thường
- w1/bbox_polygon/G02/G02_B059.jpg: bình thường
- w1/bbox_polygon/G02/G02_B060.jpg: bình thường
- w1/bbox_polygon/G02/G02_B064.jpg: bình thường
- w1/bbox_polygon/G02/G02_B065.jpg: bình thường
- w1/bbox_polygon/G02/G02_B066.jpg: bình thường
- w1/bbox_polygon/G02/G02_B068.jpg: bình thường
- w1/bbox_polygon/G02/G02_B069.jpg: bình thường
- w1/bbox_polygon/G02/G02_B070.jpg: bình thường
- w1/bbox_polygon/G02/G02_B071.jpg: bình thường
- w1/bbox_polygon/G02/G02_B072.jpg: bình thường
- w1/bbox_polygon/G02/G02_B073.jpg: bình thường
- w1/bbox_polygon/G02/G02_B075.jpg: bình thường

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
