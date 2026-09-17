# Person-bit Annotate — @PHuy — 2026-09-17

## Metadata

- **Ngày:** 2026-09-17 (T5)
- **Annotator:** @PHuy
- **Reviewer (vòng cố định):** @Mạnh — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** chưa có

## Numbers

- Task A (Seg): _ / 25 (lũy kế: _ / 25)
- Task B (BBox/Poly): _ / 25 (lũy kế: _ / 25)
- **Total: _ / 50**

## What happened

Batch Seg G02 có nhiều frame điều kiện xấu: ngược sáng, tuyết, mưa, chạng vạng. Đây là phần làm chậm nhất vì biên class khó bám. 
## Terrible frames

+ w1/segmentation/G02/G02_S077.jpg (frame 76). Ngược sáng mạnh, lens flare phủ giữa ảnh.
  (1) Xe và nhà ở cuối đường bị lóa trắng, không thấy biên. Tô `car`/`building` theo biên ước lượng, hay để trống + Issue UNCERTAIN_BOUNDARY?
  (2) Bên trái có tường gạch block và vách bê tông cao chạy dọc đường: là `wall` hay `building`?
  (3) Dải cỏ khô dưới chân tường là `terrain` hay `vegetation`?

+ w1/segmentation/G02/G02_S079.jpg (frame 78). Đường tuyết, ảnh bị nhòe chuyển động.
  (1) Đống tuyết phủ lề đường và vỉa hè không có class. Tô `terrain`, tô theo bề mặt bên dưới (`sidewalk`/`road`), hay để trống?

+ w1/segmentation/G02/G02_S080.jpg (frame 79). Chạng vạng, trên cầu.
  (1) Tháp cầu thép (dạng khung giàn) không có class `bridge`: tô `building`, `wall`, `fence` hay để trống?
  (2) Đèn đường bị lóa quầng sáng, làm biên `pole` phình ra: chỉ tô phần cột thấy rõ, đúng không?

+ w1/segmentation/G02/G02_S084.jpg (frame 83). Trời mưa, giọt nước trên kính làm nhòe cả ảnh.
  (1) Mặt đường ướt phản chiếu đèn xe: vẫn tô `road`, không tô theo phản chiếu, đúng không?

+ w1/segmentation/G02/G02_S085.jpg (frame 84).
  (1) Vùng gạch chéo vàng giữa hai chiều (xe không được đi vào): tô `road` hay để trống?
  (2) Các cọc chắn (bollard) màu đen: `pole` hay để trống?


+ w1/bbox_polygon/G02/G02_B078.jpg : giữa đường và vỉa hè có vạch vàng đôi và một vùng gạch chéo vàng (vùng cấm xe đi vào, dẫn tới dải phân cách).
+ w1/bbox_polygon/G02/G02_B081.jpg :Vạch đôi vàng thì vẽ 1 nét polyline ở giữa hay là vẽ 2 nét polyline.
## Blocker

- [ ] No blocker
- [x] Yes — `P-xxx`: Chưa có quy tắc cho (a) pixel của vật thể không thuộc 19 class (tuyết, cầu, barrier, cone, bollard). Guideline cấm tự tạo ignore class → cần mentor chốt label ignore/unlabeled cho batch.

## Cross-link verification

- [ ] Reviewer field above matches `phan-cong-review.md` rotation
- [ ] Cross-link to review file is correct