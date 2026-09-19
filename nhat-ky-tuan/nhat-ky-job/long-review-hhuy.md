# Person-bit Review — @Long review @HHuy — 2026-09-15

> Copy file này thành `long-review-hhuy-YYYY-MM-DD.md` trong `nhat-ky-job/`.
> Viết **sau 16:00**, xong **trước 20:00** cùng ngày. Review hàng ngày, không dồn T7.

## Metadata

- **Ngày:** 2026-09-19
- **Reviewer:** @Long
- **Annotator:** @HHuy
- **Vòng cố định:** xem [`phan-cong-review.md`](../../phan-cong-review.md) — `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
- **Source annotate file:** `hhuy-annotate.md` (bắt buộc link chéo)

## Numbers

- Task A (Seg): _ / 25 reviewed (sample check: _%)
- Task B (BBox/Poly): 25 / 25 reviewed (sample check: _%)
- **Total: _ / 50**

## What you found

- Frame: w1/bbox_polygon/G02/G02_B031.jpg: Đánh sai polyline cho cross walk , phải đánh 2 line ở trên và dưới cross walk
- Frame: w1/bbox_polygon/G02/G02_B032.jpg: Không rõ vạch nét đứt là single white hay single other, cần xác nhận và đánh lại
- Frame: w1/bbox_polygon/G02/G02_B038.jpg: Đánh thiếu polyline

## Terrible frames — agree / disagree with annotator

[Free prose. For each frame the annotator flagged as "terrible", state whether you agree or disagree and why. Example:
"Frame 142 — agree, blur makes it untestable, keep. Frame 201 — disagree, person on motorcycle is clearly separable, should have used box for each person per §3.2."]

## Verdict

- [ ] **Pass** — under 10% sample checked wrong
- [ ] **Return whole job** — over 10% sample wrong (per QĐ-002)
- [ ] **Pass with conditions** — fix _ specific frames

## Escalate to P-xxx?

- [ ] No
- [ ] Yes — `P-xxx`: [short description + link to backlog or say "to create"]

## Suggestion for tomorrow

[1–2 lines free prose: what pattern to avoid, what to focus on]

---
*Cross-link: this file must be referenced from `hhuy-annotate.md` same day.*
