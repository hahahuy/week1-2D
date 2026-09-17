# Person-bit Annotate — @Mạnh — 2026-09-15

> Copy file này thành `manh-annotate-YYYY-MM-DD.md` trong `nhat-ky-job/`.
> Viết cuối ngày, **trước 16:00** (deadline annotate). Làm nhiêu nộp bấy.
> **Nhóm trưởng Task A Seg — chỉ gán 25 ảnh.**

## Metadata

- **Ngày:** 2026-09-15 (T3)
- **Annotator:** @Mạnh (Nhóm trưởng Task A — Semantic Segmentation)
- **Reviewer (vòng cố định):** @Cường — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** `cuong-review-manh.md` (điền `chưa có` nếu chưa xong)

## Numbers

- Task A (Seg): _ / 25 (lũy kế: _ / 25)
- Task B (BBox/Poly): — **(nhóm trưởng, chỉ làm 1 task)**
- **Total: _ / 25**
- Review đủ 50 ảnh của người trước (PHuy) trong `manh-review-phuy.md`

## What happened

+ w1/segmentation/G02/G02_S001.jpg : Góc nhìn vạch qua đường cho người đi bộ bị chéo từ trên xuống, gây khó nhìn
w1/segmentation/G02/G02_S002.jpg: Các khoảng trời xen lẫn lá cây gây khó nhìn 
+ w1/segmentation/G02/G02_S003.jpg: phần sidewalk có chướng ngại vật, phần lane có các xe dừng ở bên, annotate theo phần bánh xe hay để điểm mờ căn theo đường
+ w1/segmentation/G02/G02_S004.jpg: phần vạch đường cho người đi bộ bị các xe ở trước chắn mất tầm nhìn
+ w1/segmentation/G02/G02_S005.jpg: phần bên trái bị ánh sáng hắt, phần đường lẫn vào với phần tường.
+ w1/segmentation/G02/G02_S007.jpg: phần đường tối, ko nhìn rõ phần đường chân trời, bị lẫn với đường
w1/segmentation/G02/G02_S008.jpg: lề vỉa hè thấp, gạch vỉa hè trùng màu đường, có thể gây lẫn
+ w1/segmentation/G02/G02_S009.jpg: cây trồng ra gần sát đường
+ w1/segmentation/G02/G02_S011.jpg: có nhiều xe ô tô cần detect, che khuất nhau
+ w1/segmentation/G02/G02_S012.jpg: đường có chữ stop, có biển stop. Xe phân vân có nên đi tiếp???
+ w1/segmentation/G02/G02_S013.jpg: vạch đường mờ, k có ngăn cách 2 hướng xe đi
+ w1/segmentation/G02/G02_S018.jpg : người đi bộ k đi trong side walk, phía trước là làn đường cho bus only
+ w1/segmentation/G02/G02_S020.jpg: xe phía trước di chuyển giữa vạch kẻ đường
+ w1/segmentation/G02/G02_S021.jpg: không có vạch kẻ đường, người đi bộ đi giữa đường
+ w1/segmentation/G02/G02_S023.jpg: các xe lớn che vạch cho người đi bộ
+ w1/segmentation/G02/G02_S025.jpg: có 2 cột đèn đỏ 2 bên, nên đi theo cái nào

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
*Reviewer will cross-link back to this file from `cuong-review-manh.md`.*
