# Nhật ký tuần NN · dd/mm – dd/mm/yyyy

> Copy file này thành `tuan-NN.md` mỗi đầu tuần (T2).
> Tuần này kiểu data: 2D / Human Keypoint / 3D LiDAR — điền vào dòng dưới.

**Lead tuần này:** @
**Dữ liệu / task CVAT:** `https://…/tasks/<id>`
**Nhóm trưởng tuần này:** xem [`phan-cong-review.md`](../phan-cong-review.md)
**Kiểu data tuần này:** 2D / Keypoint / 3D LiDAR

## Vòng review cố định

`HHuy → Long → PHuy → Mạnh → Cường → HHuy` — xem [`phan-cong-review.md`](../phan-cong-review.md).

| Annotator | Reviewer | Batch tuần này | Ghi chú |
|---|---|---|---|
| HHuy (@) | Long (@) | 50 ảnh (25+25) | |
| Long (@) | PHuy (@) | 50 ảnh | |
| PHuy (@) | Mạnh* (@) | 50 ảnh | Mạnh là nhóm trưởng Seg (25 ảnh) |
| Mạnh* (@) | Cường* (@) | 25 ảnh (Seg) + review 50 | **Nhóm trưởng Seg — chỉ gán 25, review đủ 50** |
| Cường* (@) | HHuy (@) | 25 ảnh (BBox) + review 50 | **Nhóm trưởng BBox — chỉ gán 25, review đủ 50** |

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
|  | Lead | Chia job T2, tổng hợp Duty 1 (T5) + Duty 2 (CN), giữ `so-quyet-dinh.md` |
| HHuy | Annotator | 50 ảnh (25+25) — person-bit 16:00, review Cường 20:00 |
| Long | Annotator | 50 ảnh (25+25) — review HHuy, person-bit 16:00/20:00 |
| PHuy | Annotator | 50 ảnh (25+25) — review Mạnh (nhóm trưởng Seg), person-bit 16:00/20:00 |
| Mạnh | **Nhóm trưởng Seg** (25 ảnh Seg) + review PHuy 50 ảnh | Seg 25 ảnh, review theo vòng |
| Cường | **Nhóm trưởng BBox** (25 ảnh BBox) + review Mạnh 50 ảnh | BBox 25 ảnh, review theo vòng |

## Duty 1 — T5 (tổng hợp T2→T4, xem `tuan-NN-duty-1.md` hoặc điền trực tiếp ở dưới)

> Lead điền sau khi review T4 xong trước 21:00 T4. Dùng để họp mentor T5.

- Link report Duty 1: `./tuan-NN-duty-1.md` hoặc điền trực tiếp dưới đây
- Tóm tắt: … (aggregate từ `nhat-ky-job/`)

## Duty 2 — CN (tổng hợp T6→T7, xem `tuan-NN-duty-2.md` hoặc điền trực tiếp)

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
- Nhóm trưởng tuần sau (random T2): Task A: @__ · Task B: @__
- Vòng review: giữ nguyên `HHuy → Long → PHuy → Mạnh → Cường → HHuy`

---
### Cách aggregate person-bit vào tuần (cho Lead)

```bash
ls nhat-ky-job/*-annotate.md nhat-ky-job/*-review-*.md 2>/dev/null | wc -l
```

*Person-bit hàng ngày ở [`nhat-ky-job/`](nhat-ky-job/) — mỗi annotate trước 16:00, review trước 20:00, link chéo cùng ngày.*
