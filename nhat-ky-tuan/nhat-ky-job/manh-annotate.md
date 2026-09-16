# Person-bit Annotate — @Mạnh — 2026-09-15

## Metadata

- **Ngày:** 2026-09-15 (T3)
- **Annotator:** @Mạnh (Nhóm trưởng Task A — Semantic Segmentation)
- **Reviewer (vòng cố định):** @Cường — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** `cuong-review-manh.md` (chưa có)

## Numbers

- Task A (Seg): 25 / 25 (lũy kế: 25 / 25)
- Task B (BBox/Poly): — **(nhóm trưởng, chỉ làm 1 task)**
- **Total: 25 / 25**
- Review 50 ảnh của người trước (PHuy) trong `manh-review-phuy.md`: **chưa xong, đang làm**

## What happened

Hôm nay khó khăn chính đến từ ranh giới mờ giữa các lớp — vạch đường cho người đi bộ hoặc lane bị chéo góc, bị xe/vật cản che khuất, hoặc lẫn màu với sidewalk/tường/bóng cây. Pattern hoạt động tốt: khi landmark (vạch, lane) bị che, annotate theo bánh xe hoặc để điểm mờ căn theo hướng đường thay vì đoán mù. Ngoài ra xuất hiện thêm nhóm case "hành vi bất thường" — người đi bộ không đi trong sidewalk mà băng ngang làn bus-only hoặc giữa đường không vạch kẻ (S018, S021), xe di chuyển lệch giữa vạch kẻ đường (S020) — chưa rõ nên annotate theo hành vi thực tế hay theo layout chuẩn của đường. Case gây confusing nhất vẫn là các case liên quan biển báo/đèn tín hiệu: G02_S012 (biển stop, không rõ có annotate tiếp đường phía sau không) và G02_S025 (2 cột đèn đỏ hai bên đường, không rõ nên căn theo cột nào). Đề xuất tạo P-xxx cho: case biển/đèn báo hiệu (S012, S025), case vạch đường mờ không có ngăn cách 2 hướng xe (S013), và case người đi bộ/xe đi lệch khỏi layout chuẩn (S018, S020, S021).

## Terrible frames

- **[G02_S001](w1/segmentation/G02/G02_S001.jpg)** — Góc nhìn vạch qua đường cho người đi bộ bị chéo từ trên xuống, gây khó nhìn. Propose: keep, annotate theo hướng vạch suy ra từ phối cảnh.
- **[G02_S002](w1/segmentation/G02/G02_S002.jpg)** — Các khoảng trời xen lẫn lá cây gây khó nhìn (biên tán cây/trời). Propose: keep, ưu tiên contour lá cây rõ nhất, bỏ qua phần lấm tấm nhỏ.
- **[G02_S003](w1/segmentation/G02/G02_S003.jpg)** — Phần sidewalk có chướng ngại vật, phần lane có xe dừng bên cạnh. Propose: keep — annotate lane theo phần bánh xe hoặc điểm mờ căn theo đường.
- **[G02_S004](w1/segmentation/G02/G02_S004.jpg)** — Phần vạch đường cho người đi bộ bị các xe phía trước chắn mất tầm nhìn. Propose: keep, suy vạch từ đoạn còn thấy được, đánh dấu occlusion.
- **[G02_S005](w1/segmentation/G02/G02_S005.jpg)** — Phần bên trái bị ánh sáng hắt, phần đường lẫn vào với phần tường. Propose: ask mentor — ranh giới đường/tường không chắc chắn do chói sáng.
- **[G02_S007](w1/segmentation/G02/G02_S007.jpg)** — Phần đường tối, không nhìn rõ phần đường ở chân trời, bị lẫn với đường. Propose: keep, chỉ annotate phần còn phân biệt được, để phần tối mờ.
- **[G02_S008](w1/segmentation/G02/G02_S008.jpg)** — Lề vỉa hè thấp, gạch vỉa hè trùng màu đường, có thể gây lẫn. Propose: ask mentor — cần quy tắc rõ cho case lề thấp trùng màu.
- **[G02_S009](w1/segmentation/G02/G02_S009.jpg)** — Cây trồng mọc gần sát đường, lấn ranh giới. Propose: keep, cắt theo mép gốc cây thay vì tán lá.
- **[G02_S011](w1/segmentation/G02/G02_S011.jpg)** — Nhiều xe ô tô cần detect, che khuất nhau. Propose: keep, annotate từng xe theo phần visible, đánh dấu occlusion giữa các xe.
- **[G02_S012](w1/segmentation/G02/G02_S012.jpg)** — Đường có chữ STOP, có biển stop — phân vân có nên đi tiếp (annotate tiếp đường phía sau) hay không. Propose: ask mentor — cần guideline rõ, tạo `P-xxx`.
- **[G02_S013](w1/segmentation/G02/G02_S013.jpg)** — Vạch đường mờ, không có ngăn cách 2 hướng xe đi. Propose: ask mentor — cần convention cho case không có lane divider rõ.
- **[G02_S018](w1/segmentation/G02/G02_S018.jpg)** — Người đi bộ không đi trong sidewalk, phía trước là làn đường cho bus only. Propose: ask mentor — annotate theo vị trí thực tế của người đi bộ hay theo layout chuẩn (sidewalk/bus lane)?
- **[G02_S020](w1/segmentation/G02/G02_S020.jpg)** — Xe phía trước di chuyển giữa vạch kẻ đường (lệch lane). Propose: keep, annotate lane theo vạch kẻ chuẩn, xe vẫn annotate theo vị trí thực tế dù lệch.
- **[G02_S021](w1/segmentation/G02/G02_S021.jpg)** — Không có vạch kẻ đường, người đi bộ đi giữa đường. Propose: ask mentor — cần rule cho case không có crosswalk nhưng có người đi bộ băng ngang.
- **[G02_S023](w1/segmentation/G02/G02_S023.jpg)** — Các xe lớn che vạch cho người đi bộ. Propose: keep, suy vạch từ đoạn còn thấy được (giống pattern ở S004), đánh dấu occlusion.
- **[G02_S025](w1/segmentation/G02/G02_S025.jpg)** — Có 2 cột đèn đỏ ở 2 bên đường, không rõ nên căn/annotate theo cột nào. Propose: ask mentor — cần guideline rõ cho case nhiều đèn tín hiệu, tạo `P-xxx`.

## Blocker

- [ ] No blocker
- [x] Yes — `P-xxx`: guideline gap cho 3 nhóm case — (1) biển báo/đèn tín hiệu (S012, S025), (2) vạch đường mờ/không có ngăn cách 2 hướng xe (S013), (3) người đi bộ/xe đi lệch khỏi layout chuẩn (S018, S020, S021)

## Cross-link verification

- [ ] Reviewer field above matches `phan-cong-review.md` rotation
- [ ] Cross-link to review file is correct — sẽ cập nhật sau khi @Cường tạo `cuong-review-manh.md`

---
*Reviewer will cross-link back to this file from `cuong-review-manh.md`.*
