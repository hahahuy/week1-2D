# Person-bit Annotate — @HHuy — 2026-09-15

> Copy file này thành `hhuy-annotate-YYYY-MM-DD.md` trong `nhat-ky-job/`.
> Viết cuối ngày, **trước 16:00** (deadline annotate). Làm nhiêu nộp bấy.

## Metadata

- **Ngày:** 2026-09-15 (T3)
- **Annotator:** @HHuy
- **Reviewer (vòng cố định):** @Long — xem [`phan-cong-review.md`](../../phan-cong-review.md)
- **Cross-link review:** `long-review-hhuy.md` (điền `chưa có` nếu chưa xong)

## Numbers

- Task A (Seg): _ / 25 (lũy kế: _ / 25)
- Task B (BBox/Poly): _ / 25 (lũy kế: _ / 25)
- **Total: _ / 50**

## What happened

### BBox
+ w1/bbox_polygon/G02/G02_B026.jpg (frame 1), là frame đầu tiên làm nên có nhiều vướng mắc thẳng vào guideline, như là sự khác nhau giữa perdestrian và person mark trong ảnh nên như nào, area drivable và area alternative hơi vague nên assume là ngoại trừ drivable thì là mặc định alternative. với lại việc phân area lái mình kéo dài area tới đường chân trời (Horizon Line - Vanishing Point), vì theo cái sense của việc học máy nó sẽ hiểu rõ hơn về area, đồng thời cũng có thể dễ label các vạch trắng dải, vạch qua đường nếu mark theo kiểu này. Và có lẽ phải bàn lại về trafic_light nên là cái cục đèn thôi hay là cả cây đèn giao thông. Và có lẽ cũng phải chú thích rõ biển báo giao thông là cả các biển báo gồm chữ hay biển báo ký tự vì sense máy học sẽ không thể đọc chữ hay phân biệt được biển báo chữ (trong trường hợp quá nhiều chữ), thì nó sẽ không phân biệt được biển quảng cáo hay biển báo chữ bình thường
+ w1/bbox_polygon/G02/G02_B027.jpg (frame 2), tương tự với area driveable và phần đường đi bộ (alternative), vấn đề mới duy nhất sẽ là đèn báo hiệu qua đường đang cân nhắc là có được tính như traffic_light, trong phần đường crossway, để đi bộ qua thì có tính là như một area alternative chồng lên trên drivable không
+ w1/bbox_polygon/G02/G02_B028.jpg (frame 3), có thể coi như là một near-terrible frame vì cảnh vào buổi tối sau trời mưa, đường ướt làm phản chiếu đèn + phản chiếu dèn lên xe (tại đây là góc nhìn hành trình) không nhìn rõ được người đi đường + các chiếc xe màu đen đậu bên lề + trạm xe bus (nhìn nhầm thành một chiếc bus) (nếu xét theo sense học máy thì vẫn dùng được để nhận diện một con đường tối trông như nào nhưng mà dùng ảnh này để trực tiếp train thì ít học được). Đang cân nhắc về một thang đo các data "được đánh giá cao" 0% (là data ít giá trị cho model học) - 100% (là data thực sự góp phần có ích cho model học)
+ w1/bbox_polygon/G02/G02_B029.jpg (frame 4), bình thường
+ w1/bbox_polygon/G02/G02_B030.jpg (frame 5), bình thường
+ w1/bbox_polygon/G02/G02_B031.jpg (frame 6), bình thường
+ w1/bbox_polygon/G02/G02_B032.jpg (frame 7), tự dự đoán đường kẻ single white line và drivable/alternative area kẻ xuyên ảnh
+ w1/bbox_polygon/G02/G02_B033.jpg (frame 8), bình thường
+ w1/bbox_polygon/G02/G02_B034.jpg (frame 9), bình thường 
+ w1/bbox_polygon/G02/G02_B035.jpg (frame 10), bức ảnh trời tối
+ w1/bbox_polygon/G02/G02_B036.jpg (frame 11), bình thường 
+ w1/bbox_polygon/G02/G02_B037.jpg (frame 12), bình thường
+ w1/bbox_polygon/G02/G02_B038.jpg (frame 13), ảnh trời tối
+ w1/bbox_polygon/G02/G02_B039.jpg (frame 14), bình thường
+ w1/bbox_polygon/G02/G02_B040.jpg (frame 15), bình thường
+ w1/bbox_polygon/G02/G02_B041.jpg (frame 16), trời mưa, pov từ cam hành trình nên có nhiều điểm mưa che pixel và mờ xe xa hơn
+ w1/bbox_polygon/G02/G02_B042.jpg (frame 17), bình thường 
+ w1/bbox_polygon/G02/G02_B043.jpg (frame 18), bình thường
+ w1/bbox_polygon/G02/G02_B044.jpg (frame 19), bình thường
+ w1/bbox_polygon/G02/G02_B045.jpg (frame 20), bình thường
+ w1/bbox_polygon/G02/G02_B046.jpg (frame 21), bình thường
+ w1/bbox_polygon/G02/G02_B047.jpg (frame 22), ảnh trời tối + đèn mờ làm vật xa khó định nghĩa hơn
+ w1/bbox_polygon/G02/G02_B048.jpg (frame 23), bình thường
+ w1/bbox_polygon/G02/G02_B049.jpg (frame 24), ảnh trời tối + đèn chói và mờ làm vật xa khó định nghĩa hơn
+ w1/bbox_polygon/G02/G02_B050.jpg (frame 25), bình thường

### Segmentation
+ w1/segmentation/G02/G02_S026.jpg (frame 1), vì pov ở cam hành trình nên dính mũi xe và đang không rõ phải segment phần mũi xe là gì; trong ảnh là một đường 2 chiều với hàng cây ở giữa, hàng cây giữa với hàng cây bên lề dính với nhau (trong pixel ảnh), nên câu hỏi là 2 ID cây khác nhau có giúp ích cho mục đích học máy không 

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
*Reviewer will cross-link back to this file from `long-review-hhuy.md`.*
