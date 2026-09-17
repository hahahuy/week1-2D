# Person-bit Annotate — @Cường — 2026-09-15

> Copy file này thành `cuong-annotate-YYYY-MM-DD.md` trong `nhat-ky-job/`.
> Viết cuối ngày, **trước 16:00** (deadline annotate). Làm nhiêu nộp bấy.
> **Nhóm trưởng Task B BBox — chỉ gán 25 ảnh.**

## Metadata

- **Ngày:** 2026-09-15 (T3)
- **Annotator:** @Cường (Nhóm trưởng Task B — BBox/Polygon/Polyline)
- **Reviewer (vòng cố định):** @HHuy — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** `hhuy-review-cuong.md` (điền `chưa có` nếu chưa xong)

## Numbers

- Task A (Seg): — **(nhóm trưởng, chỉ làm 1 task)**
- Task B (BBox/Poly): _ / 25 (lũy kế: _ / 25)
- **Total: _ / 25**
- Review đủ 50 ảnh của người trước (Mạnh) trong `cuong-review-manh.md`

## What happened

+ w1/bbox_polygon/G02/G02_B001.jpg, đánh giá lại road curb ở hai bên, có phải là alternative area không; nếu là other line hoặc double white line thì nên vẽ như thế nào, và cần đi hết tất cả các vạch trắng hay chỉ cần polygon đi theo đường thẳng để label là được.
+ w1/bbox_polygon/G02/G02_B002.jpg, ảnh mờ, cần review; không xác định được alternative area, đèn giao thông là reflection, không rõ lề đường và vạch kẻ.
+ w1/bbox_polygon/G02/G02_B003.jpg, chưa phân biệt được nét đứt và nét liền; các vạch mang cá hoặc vạch dừng cho làn khẩn cấp có phải alternative area không; road curb là chỉ đường kẻ vàng mép lề hay toàn khu vực lề đường.
+ w1/bbox_polygon/G02/G02_B004.jpg, item 48 không chắc chắn là bicycle hay chỉ thuần pedestrian.
+ w1/bbox_polygon/G02/G02_B008.jpg, chưa xác định được các line bên trái có thể xem là alternative area, road curb hay chỉ là single white line hoặc double white line.
+ w1/bbox_polygon/G02/G02_B010.jpg, vạch kẻ qua đường cho người đi bộ cần vẽ 1 polyline ở giữa tim line marking theo guideline hay phải vẽ rõ từng đường một với mỗi vạch trắng.
+ w1/bbox_polygon/G02/G02_B011.jpg, không xác định được vạch bên trái là cho người đi bộ hay double white line.
+ w1/bbox_polygon/G02/G02_B006.jpg, w1/bbox_polygon/G02/G02_B009.jpg, w1/bbox_polygon/G02/G02_B012.jpg, không xác định rõ double yellow line hay other line; các đường như thế vẽ polyline chỉ là các đường thẳng theo hướng xe chạy hay cả các vạch ngang nữa.
+ Những frame rõ như G02_B005.jpg, G02_B007.jpg thì làm tương đối ổn theo guideline; phần khó nhất là phân biệt line / road curb / alternative area ở các frame mờ hoặc có vạch chồng lẫn.

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
*Reviewer will cross-link back to this file from `hhuy-review-cuong.md`.*
