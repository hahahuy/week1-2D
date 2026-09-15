# Phân công review — vòng cố định 3 tuần

> **Vòng cố định:** `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
> Nghĩa: Long review HHuy, PHuy review Long, Mạnh review PHuy, Cường review Mạnh, HHuy review Cường.
> **Không tự review.** Không đổi vòng giữa chừng (trừ khi Lead ghi QĐ mới).

**Handle GitHub:** đang để `@empty` — thay bằng handle thật khi có (ví dụ `@hhuy`).

| # | Annotator | Handle | Reviewer | Handle reviewer | Batch tuần |
|---|---|---|---|---|---|
| 1 | HHuy | @empty | Long | @empty | 50 ảnh (25+25) |
| 2 | Long | @empty | PHuy | @empty | 50 ảnh |
| 3 | PHuy | @empty | Mạnh* | @empty | 50 ảnh — **nhóm trưởng Seg (25)** |
| 4 | Mạnh* | @empty | Cường* | @empty | 50 ảnh — **nhóm trưởng BBox (25)** |
| 5 | Cường* | @empty | HHuy | @empty | 50 ảnh — **nhóm trưởng BBox (25)** |

> Mạnh và Cường là nhóm trưởng tuần 01: Mạnh làm 25 ảnh Seg, Cường làm 25 ảnh BBox.
> Mạnh vẫn review PHuy (vòng cố định), Cường vẫn review Mạnh (vòng cố định).
> Nhóm trưởng review đủ 50 ảnh của người trước dù chỉ gán 25.

**Nhóm trưởng tuần hiện tại (chỉ làm 25 ảnh / 1 task):**

| Tuần | Kiểu data | Nhóm trưởng Task A (Seg) | Nhóm trưởng Task B (BBox/Poly) | Ghi chú |
|---|---|---|---|---|
| 01 · 14–20/09/2026 | 2D | **Mạnh** (25 ảnh) | **Cường** (25 ảnh) | Chốt, không random |

## Tracking theo tuần (Lead cập nhật T7/CN)

### Tuần 01 · 14–20/09/2026 · 2D

| Annotator | Reviewer | T3 | T4 (nộp phần đầu) | T6 | T7 (đóng 20:00) | Cả tuần | Trạng thái |
|---|---|---|---|---|---|---|---|
| HHuy | Long | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Long | PHuy | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| PHuy | Mạnh | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Mạnh | Cường | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Cường | HHuy | ⬜ | ⬜ | ⬜ | _/50 | _/50 | ⬜ |

### Tuần 02 · 21–27/09/2026 · Human Keypoint

| Annotator | Reviewer | T3 | T4 | T6 | T7 | Cả tuần | Trạng thái |
|---|---|---|---|---|---|---|---|
| HHuy | Long | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Long | PHuy | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| PHuy | Mạnh | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Mạnh | Cường | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Cường | HHuy | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |

### Tuần 03 · 28/09–04/10/2026 · 3D LiDAR

| Annotator | Reviewer | T3 | T4 | T6 | T7 | Cả tuần | Trạng thái |
|---|---|---|---|---|---|---|---|
| HHuy | Long | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Long | PHuy | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| PHuy | Mạnh | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Mạnh | Cường | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |
| Cường | HHuy | ⬜ | ⬜ | ⬜ | ⬜ | _/50 | ⬜ |

Mức: ✅ xong và đã qua review · 🟡 đang làm · ⛔ bị chặn (P-xxx) · ⬜ chưa bắt đầu

## Quy ước person-bit hàng ngày

- **Annotate deadline 16:00** — `nhat-ky-job/YYYY-MM-DD/<ten>-annotate.md` (làm nhiêu nộp bấy)
- **Review deadline 20:00** — `nhat-ky-job/YYYY-MM-DD/<reviewer>-review-<annotator>.md`
- **T4 review phải xong trước 21:00** để có số liệu họp Duty 1 (T5)
- Link chéo bắt buộc cùng ngày: annotate → review và review → annotate

## Khi nào đổi vòng?

Mặc định **không đổi**. Nếu cần đổi (người nghỉ, bias), Lead ghi `QĐ-xxx` trong [`so-quyet-dinh.md`](so-quyet-dinh.md) và cập nhật bảng trên.
