# Nhật ký tuần 01 · 14/09 – 20/09/2026

> **File ví dụ** — tên và số liệu đều giả. Tuần mới thì copy [`_mau-tuan.md`](_mau-tuan.md) thành `tuan-02.md`.
> Tuần này kiểu data: **2D** (tuần đầu 3 tuần: 2D → Keypoint → 3D LiDAR).

**Lead tuần này:** @
**Dữ liệu / task CVAT:** Ảnh giao thông đô thị — [task 12](https://cvat.example.com/tasks/12)

## Nhóm trưởng tuần 01 (chỉ làm 25 ảnh / 1 task)

| Nhóm trưởng | Task | Số ảnh | Ghi chú |
|---|---|---|---|
| **Mạnh** | Task A — Semantic Segmentation | 25 | Nhóm trưởng Seg, review theo vòng PHuy |
| **Cường** | Task B — BBox/Polygon/Polyline | 25 | Nhóm trưởng BBox, review theo vòng Mạnh |

> Mạnh và Cường chỉ gán 25 ảnh mỗi người nhưng vẫn **review đủ 50 ảnh** của người trước theo vòng cố định.

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
|  | Lead | Chia job, chốt edge case, review xác suất 10% mọi job |
| HHuy | Annotator | 50 ảnh (25+25) — person-bit 16:00, review Cường 20:00 |
| Long | Annotator | 50 ảnh (25+25) — review HHuy, person-bit 16:00/20:00 |
| PHuy | Annotator | 50 ảnh (25+25) — review Mạnh (nhóm trưởng Seg), person-bit 16:00/20:00 |
| Mạnh | **Nhóm trưởng Seg** | 25 ảnh Seg — review PHuy (vòng) |
| Cường | **Nhóm trưởng BBox** | 25 ảnh BBox — review Mạnh (vòng) |

> Review rotation: `HHuy → Long → PHuy → Mạnh → Cường → HHuy` — xem [`phan-cong-review.md`](phan-cong-review.md).

## Công việc

| # | Nội dung công việc | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | T2 Nhận Job — Lead chia batch | — | — | ⬜ 0% | 25+25 / người |
| 2 | T3 Gán đợt 1 | @HHuy, @Long, @PHuy, @Mạnh, @Cường | @Long, @PHuy, @Mạnh, @Cường, @HHuy | 🟡 Số lượng chưa báo cáo | Đã nhận đủ 5 person-bit annotate; không dùng review trong tổng hợp này |
| 3 | T4 Nộp phần đầu + Report | Mỗi người | Mỗi người | ⬜ 0% | review T4 xong trước 21:00 để họp T5 |
| 4 | T5 Mentor Duty 1 — họp online | Lead | — | ⬜ 0% | dùng § Duty 1 trong `tuan-01.md` |
| 5 | T6 Gán đợt 2 | Mỗi người | Mỗi người | ⬜ 0% | 16:00/20:00 |
| 6 | T7 Đóng batch trước 20:00 | Mỗi người | Mỗi người | ⬜ 0% | |
| 7 | CN Mentor Duty 2 — chốt tuần | Lead | — | ⬜ 0% | dùng § Duty 2 trong `tuan-01.md` |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đang làm (ghi %) · ⛔ bị chặn (ghi P-xxx) · ⬜ chưa bắt đầu

## Tổng kết

### Tổng hợp annotate — 15/09/2026

| Annotator | Task A (Seg) | Task B (BBox/Poly) | Tổng | Trạng thái / ghi nhận |
|---|---:|---:|---:|---|
| HHuy | Chưa báo cáo / 25 | Chưa báo cáo / 25 | Chưa báo cáo / 50 | Ghi nhận vướng mắc về phạm vi area, class đối tượng và ảnh tối/mưa |
| Long | Chưa báo cáo / 25 | Chưa báo cáo / 25 | Chưa báo cáo / 50 | Ghi nhận vướng mắc về biển báo, cầu, hàng rào, ranh giới khu vực lái và xe chỉ thấy đèn |
| PHuy | Chưa báo cáo / 25 | Chưa báo cáo / 25 | Chưa báo cáo / 50 | Báo blocker về pixel không thuộc 19 class |
| Mạnh | Chưa báo cáo / 25 | — | Chưa báo cáo / 25 | Ghi nhận ca che khuất, ánh sáng kém và ranh giới road/sidewalk |
| Cường | — | Chưa báo cáo / 25 | Chưa báo cáo / 25 | Ghi nhận vướng mắc về line, road curb và alternative area |
| **Tổng** | **Chưa báo cáo / 100** | **Chưa báo cáo / 100** | **Chưa báo cáo / 200** | Tổng quota theo phân công: 200 ảnh |

- Đã nhận: 5/5 person-bit annotate.
- Số ảnh đã gán: chưa thể tổng hợp vì cả 5 file để trống trường `Numbers`.
- Review: không tổng hợp theo phạm vi báo cáo annotate.
- Edge case mới: P-004 đến P-008 đang mở; chưa có quyết định mới.
- Ảnh tệ: chỉ HHuy đề cập G02_B028 là near-terrible; chưa có đề xuất keep/drop/ask trong mục `Terrible frames`.

## Vướng mắc

- P-004: Quy tắc phân biệt và vẽ `drivable area`, `alternative area`, road curb và line marking.
- P-005: Phạm vi class BBox/Polygon cho biển tên đường, traffic light, cầu, hàng rào và vật thể chỉ thấy một phần.
- P-006: Cách xử lý biên không nhìn rõ do tối, mưa, phản xạ, mờ hoặc che khuất.
- P-007: Label segmentation cho vật thể/pixel ngoài 19 class, gồm tuyết, cầu, barrier, cone và bollard.
- P-008: Quy tắc segmentation cho road/sidewalk bị che, phản chiếu, lóa hoặc khó phân ranh giới.

## Kế hoạch tuần 02

- Chốt P-xxx, mở lại job bị dừng.
- Tuần 02: Human Keypoint — cập nhật nhóm trưởng (random hoặc chốt lại).
- Vòng review: giữ nguyên `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
