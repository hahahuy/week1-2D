# Problem backlog

Những chỗ gặp trong lúc gán nhãn mà **guideline chưa trả lời được**, cộng các pain point về công cụ.

Ghi ngay khi gặp, kể cả lúc chưa biết xử lý thế nào. Một edge case không được ghi lại thì
mỗi người sẽ tự xử lý theo một kiểu — và đó là nguồn lớn nhất của nhãn không nhất quán.

> Các mục bên dưới là **ví dụ**, tên và link CVAT đều giả. Mẫu trống để copy nằm cuối file.

## Danh sách

| Mã | Tóm tắt | Loại | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|
| [P-001](#p-001) | Người ngồi sau xe máy: box riêng hay gộp với người lái | Guideline mơ hồ | §3.2 | ✅ Đã chốt | [QĐ-001](so-quyet-dinh.md#qđ-001) |
| [P-002](#p-002) | Xe bị che khuất hơn một nửa | Guideline chưa nói tới | §3.4 | ↗️ Hỏi BTC | — |
| [P-003](#p-003) | Phải vẽ lại box y hệt qua nhiều frame liên tiếp | Pain point công cụ | — | 🗣️ Đang bàn | — |
| [P-004](#p-004) | Phân biệt area, road curb và line marking | Guideline mơ hồ | — | 🔴 Mở | — |
| [P-005](#p-005) | Class cho đối tượng giao thông hoặc công trình không rõ | Guideline chưa nói tới | — | 🔴 Mở | — |
| [P-006](#p-006) | Gán nhãn khi biên vật thể không nhìn rõ | Guideline mơ hồ | — | 🔴 Mở | — |
| [P-007](#p-007) | Pixel vật thể ngoài 19 class segmentation | Guideline chưa nói tới | — | 🔴 Mở | — |
| [P-008](#p-008) | Ranh giới segmentation road/sidewalk trong điều kiện khó | Guideline mơ hồ | — | 🔴 Mở | — |

**Loại**

| Loại | Nghĩa là |
|---|---|
| Guideline chưa nói tới | Tình huống không có trong guideline |
| Guideline mơ hồ | Đọc guideline ra được hai cách hiểu trở lên |
| Guideline mâu thuẫn | Hai mục trong guideline nói ngược nhau |
| Pain point công cụ | Guideline rõ, nhưng làm trên CVAT chậm hoặc dễ sai |

**Trạng thái:** 🔴 Mở · 🗣️ Đang bàn · ↗️ Hỏi BTC · ✅ Đã chốt (trỏ sang QĐ) · 🛠️ Làm tool (trỏ sang `source-tool/`) · ⚪ Bỏ (ghi lý do)

---

## P-001

**Người ngồi sau xe máy: box riêng hay gộp chung với người lái**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** §3.2 — "mỗi người một bounding box"
- **Người phát hiện:** @thanh-vien-b · 16/09/2026
- **Link CVAT:**
  - https://cvat.example.com/tasks/12/jobs/101?frame=37 — hai người, gần như chồng khít
  - https://cvat.example.com/tasks/12/jobs/101?frame=112 — người ngồi sau chỉ lộ đầu
- **Mô tả:** §3.2 nói mỗi người một box, nhưng hình minh hoạ trong guideline lại vẽ một box
  cho cả xe máy lẫn người trên xe.
- **Các cách hiểu:**
  1. Theo câu chữ: người ngồi sau có box `nguoi` riêng.
  2. Theo hình minh hoạ: không vẽ box `nguoi` cho ai đang ngồi trên xe.
- **Xử lý tạm trong lúc chờ:** vẽ box riêng và gắn tag `can_xem_lai` để dễ lọc ra sửa.
- **Kết quả:** ✅ [QĐ-001](so-quyet-dinh.md#qđ-001)

## P-002

**Xe bị che khuất hơn một nửa**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** §3.4 — chỉ nói về vật thể bị cắt ở mép ảnh, không nói về bị che
- **Người phát hiện:** @thanh-vien-c · 17/09/2026
- **Link CVAT:**
  - https://cvat.example.com/tasks/12/jobs/103?frame=8 — ô tô sau xe buýt, lộ khoảng 30%
  - https://cvat.example.com/tasks/12/jobs/103?frame=64 — xe máy sau cột điện, lộ khoảng 50%
- **Mô tả:** Không rõ có gán nhãn vật thể bị che không, và nếu có thì box ôm phần nhìn thấy
  hay ôm cả phần ước lượng bị che.
- **Các cách hiểu:**
  1. Bỏ qua khi lộ dưới 50%.
  2. Luôn gán, box chỉ ôm phần nhìn thấy.
  3. Luôn gán, box ôm cả phần ước lượng.
- **Xử lý tạm trong lúc chờ:** dừng job 103, chuyển sang job khác ít ca che khuất.
- **Kết quả:** ↗️ Đã hỏi BTC ngày 18/09/2026, chờ trả lời.

## P-003

**Phải vẽ lại box y hệt qua nhiều frame liên tiếp**

- **Loại:** Pain point công cụ
- **Mục guideline:** —
- **Người phát hiện:** @thanh-vien-d · 18/09/2026
- **Link CVAT:** https://cvat.example.com/tasks/12/jobs/105?frame=200 — frame 200–260, xe đỗ không di chuyển
- **Mô tả:** Ảnh chụp liên tiếp từ camera cố định. Xe đỗ bên đường xuất hiện y nguyên ở hàng chục
  frame, annotator phải vẽ lại ở từng frame. Ước tính chiếm ~40% thời gian job 105.
- **Hướng đang cân nhắc:**
  1. Dùng chế độ *Track* sẵn có của CVAT — cần thử xem có hợp với dữ liệu dạng ảnh rời không.
  2. Viết script đọc file export của CVAT, nhân box sang các frame kế tiếp, rồi import lại.
- **Kết quả:** 🗣️ Đang bàn. Nếu chọn hướng 2 thì đổi trạng thái sang 🛠️ và làm trong
  [`source-tool/`](source-tool/).

---

## P-004

**Phân biệt và vẽ area, road curb và line marking**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** —
- **Người phát hiện:** @HHuy, @Cường · 15/09/2026
- **Link CVAT:**
  - `w1/bbox_polygon/G02/G02_B001.jpg`, `G02_B003.jpg`, `G02_B008.jpg`, `G02_B010.jpg`, `G02_B011.jpg`, `G02_B012.jpg`
  - `w1/bbox_polygon/G02/G02_B026.jpg`, `G02_B027.jpg`, `G02_B032.jpg`
- **Mô tả:** Chưa rõ ranh giới giữa `drivable area`, `alternative area`, road curb, vạch đơn/vạch đôi, vạch chéo và vạch qua đường. Cũng chưa rõ polyline phải đi theo từng nét vạch hay chỉ theo tim/hướng tuyến.
- **Các cách hiểu:**
  1. Vẽ theo toàn bộ vạch và vùng nhìn thấy.
  2. Vẽ một đường tim hoặc ranh giới ước lượng liên tục.
- **Xử lý tạm trong lúc chờ:** Không tự suy đoán phần không chắc chắn; gắn frame cần rà lại.
- **Kết quả:** 🔴 Mở

## P-005

**Class cho đối tượng giao thông hoặc công trình không rõ**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** —
- **Người phát hiện:** @HHuy, @Long · 15/09/2026
- **Link CVAT:**
  - `w1/bbox_polygon/G02/G02_B026.jpg`, `G02_B027.jpg` — phạm vi `traffic_light`, biển báo chữ và đèn qua đường
  - `w1/bbox_polygon/G02/G02_B051.jpg`, `G02_B061.jpg`, `G02_B063.jpg`, `G02_B067.jpg` — bảng tên đường, cầu vượt và hàng rào
- **Mô tả:** Guideline chưa chốt class hoặc phạm vi annotate cho bảng tên đường, biển có chữ, traffic light gồm cột/đèn, đèn qua đường, cầu vượt và hàng rào.
- **Các cách hiểu:**
  1. Gán vào class gần nhất đang có.
  2. Không gán khi guideline chưa định nghĩa class/phạm vi.
- **Xử lý tạm trong lúc chờ:** Đánh dấu frame cần mentor chốt, không tự tạo class mới.
- **Kết quả:** 🔴 Mở

## P-006

**Gán nhãn khi biên vật thể không nhìn rõ**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** —
- **Người phát hiện:** @HHuy, @Long · 15/09/2026
- **Link CVAT:**
  - `w1/bbox_polygon/G02/G02_B028.jpg`, `G02_B035.jpg`, `G02_B041.jpg`, `G02_B047.jpg`, `G02_B049.jpg`
  - `w1/bbox_polygon/G02/G02_B062.jpg`, `G02_B074.jpg`
- **Mô tả:** Trời tối, mưa, phản xạ, ảnh mờ hoặc vật bị che khiến không thể xác định chính xác biên xe, lề đường và vùng lái. Chưa rõ có ước lượng biên, chỉ gán phần thấy rõ, hay bỏ qua vật thể/vùng đó.
- **Các cách hiểu:**
  1. Ước lượng biên theo ngữ cảnh.
  2. Chỉ gán phần nhìn thấy rõ.
  3. Không gán khi không đủ thông tin.
- **Xử lý tạm trong lúc chờ:** Gắn cờ các frame không chắc chắn để rà lại sau khi mentor chốt.
- **Kết quả:** 🔴 Mở

## P-007

**Pixel vật thể ngoài 19 class segmentation**

- **Loại:** Guideline chưa nói tới
- **Mục guideline:** —
- **Người phát hiện:** @PHuy · 17/09/2026
- **Link CVAT:**
  - `w1/segmentation/G02/G02_S079.jpg` — tuyết phủ road/sidewalk
  - `w1/segmentation/G02/G02_S080.jpg`, `G02_S085.jpg` — cầu, bollard; blocker cũng nêu barrier và cone
- **Mô tả:** Dataset có pixel tuyết, cầu, barrier, cone và bollard nhưng không có class tương ứng; guideline cấm tự tạo class `ignore`.
- **Các cách hiểu:**
  1. Gán vào class gần nhất theo bề mặt hoặc hình dạng.
  2. Để pixel không gán nhãn bằng quy ước `ignore`/`unlabeled` do mentor chốt.
- **Xử lý tạm trong lúc chờ:** Dừng quyết định label các pixel ngoài taxonomy; cần mentor chốt quy tắc chung cho batch.
- **Kết quả:** 🔴 Mở

## P-008

**Ranh giới segmentation road/sidewalk trong điều kiện khó**

- **Loại:** Guideline mơ hồ
- **Mục guideline:** —
- **Người phát hiện:** @Mạnh, @PHuy, @HHuy · 15/09/2026–17/09/2026
- **Link CVAT:**
  - `w1/segmentation/G02/G02_S003.jpg`, `G02_S004.jpg`, `G02_S005.jpg`, `G02_S007.jpg`, `G02_S008.jpg`, `G02_S011.jpg`, `G02_S023.jpg`
  - `w1/segmentation/G02/G02_S077.jpg`, `G02_S084.jpg`, `G02_S085.jpg`, `G02_S026.jpg`
- **Mô tả:** Che khuất, lóa, phản chiếu mặt đường, mưa, vỉa hè cùng màu road và mũi xe trong khung hình làm ranh giới segmentation không rõ. Chưa có quy tắc thống nhất cho phần bị che, phần phản chiếu hoặc biên ước lượng.
- **Các cách hiểu:**
  1. Chỉ tô pixel nhìn thấy rõ.
  2. Nội suy theo bề mặt/ngữ cảnh khi biên bị che hoặc lóa.
- **Xử lý tạm trong lúc chờ:** Giữ các frame làm ví dụ để mentor chốt một quy tắc áp dụng thống nhất.
- **Kết quả:** 🔴 Mở

---

## Mẫu để copy

```markdown
## P-NNN

**Tóm tắt một dòng**

- **Loại:** Guideline chưa nói tới | Guideline mơ hồ | Guideline mâu thuẫn | Pain point công cụ
- **Mục guideline:** §
- **Người phát hiện:** @ · dd/mm/yyyy
- **Link CVAT:** (bỏ trống nếu không có)
  - https://…/tasks/<id>/jobs/<id>?frame=<n> — frame này có gì
- **Mô tả:**
- **Các cách hiểu:** (với pain point công cụ thì ghi **Hướng đang cân nhắc:**)
  1.
  2.
- **Xử lý tạm trong lúc chờ:**
- **Kết quả:** 🔴 Mở
```

Nhớ thêm một dòng vào bảng **Danh sách** ở đầu file.
