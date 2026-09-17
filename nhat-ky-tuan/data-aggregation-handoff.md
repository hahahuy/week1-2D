# Handoff — Data Aggregation Agent

**Created:** 2026-09-16
**Purpose:** Guide the next agent on how to read person-bits from annotators/reviewers and populate tracking documents.

---

## What you read

Every day, read these files from `nhat-ky-job/`:

| File | What it contains | Who wrote it |
|---|---|---|
| `hhuy-annotate.md` | Progress, terrible frames, blockers | HHuy |
| `long-annotate.md` | Progress, terrible frames, blockers | Long |
| `phuy-annotate.md` | Progress, terrible frames, blockers | PHuy |
| `manh-annotate.md` | Progress (25 imgs only), blockers | Mạnh |
| `cuong-annotate.md` | Progress (25 imgs only), blockers | Cường |
| `long-review-hhuy.md` | Verdict, errors found, agree/disagree on terrible frames | Long (reviewer of HHuy) |
| `phuy-review-long.md` | Same | PHuy |
| `manh-review-phuy.md` | Same | Mạnh |
| `cuong-review-manh.md` | Same | Cường |
| `hhuy-review-cuong.md` | Same | HHuy |

Each annotate file has this structure:
```
## Metadata → date, annotator handle, reviewer handle, cross-link
## Numbers → Task A: _/25, Task B: _/25, Total: _/50
## What happened → prose about patterns, confusion, errors, P-xxx references
## Terrible frames → prose: frame link + why terrible + keep/drop/ask
## Blocker → yes/no + P-xxx if applicable
```

Each review file has:
```
## Metadata → date, reviewer, annotator, source file link
## Numbers → Task A: _/25 reviewed, sample check %, Total: _/50
## What you found → prose about quality, systematic errors
## Terrible frames — agree/disagree → prose
## Verdict → Pass / Return / Pass with conditions
## Escalate to P-xxx? → yes/no
## Suggestion for tomorrow → prose
```

---

## What you extract

From each person-bit, extract these data points:

### Per person per day:
1. **Task A count** (done/ludget)
2. **Task B count** (done/ludget)
3. **Total count** (done/ludget)
4. **Blocker status** (yes/no + P-xxx code if yes)
5. **Verdict** (from review file: Pass/Return/Pass with conditions)
6. **P-xxx references** (any mentioned in "What happened" or "Blocker")
7. **Terrible frame proposals** (frame links + keep/drop/ask)
8. **Reviewer agreement** (on terrible frames — agree/disagree)

### Per week aggregation (for Duty 1/2):
- Sum all person-bits from T2→T4 (Duty 1) or T6→T7 (Duty 2)
- Total images assigned: _/250 (5 people × 50, minus group leaders' 25 each = 475)
- Review pass rate: _% (how many passed on first review)
- Images returned: _ (how many were returned)

---

## Where you write

### 1. `nhat-ky-tuan/tuan-01.md` (Week 01 weekly log)

**§ Duty 1** (T5, after T4 review done by 21:00):
- Aggregate all person-bits T2→T4 into a table:
  - Per person: Task A done, Task B done, Total done, Reviewer, Pass %, Blocker
  - Total team: _/250 images assigned
- Summarize blockers, P-xxx raised
- List questions for mentor họp

**§ Duty 2** (CN, after T7 20:00):
- Aggregate all person-bits T6→T7
- Weekly totals: _/250 assigned, _% passed review
- Edge case summary: P-xxx resolved/chốt

### 2. `problem-backlog.md` (Edge cases)

When an annotator mentions a guideline gap in "What happened" section:
1. Check if P-xxx already exists in the backlog
2. If not, create new entry:
   - Code: `P-NNN` (next available number)
   - Type: `Guideline mơ hồ` / `Guideline chưa nói tới` / `Pain point công cụ`
   - Description from annotator's prose
   - Frame links if any
   - Status: `🔴 Mở`
3. Update the summary table at the top of `problem-backlog.md`

### 3. `so-quyet-dinh.md` (Decisions)

When a P-xxx gets chốt (resolved):
1. Create new QĐ entry:
   - Code: `QĐ-NNN`
   - Summary of the decision
   - Origin: `P-xxx` reference
   - Date chốt
   - What applies going forward
2. Update `problem-backlog.md`: change P-xxx status to `✅ Đã chốt → QĐ-xxx`

---

## Workflow per day

```
Morning (T3/T6):
  1. Check nhat-ky-job/ for all 5 *_annotate.md files from yesterday
  2. Verify all 5 exist before 16:00 deadline
  3. If any missing → contact the person

Afternoon (T3/T6 evening):
  4. Check for all 5 *_review-*.md files
  5. Verify cross-links are correct (review file links to annotate file)
  6. Verify no self-review (annotator ≠ reviewer)
  7. Verify rotation matches: HHuy→Long→PHuy→Mạnh→Cường→HHuy

Weekly (T5 morning):
  8. Aggregate T2→T4 person-bits → fill § Duty 1 in tuan-01.md
  9. Present to mentor họp

Weekly (CN):
  10. Aggregate T6→T7 person-bits → fill § Duty 2 in tuan-01.md
  11. Update problem-backlog.md and so-quyet-dinh.md
```

---

## Key rules

- **Annotator never guesses** → if guideline unclear, must create P-xxx in person-bit "What happened"
- **Reviewer never self-resolves P-xxx** → mentor confirms
- **Link chéo mandatory** → every review file must link to its annotate source
- **No self-review** → annotator ≠ reviewer in every file pair
- **Deadline hard** → annotate 16:00, review 20:00, T4 review 21:00, T7 batch 20:00
- **Group leaders**: Mạnh (25 imgs Seg) + Cường (25 imgs BBox) review 50 imgs each

---

## Rotation reference

```
HHuy → Long → PHuy → Mạnh → Cường → HHuy
```
- Long reviews HHuy
- PHuy reviews Long
- Mạnh reviews PHuy
- Cường reviews Mạnh
- HHuy reviews Cường

---

*This document lives alongside the repo. Read all 5 person-bits per day, extract numbers, and populate tracking docs. The person-bits are the single source of truth.*
