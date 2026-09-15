# Nhật ký tuần NN · dd/mm – dd/mm/yyyy

> Copy file này thành `tuan-NN.md` mỗi đầu tuần (T2).
> Tuần này kiểu data: 2D / Human Keypoint / 3D LiDAR — điền vào dòng dưới.

**Lead tuần này:** @
**Dữ liệu / task CVAT:** `https://…/tasks/<id>` — Task A: Semantic Segmentation (25 ảnh/ng) · Task B: BBox/Polygon/Polyline (25 ảnh/ng)
**Nhóm trưởng tuần này (chỉ làm 25 ảnh):** Task A: @__ · Task B: @__
**Kiểu data tuần này:** 2D / Keypoint / 3D LiDAR

## Vòng review cố định (không đổi 3 tuần)

`HHuy → Long → PHuy → Mạnh → Cường → HHuy` — xem [`phan-cong-review.md`](../phan-cong-review.md).
Mỗi `person-bit annotate` link tới `person-bit review` cùng ngày trong [`nhat-ky-job/`](nhat-ky-job/).

| Annotator | Reviewer | Batch tuần này |
|---|---|---|
| HHuy (@) | Long (@) | 50 ảnh (25+25) — nhóm trưởng 25 |
| Long (@) | PHuy (@) | 50 ảnh |
| PHuy (@) | Mạnh (@) | 50 ảnh |
| Mạnh (@) | Cường (@) | 50 ảnh |
| Cường (@) | HHuy (@) | 50 ảnh |

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
|  | Lead | Chia job T2, tổng hợp Duty 1 (T5) + Duty 2 (CN), giữ `so-quyet-dinh.md` |
|  | Annotator | 50 ảnh (25+25) — person-bit annotate hàng ngày trước 16:00 |
|  | Annotator | 50 ảnh |
|  | Annotator | 50 ảnh |
|  | Reviewer (kiêm Annotator) | Review person-bit của người trước, xong trước 20:00 hàng ngày |

> Nhóm trưởng chỉ làm 25 ảnh (1 task) nhưng vẫn review đủ 50 ảnh của người trước.

## Công việc (theo cadence T2→CN)

| # | Nội dung | Annotator | Reviewer | Hoàn thành | Ghi chú |
|---|---|---|---|---|---|
| 1 | T2 Nhận Job — Lead chia batch | — | — | ⬜ 0% | 25+25 / người |
| 2 | T3 Gán đợt 1 | @ | @ | ⬜ 0% | person-bit `nhat-ky-job/YYYY-MM-DD/` 16:00/20:00 |
| 3 | T4 Nộp phần đầu (làm nhiêu nộp bấy) + Report | @ | @ | ⬜ 0% | review T4 xong trước 21:00 để họp T5 |
| 4 | T5 Mentor Duty 1 — họp online | Lead | — | ⬜ 0% | dùng `_mau-duty-1.md` |
| 5 | T6 Gán đợt 2 | @ | @ | ⬜ 0% | 16:00/20:00 |
| 6 | T7 Đóng batch trước 20:00 | @ | @ | ⬜ 0% |  |
| 7 | CN Mentor Duty 2 — chốt tuần | Lead | — | ⬜ 0% | dùng `_mau-duty-2.md` |

Mức hoàn thành: ✅ xong **và đã qua review** · 🟡 đang làm (ghi %) · ⛔ bị chặn (ghi P-xxx) · ⬜ chưa bắt đầu

## Duty 1 — T5 (tổng hợp T2→T4, copy từ `_mau-duty-1.md` hoặc link tới file duty)

> Lead điền sau khi review T4 xong trước 21:00 T4. Dùng để họp mentor T5.

- Link report Duty 1: `./tuan-NN-duty-1.md` hoặc điền trực tiếp dưới đây
- Tóm tắt: … (sẽ aggregate từ `nhat-ky-job/`)

## Duty 2 — CN (tổng hợp T6→T7, copy từ `_mau-duty-2.md`)

> Lead điền sau T7 20:00.

- Link report Duty 2: `./tuan-NN-duty-2.md` hoặc điền trực tiếp
- Tóm tắt: …

## Tổng kết (sau Duty 2)

- Đã gán: _ / 250 ảnh (_%) — 5 người × 50 (nhóm trưởng × 25)
- Qua review lần đầu: _% (trả lại _ ảnh)
- Edge case mới / đã chốt: P-xxx → QĐ-xxx
- Ảnh tệ: _ đề xuất → _ đồng ý bỏ/giữ

## Vướng mắc

- … (P-xxx nào chưa chốt, job nào dừng, đã hỏi mentor/BTC chưa)

## Kế hoạch tuần sau

- Kiểu data tuần sau: …
- Nhóm trưởng tuần sau (random T2): Task A: @__, Task B: @__
- Vòng review: giữ nguyên `HHuy → Long → PHuy → Mạnh → Cường → HHuy`

---
### Cách aggregate person-bit vào tuần (cho Lead)

```bash
# Đếm person-bit đã nộp
ls nhat-ky-job/2026-09-1*/*-annotate.md nhat-ky-job/2026-09-1*/*-review-*.md 2>/dev/null | wc -l
# Hoặc mở từng ngày YYYY-MM-DD và copy 4 số vào bảng Duty 1/2
```

*Person-bit hàng ngày ở [`nhat-ky-job/`](nhat-ky-job/) — mỗi annotate trước 16:00, review trước 20:00, link chéo cùng ngày.*
