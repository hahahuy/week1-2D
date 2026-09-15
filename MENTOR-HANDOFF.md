# Mentor Handoff — Buid-Phase Annotation Program 3 Weeks

## Who this is for

This document is handed to the **next agent acting as MENTOR** for the 5-person annotation team. The agent's role is **NOT** an annotator or reviewer — it is the **guide/mentor** who:

1. Ensures the team works **systematically** (not ad-hoc)
2. Reviews Duty 1 (T5) and Duty 2 (CN) reports
3. Chases open questions / edge cases (P-xxx) to resolution
4. Validates the workflow cadence is being followed
5. Flags blockers early, before they cascade into missed deadlines

---

## Program Overview

| Property | Value |
|---|---|
| **Duration** | 14/09/2026 → 04/10/2026 (3 weeks) |
| **Team** | HHuy - Long - PHuy - Mạnh - Cường (handles: @empty, awaiting real IDs) |
| **Weekly data type** | W1: 2D · W2: Human Keypoint · W3: 3D LiDAR |
| **Tasks** | A: Semantic Segmentation · B: BBox/Polygon/Polyline (25+25=50/pp/week) |
| **Group leaders W1** | **Mạnh** = Task A Seg (25 img) · **Cường** = Task B BBox (25 img) |
| **Round-robin reviewer** | Fixed: `HHuy → Long → PHuy → Mạnh → Cường → HHuy` |
| **Batch deadline** | T7 (Saturday) before **20:00** |
| **Git repos** | `hahahuy/week1-2D`, `hahahuy/week2-humankeypoint`, `hahahuy/week3-Lidarmapping` |

---

## The Cadence — Mentor's Daily/Weekly Checklist

Every week follows this identical cadence. The mentor must verify each step:

```
T2 (Mon)   → Nhận Job. Lead divides batch (50/pp, leaders 25). Mentor: verify split is fair, group leaders confirmed.
T3 (Tue)   → Gán đợt 1. Deadline 16:00. Mentor: check person-bit files exist in nhat-ky-job/YYYY-MM-DD/.
T4 (Wed)   → Nộp phần đầu (làm nhiều nộp bấy). Deadline 16:00 annotate, 20:00 review, 21:00 T4 review must be DONE.
             Mentor: confirm review files link to annotate files. If missing → escalate.
T5 (Thu)   → MENTOR DUTY 1. Họp online. Mentor: present Duty 1 report (aggregate T2→T4).
             Ask: blockers? guideline gaps? edge cases needing P-xxx?
T6 (Fri)   → Gán đợt 2. Deadline 16:00/20:00.
T7 (Sat)   → Đóng batch. DEADLINE 20:00. Mentor: verify all jobs submitted before 20:00.
CN (Sun)   → MENTOR DUTY 2. Chốt tuần. Mentor: present Duty 2 report (T6→T7 + weekly summary).
             Chốt edge cases → create QĐ-xxx in so-quyet-dinh.md.
```

**Mentor mantra:** *"If someone hasn't filed their person-bit by 16:00, ask why. If reviewer hasn't filed by 20:00, ask why. If Duty 1/2 report is missing, the họp is empty — follow up."*

---

## Repository Structure (Mentor Must Know)

```
Build-Phase/
├── week1-2D/                  → repo: hahahuy/week1-2D (branch feat/person-bit-template)
│   ├── README.md              # Main guide — updated with cadence, batch rules, person-bit tree
│   ├── phan-cong-review.md    # Fixed rotation matrix + 3-week tracking tables
│   ├── problem-backlog.md     # Edge cases (P-xxx) — mentor tracks these
│   ├── so-quyet-dinh.md       # Decisions (QĐ-xxx) — mentor confirms resolution
│   ├── source-tool/           # Custom tools for pain points
│   └── nhat-ky-tuan/
│       ├── _mau-tuan.md       # Weekly big report template
│       ├── _mau-duty-1.md     # Duty 1 (T5) report template — aggregate T2→T4
│       ├── _mau-duty-2.md     # Duty 2 (CN) report template — aggregate T6→T7
│       ├── tuan-01.md         # Week 01 example (14-20/09, 2D) — ALREADY FILLED
│       └── nhat-ky-job/
│           ├── _mau-annotate.md   # Person-bit annotate template (16:00 deadline)
│           ├── _mau-review.md     # Person-bit review template (20:00 deadline)
│           └── YYYY-MM-DD/
│               ├── hhuy-annotate.md
│               ├── long-review-hhuy.md
│               ├── long-annotate.md
│               └── ...
├── week2-humankeypoint/       → repo: hahahuy/week2-humankeypoint (branch main)
└── week3-Lidarmapping/        → repo: hahahuy/week3-Lidarmapping (branch main)
```

**Key insight:** `tuan-02.md` and `tuan-03.md` do NOT exist in week1-2D. They live in week2/3 repos respectively. Each week repo has its own `tuan-01.md` (the current week) and the next week is pre-created.

---

## Round-Robin Reviewer — Mentor Verification Rules

**Fixed rotation (3 weeks, never changes unless QĐ says so):**

```
HHuy → Long → PHuy → Mạnh → Cường → HHuy (circle closes)
```

**Mentor must verify EVERY day:**

1. Each `*-annotate.md` has `Reviewer: @<kế-tiếp>` field pointing to the correct person
2. Each `*-review-*.md` has `Nguồn: link tới file annotate` — link chéo bắt buộc
3. **No self-review.** Check: annotator name ≠ reviewer name in every file pair
4. **Group leaders review 50** of predecessor even though they only annotate 25
5. **Mạnh** (Seg leader) reviews PHuy's 50 photos — Mạnh does NOT review Cường
6. **Cường** (BBox leader) reviews Mạnh's 50 photos — Cường does NOT review HHuy
7. **Deadline enforcement:** annotate 16:00, review 20:00 (T4 review must be 21:00 for Duty 1 prep)

**If someone is missing their review file by 20:00, mentor escalates immediately.**

---

## Person-Bit Format — What Mentor Looks For

Each daily annotate file (`nhat-ky-job/YYYY-MM-DD/<ten>-annotate.md`) must contain:

- [ ] Date + task breakdown (Task A _/25, Task B _/25, total _/50)
- [ ] CVAT link(s) to batch
- [ ] What went right (1-2 lines)
- [ ] What went wrong / confusing (1-2 lines + frame links)
- [ ] **Ảnh tệ (terrible match)** table: frame + why terrible + propose bỏ/giữ
- [ ] Blocker: yes/no → if P-xxx, link to backlog
- [ ] Reviewer pinged: yes/no
- [ ] What needed tomorrow

Each daily review file (`<reviewer>-review-<annotator>.md`) must contain:

- [ ] Link to annotate source file (link chéo)
- [ ] Count: _/50 reviewed, sample check _%
- [ ] Trả lại table: frame + error + § guideline + level (lẻ tẻ/hệ thống)
- [ ] Verdict: Pass (<10% sample wrong) / Return whole job (>10%) / Pass with conditions
- [ ] Ảnh tệ agree/disagree with annotator's proposal
- [ ] Suggestions for tomorrow's annotate
- [ ] Escalate to P-xxx? yes/no

**Mentor checks:** if annotate file exists but no matching review file by 20:00 → gap. If image terrible match but no reviewer comment → annotator may have self-decided without oversight → flag.

---

## Edge Case Flow (P-xxx → QĐ-xxx)

```
Annotator meets guideline gap → writes P-xxx in problem-backlog.md + daily-bit
    ↓
Reviewer sees it in review file → confirms it's a real gap
    ↓
Mentor collects during Duty 1 (T5) or Duty 2 (CN) meeting
    ↓
Mentor decides or escalates to BTC
    ↓
Chốt → QĐ-xxx written in so-quyet-dinh.md
    ↓
QĐ-xxx applies to all future annotations
```

**Mentor rules:**
- **Never let annotator guess** when guideline is unclear → must create P-xxx
- **Never let reviewer self-resolve** a P-xxx alone → mentor confirms
- **Update so-quyet-dinh.md immediately** when a P-xxx is resolved — do not batch
- **Track P-xxx status** in problem-backlog.md: 🔴 Mở / 🗣️ Đang bàn / ↗️ Hỏi BTC / ✅ Đã chốt → QĐ-xxx / 🛠️ Làm tool / ⚪ Bỏ

---

## Weekly Reports — Mentor Review Guide

### Duty 1 Report (T5, Thursday) — Mentor reads BEFORE the họp online

File: `nhat-ky-tuan/tuan-NN.md` § Duty 1, or separate `tuan-NN-duty-1.md`

Mentor checks:
- [ ] All 5 annotators have person-bit files for T2→T4
- [ ] All review files exist with link chéo
- [ ] Progress % matches actual person-bit counts
- [ ] Blockers listed with P-xxx references
- [ ] Ảnh tệ table filled (propose bỏ/giữ)
- [ ] Questions ready for mentor họp
- [ ] **If any gap found:** annotate before entering họp — do NOT present empty data

### Duty 2 Report (CN, Sunday) — Mentor writes/validates

File: `nhat-ky-tuan/tuan-NN.md` § Duty 2, or separate `tuan-NN-duty-2.md`

Mentor checks:
- [ ] T6→T7 person-bit aggregate matches actual counts
- [ ] Weekly total: _/250 (5pp × 50, minus leaders' 25 if applicable)
- [ ] Quality summary: review pass %, Ảnh tệ resolved
- [ ] New QĐ-xxx created for any edge case chốt this week
- [ ] P-xxx backlog updated
- [ ] Next week plan: leader rotation, data type confirmation
- [ ] **Copy 3 numbers** into § Tổng kết: đã gán, qua review %, edge case

---

## Current State (as of 15/09/2026)

### What's DONE
- [x] Repo structure created (`week1-2D`, `week2-humankeypoint`, `week3-Lidarmapping`)
- [x] All templates created (`_mau-annotate.md`, `_mau-review.md`, `_mau-tuan.md`, `_mau-duty-1.md`, `_mau-duty-2.md`)
- [x] `phan-cong-review.md` with fixed rotation and 3-week tracking
- [x] `tuan-01.md` example filled (week 01, 2D data)
- [x] Group leaders confirmed: **Mạnh (Seg)** + **Cường (BBox)**, each 25 photos
- [x] Round-robin confirmed: `HHuy → Long → PHuy → Mạnh → Cường → HHuy`
- [x] All files committed and pushed to GitHub

### What's OPEN (Mentor must chase)
- [ ] **Handle GitHub thật** cho 5 người (hiện `@empty`) — cần để commit author đúng tên
- [ ] **Task guideline cho W2 (Human Keypoint) và W3 (3D LiDAR)** — hiện chỉ có Task A (Seg) + Task B (BBox/Polyline) cho W1
- [ ] **Nhóm trưởng W2, W3** — tuần 1 đã chốt (Mạnh/Cường), tuần 2/3 random hoặc chốt lại
- [ ] **P-xxx từ tuần 01** — ví dụ trong tuan-01: P-002 (xe bị che khuất), P-003 (vẽ lại box qua frame) — cần chốt
- [ ] **CVAT task links thật** — hiện chỉ có `task 12` giả trong tuan-01
- [ ] **Mentor Duty 1 họp T5 đầu tiên** — 25/09/2026 (đang đến gần)

### Deadlines Coming Up
| Date | Event | Mentor action |
|---|---|---|
| 22/09 (T3) | Gán đợt 1 deadline 16:00 | Verify person-bit files exist |
| 23/09 (T4) | Nộp phần đầu 16:00, review 20:00, T4 review 21:00 | Check all review files link to annotate |
| 24/09 (T5) | **MENTOR DUTY 1** — họp online | Present Duty 1 aggregate T2→T4 |
| 25/09 (T6) | Gán đợt 2 | Verify person-bit files |
| 26/09 (T7) | **Đóng batch 20:00** | Verify all jobs submitted |
| 27/09 (CN) | **MENTOR DUTY 2** — chốt tuần | Present Duty 2, create QĐ-xxx if needed |

---

## Mentor Decision-Making Protocol

When the team encounters an issue, the mentor follows this hierarchy:

1. **Guideline says clearly** → annotator follows. No P-xxx needed.
2. **Guideline unclear/ambiguous** → annotator creates P-xxx in problem-backlog.md, annotates with `can_xem_lai` tag. Reviewer confirms.
3. **P-xxx needs team decision** → mentor collects during Duty 1/2 họp. Options discussed. Chốt → QĐ-xxx.
4. **P-xxx needs external answer (BTC)** → mentor asks. Status: ↗️ Hỏi BTC. Annotators stop that task or use `can_xem_lai` tag temporarily.
5. **Pain point repeats + tool could fix** → status changes to 🛠️ Làm tool. Source code goes to `source-tool/`.
6. **Annotation must stop** → if blocker P-xxx unresolved, job ⛔. Move to other task if possible.

**Golden rule:** Annotator NEVER guesses. Annotator NEVER self-resolves P-xxx. Annotator NEVER changes guideline interpretation without QĐ-xxx.

---

## How to Verify the Team is Working Systematically

Run this checklist every morning (T3, T6) or whenever:

```bash
# 1. Check all person-bit files exist for yesterday
ls /path/to/repo/nhat-ky-tuan/nhat-ky-job/$(date -d yesterday +%Y-%m-%d)/
# Expected: 5 annotate files + 5 review files (10 total)

# 2. Verify link chéo — every review file links back to an annotate file
grep -r "nhat-ky-job" /path/to/repo/nhat-ky-tuan/nhat-ky-job/$(date -d yesterday +%Y-%m-%d)/*.md
# Expected: each review file has "File annotate nguồn: ..."

# 3. Check no self-review
# Manually verify: in every *-review-*.md, reviewer ≠ annotator

# 4. Check deadlines
# All annotate files should be 16:00, all review files 20:00 (T4 21:00)

# 5. Verify round-robin rotation is maintained
# HHuy → Long → PHuy → Mạnh → Cường → HHuy (no exceptions)
```

If any check fails → mentor contacts the person immediately and documents in weekly report.

---

## File Naming Convention (Mentor Enforces)

```
nhat-ky-job/
└── YYYY-MM-DD/
    ├── hhuy-annotate.md          # HHuy annotates, reviewer = Long
    ├── long-review-hhuy.md       # Long reviews HHuy (correct rotation)
    ├── long-annotate.md          # Long annotates, reviewer = PHuy
    ├── phuy-review-long.md       # PHuy reviews Long
    ├── phuy-annotate.md          # PHuy annotates, reviewer = Mạnh
    ├── manh-review-phuy.md       # Mạnh reviews PHuy
    ├── manh-annotate.md          # Mạnh annotates, reviewer = Cường
    ├── cuong-review-manh.md      # Cường reviews Mạnh
    ├── cuong-annotate.md         # Cường annotates, reviewer = HHuy
    └── hhuy-review-cuong.md      # HHuy reviews Cường (circle closes)
```

**Naming rule:** `<reviewer>-review-<annotator>.md` — always. This makes it obvious who reviewed whom at a glance.

---

## Quick Reference — Mentor Commands

| Situation | Mentor action |
|---|---|
| Annotator stuck on guideline | Ask → create P-xxx → log in problem-backlog.md |
| Reviewer didn't file by 20:00 | Contact reviewer immediately + note gap in weekly report |
| Annotator didn't file by 16:00 | Contact annotator + note gap |
| Wrong reviewer in file | Fix + remind rotation rule |
| Self-review detected | Reject + reassign + note in weekly report |
| Batch deadline approaching (T7 20:00) | Verify ALL jobs submitted, not just some |
| Edge case needs BTC | Status ↗️ Hỏi BTC, annotators use `can_xem_lai` tag temporarily |
| Tool needed for repeat pain | Status 🛠️, create `source-tool/<name>/`, update problem-backlog.md |
| Weekly report incomplete | Do NOT proceed to Duty 1/2 họp until complete |
| Handle GitHub needed | Collect real handles, update phan-cong-review.md + README |
| Next week task unknown | Wait for Job T2, then update _mau-tuan.md for next week |

---

## Links to Repositories

- **week1-2D:** https://github.com/hahahuy/week1-2D (branch `feat/person-bit-template`)
- **week2-humankeypoint:** https://github.com/hahahuy/week2-humankeypoint (branch `main`)
- **week3-Lidarmapping:** https://github.com/hahahuy/week3-Lidarmapping (branch `main`)

All 3 repos have identical template structure. Each week repo contains:
- `README.md` (updated with cadence + person-bit info)
- `phan-cong-review.md` (rotation matrix + tracking)
- `nhat-ky-tuan/_mau-tuan.md`, `_mau-duty-1.md`, `_mau-duty-2.md`
- `nhat-ky-tuan/nhat-ky-job/_mau-annotate.md`, `_mau-review.md`, `.gitkeep`
- `nhat-ky-tuan/tuan-01.md` (current week's example)
- `problem-backlog.md`, `so-quyet-dinh.md`, `source-tool/README.md`

---

## Mentorship Mindset

> *"The mentor is not the person who does the work — it is the person who ensures the work is done correctly, on time, and systematically. If the team is working smoothly, the mentor's job is to step back and let them. If the team is stuck, the mentor's job is to unblock — not to annotate for them."*

**Key principles:**
1. **System over speed** — a consistent annotation process beats fast but inconsistent work
2. **Never guess** — if unsure, create P-xxx, not an assumption
3. **Link chéo always** — no orphan files, no orphan reviews
4. **Deadline is hard** — 16:00 annotate, 20:00 review, 20:00 T7 batch close
5. **Document everything** — every decision becomes QĐ-xxx, every gap becomes P-xxx
6. **Rotate but don't break** — rotation is fixed for 3 weeks, changing it mid-stream causes chaos

---

*Handoff created 15/09/2026. Next agent reads this + the 3 repo READMEs before first Duty 1 họp (T5 = 24/09/2026).*
