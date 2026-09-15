# Person-bit Review — @<reviewer> review @<annotator> — YYYY-MM-DD

> Copy file này thành `<reviewer>-review-<annotator>.md` trong `nhat-ky-job/YYYY-MM-DD/`.
> Viết **sau 16:00**, xong **trước 20:00** cùng ngày. Review hàng ngày, không dồn T7.

## Metadata

- **Ngày:** YYYY-MM-DD
- **Reviewer:** @<reviewer>
- **Annotator:** @<annotator>
- **Vòng cố định:** xem [`phan-cong-review.md`](../../phan-cong-review.md) — `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
- **Source annotate file:** `<annotator>-annotate.md` (bắt buộc link chéo)

## Numbers

- Task A (Seg): _ / 25 reviewed (sample check: _%)
- Task B (BBox/Poly): _ / 25 reviewed (sample check: _%)
- **Total: _ / 50**

## What you found

[Free prose. 3–5 sentences. Cover:
- Overall quality impression (good patterns, common mistakes)
- Systematic errors vs one-off mistakes
- Which frames (link) had errors and what guideline/section applies
- What the annotator got right that should continue]

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
*Cross-link: this file must be referenced from `<annotator>-annotate.md` same day.*
