# Person-bit Review — @<reviewer> review @<annotator> — YYYY-MM-DD

> Copy file này thành `<reviewer>-review-<annotator>.md` trong `nhat-ky-job/YYYY-MM-DD/`.
> Viết **sau 16:00**, xong **trước 20:00** cùng ngày. Review hàng ngày, không dồn T7.

**Ngày:** YYYY-MM-DD
**Reviewer:** @<reviewer>
**Annotator:** @<annotator>
**Vòng cố định:** xem [`phan-cong-review.md`](../../phan-cong-review.md) — `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
**File annotate nguồn:** `../YYYY-MM-DD/<annotator>-annotate.md` (bắt buộc link chéo)

## Đã review

| Task | Đã review | Mẫu kiểm | Link CVAT |
|---|---|---|---|
| A — Semantic Segmentation | _ / 25 | _% | `https://…/jobs/<id>?frame=<n>` |
| B — BBox / Polygon / Polyline | _ / 25 | _% | `https://…/jobs/<id>?frame=<n>` |
| **Tổng** | **_ / 50** | | |

> Nhóm trưởng annotate chỉ 25 ảnh thì review vẫn đủ số ảnh của annotator (50).

## Trả lại

| # | Link frame | Lỗi | § guideline / QĐ | Mức |
|---|---|---|---|---|
| 1 | `https://…/jobs/<id>?frame=<n>` | … | § / QĐ-xxx | lẻ tẻ / hệ thống |
| 2 | | | | |

**Kết luận:** [ ] Pass — dưới 10% mẫu kiểm sai · [ ] Trả nguyên job — trên 10% (theo QĐ-002) · [ ] Pass có điều kiện — sửa _ ảnh lẻ

## Ảnh tệ — đồng ý / không đồng ý với annotator

| # | Frame annotator đề xuất | Đồng ý? | Lý do |
|---|---|---|---|
| 1 | `frame=<n>` — đề xuất bỏ | ✅ / ❌ | … |
| 2 | | | |

> Nếu cả hai đồng ý bỏ nhưng chưa có guideline, ghi `P-xxx` để chốt ở Duty 1/2. Không tự bỏ.

## Góp ý cho annotate ngày mai

- … (1–2 dòng, pattern lỗi hệ thống cần tránh)

## Cần escalate thành P-xxx?

- [ ] Không
- [ ] Có — `P-xxx`: … (link tới backlog, mô tả ngắn)

---
*Link chéo: file này phải được trỏ tới từ `<annotator>-annotate.md` cùng ngày.*
