# Nhật ký tuần 01 · 14/09 – 20/09/2026

> **File ví dụ** — tên, số liệu và link đều là giả. Tuần mới thì copy
> [`_mau-tuan.md`](_mau-tuan.md) thành `tuan-02.md`.
> Tuần này kiểu data: **2D** (tuần đầu 3 tuần: 2D → Keypoint → 3D LiDAR).

**Lead tuần này:** @thanh-vien-a
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
| Nguyễn Văn A (@thanh-vien-a) | Lead | Chia job, chốt edge case, review xác suất 10% mọi job |
| Trần Thị B (@thanh-vien-b) | Annotator | Job 101, 102 |
| Lê Văn C (@thanh-vien-c) | Annotator | Job 103, 104 |
| Phạm Thị D (@thanh-vien-d) | Reviewer · Annotator | Review job 101–104; gán job 105 |
| Mạnh (@) | **Nhóm trưởng Seg** | 25 ảnh Seg — review PHuy (vòng) |
| Cường (@) | **Nhóm trưởng BBox** | 25 ảnh BBox — review Mạnh (vòng) |

> Phạm Thị D vừa review vừa gán, nên job 105 do Lead review.

## Vòng review cố định

`HHuy → Long → PHuy → Mạnh → Cường → HHuy` — xem [`phan-cong-review.md`](../phan-cong-review.md).

## Công việc

| # | Nội dung công việc | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | Job 101 — 250 ảnh, bbox `xe_may` / `o_to` / `nguoi` | @thanh-vien-b | @thanh-vien-d | ✅ 100% | Review trả lại 12 ảnh, đã sửa xong |
| 2 | Job 102 — 250 ảnh, cùng nhãn | @thanh-vien-b | @thanh-vien-d | 🟡 70% |  |
| 3 | Job 103 — 250 ảnh, cùng nhãn | @thanh-vien-c | @thanh-vien-d | ⛔ 30% | Dừng, chờ chốt [P-002](../problem-backlog.md#p-002) |
| 4 | Job 104 — 250 ảnh, cùng nhãn | @thanh-vien-c | @thanh-vien-d | ⬜ 0% | Làm sau job 103 |
| 5 | Job 105 — 250 ảnh, cùng nhãn | @thanh-vien-d | @thanh-vien-a | 🟡 40% |  |
| 6 | Đọc lại guideline §3, gom các ca chưa rõ | @thanh-vien-a | — | ✅ 100% | Ra P-001, P-002 |
| 7 | Rà lại job 101 theo QĐ-001 | @thanh-vien-b | @thanh-vien-d | ✅ 100% | Sửa 37 ảnh người ngồi sau |
| 8 | Mạnh — nhóm trưởng Seg (25 ảnh Seg) | Mạnh (@) | — | ⬜ 0% | Nhóm trưởng Seg, review theo vòng PHuy |
| 9 | Cường — nhóm trưởng BBox (25 ảnh BBox) | Cường (@) | — | ⬜ 0% | Nhóm trưởng BBox, review theo vòng Mạnh |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đang làm (ghi %) · ⛔ bị chặn (ghi lý do) · ⬜ chưa bắt đầu

## Tổng kết

- Đã gán: 425 / 1.250 ảnh (34%) — cộng thêm Mạnh 25 Seg + Cường 25 BBox = **475/1275**
- Qua review lần đầu: 88% (trả lại 51 ảnh)
- Edge case mới: P-001, P-002, P-003 — đã chốt P-001 thành [QĐ-001](../so-quyet-dinh.md#qđ-001)
- Nhóm trưởng tuần 01: **Mạnh (Seg)** · **Cường (BBox)**

## Vướng mắc

- P-002 (xe bị che khuất) chưa chốt nên job 103 phải dừng. Lead đã gửi câu hỏi lên BTC.
- P-003: vẽ lại box y hệt qua các frame liên tiếp mất ~40% thời gian job 105.
  Đang cân nhắc làm tool trong [`source-tool/`](../source-tool/).

## Kế hoạch tuần 02

- Chốt P-002, mở lại job 103.
- Xong job 102, 104, 105.
- Quyết định có làm tool cho P-003 hay dùng chế độ Track sẵn có của CVAT.
- Tuần 02: Human Keypoint — cập nhật nhóm trưởng (random hoặc chốt lại).
