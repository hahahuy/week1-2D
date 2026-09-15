# Repo đội — Cohort 4A

Repo làm việc của một đội gán nhãn. Mỗi đội nhận một bản sao của template này.

> Tên người, handle GitHub, số liệu và link CVAT trong các file mẫu đều là **giả**,
> chỉ để minh hoạ cách ghi. Thay bằng dữ liệu của đội khi bắt đầu.

## Có gì trong repo

| Đường dẫn | Dùng để | Cập nhật khi nào |
|---|---|---|
| [`nhat-ky-tuan/`](nhat-ky-tuan/) | Big report theo tuần: phân công, Duty 1 (T5) + Duty 2 (CN), tổng kết | Đầu tuần phân công, T5/CN tổng hợp |
| [`nhat-ky-tuan/nhat-ky-job/`](nhat-ky-tuan/nhat-ky-job/) | **Person-bit** theo ngày: `*-annotate.md` + `*-review-*.md` (link chéo) | **Hàng ngày** — annotate trước 16:00, review trước 20:00 |
| [`nhat-ky-tuan/_mau-duty-1.md`](nhat-ky-tuan/_mau-duty-1.md) | Mẫu report Duty 1 (T5) — tổng hợp T2→T4 cho họp mentor | T5 |
| [`nhat-ky-tuan/_mau-duty-2.md`](nhat-ky-tuan/_mau-duty-2.md) | Mẫu report Duty 2 (CN) — tổng hợp T6→T7, chốt tuần | CN |
| [`phan-cong-review.md`](phan-cong-review.md) | Vòng review cố định + tracking 3 tuần | Đầu đợt, cập nhật T7/CN |
| [`problem-backlog.md`](problem-backlog.md) | Edge case gặp khi gán nhãn mà guideline chưa trả lời được, kèm link CVAT | **Ngay khi gặp** |
| [`so-quyet-dinh.md`](so-quyet-dinh.md) | Những gì đội đã chốt, và vì sao | Mỗi lần chốt một vấn đề |
| [`source-tool/`](source-tool/) | Source code công cụ đội tự viết để gỡ pain point khi gán nhãn | Khi đã xác định được pain point đáng làm tool |

## Các file nối với nhau thế nào

```mermaid
flowchart TB
    A[Gán nhãn trên CVAT] -->|hàng ngày| P1[nhat-ky-job/<br/>person-bit annotate<br/>trước 16:00]
    P1 -->|sau 16:00| P2[nhat-ky-job/<br/>person-bit review<br/>trước 20:00]
    P1 & P2 -->|T5 Duty 1<br/>T2→T4| D1[nhat-ky-tuan/<br/>Duty 1 report]
    P1 & P2 -->|CN Duty 2<br/>T6→T7| D2[nhat-ky-tuan/<br/>Duty 2 + tổng kết tuần]
    P1 -.->|guideline không trả lời được| B[problem-backlog.md<br/>P-xxx + link CVAT]
    P2 -.->|lỗi hệ thống| B
    B -->|đội bàn và chốt| C[so-quyet-dinh.md<br/>QĐ-xxx]
    C -->|áp dụng lại| A
    B -->|pain point lặp lại| D[source-tool/]
    D -->|tool dùng khi gán| A
    B -.-> D1 & D2
    C -.-> D1 & D2
```

**Luồng person-bit → duty:** `nhat-ky-job/YYYY-MM-DD/*-annotate + *-review` (hàng ngày, link chéo) → aggregate vào `nhat-ky-tuan/tuan-NN.md` § Duty 1 (T5) và § Duty 2 (CN).

## Vị trí trong đội

| Vị trí | Việc chính |
|---|---|
| **Lead** | Chia job, điều phối, đưa edge case ra bàn và chốt, giữ sổ quyết định |
| **Annotator** | Gán nhãn theo guideline; gặp chỗ guideline không trả lời được thì ghi vào backlog thay vì tự đoán |
| **Reviewer** | Kiểm job đã gán, trả lại chỗ sai kèm lý do |

Một người có thể giữ nhiều vị trí, nhưng **không review job do chính mình gán**.

## Cách làm việc 3 tuần tới (14/09 – 04/10/2026)

> Đợt này 3 kiểu data: **W1 2D → W2 Human Keypoint → W3 3D LiDAR**. Task hiện tại: **A Semantic Segmentation + B BBox/Polygon/Polyline** (tuần sau có thể đổi, chỉ biết kiểu data).

### Cadence cố định T2→CN (áp dụng cả 3 tuần)

| Ngày | Việc | Deadline | Ai |
|---|---|---|---|
| **T2** | Nhận Job — Lead chia batch (25+25 / người, nhóm trưởng chỉ 25 / 1 task) | T2 cuối ngày | Lead |
| **T3** | Gán đợt 1 — person-bit annotate | **16:00** | Mỗi người |
|  | Review đợt 1 — person-bit review (vòng cố định) | **20:00** | Reviewer |
| **T4** | Nộp phần đầu (**làm nhiêu nộp bấy**) + person-bit | 16:00 / 20:00 | Mỗi người |
|  | Review T4 phải xong để họp T5 | **21:00 T4** | Reviewer |
| **T5** | **Mentor Duty 1** — họp online, trình bày report Duty 1 (tổng hợp T2→T4) | T5 | Lead + cả đội |
| **T6** | Gán đợt 2 — person-bit | 16:00 / 20:00 | Mỗi người |
| **T7** | **Đóng batch — nộp hết job trước 20:00** + person-bit | 16:00 / **20:00** | Mỗi người |
| **CN** | **Mentor Duty 2** — chốt tuần, report Duty 2 (T6→T7) | CN | Lead |

### Batch & vòng review

- **Batch:** 25 ảnh / task / người = **50 ảnh/tuần/người**. 2 nhóm trưởng (random T2) chỉ làm **25 ảnh (1 task)** nhưng vẫn review đủ 50 của người trước.
- **Vòng review cố định 3 tuần:** `HHuy → Long → PHuy → Mạnh → Cường → HHuy` — xem [`phan-cong-review.md`](phan-cong-review.md). Không tự review, không đổi vòng giữa chừng.
- **Ảnh tệ (terrible match):** Annotator đề xuất trong `*-annotate.md`, reviewer đồng ý/không trong `*-review-*.md`. Chưa có guideline thì chưa tự bỏ — chờ chốt ở Duty 1/2 thành `QĐ-xxx`.

### Person-bit hàng ngày (trong `nhat-ky-job/`)

```
nhat-ky-tuan/nhat-ky-job/
├── _mau-annotate.md              # mẫu
├── _mau-review.md                # mẫu
└── YYYY-MM-DD/                   # 1 thư mục/ngày
    ├── hhuy-annotate.md          # HHuy log phần mình
    ├── long-review-hhuy.md       # Long review HHuy (theo vòng)
    ├── long-annotate.md
    ├── phuy-review-long.md
    └── …
```

Mỗi `*-annotate.md` có `Reviewer: @<kế tiếp>` và link tới file review cùng ngày; mỗi `*-review-*.md` có `Nguồn: link tới file annotate` — **link chéo bắt buộc** để hai người không lạc nhau.

### Từ person-bit lên big report

1. Hàng ngày: mỗi người tự log `person-bit` (đúng/sai, ảnh tệ + link CVAT, blocker `P-xxx`).
2. T5: Lead aggregate `nhat-ky-job/T2→T4` vào `nhat-ky-tuan/tuan-NN.md` § Duty 1 (dùng [`_mau-duty-1.md`](nhat-ky-tuan/_mau-duty-1.md)) — mang đi họp mentor.
3. CN: Lead aggregate `T6→T7` vào § Duty 2 (dùng [`_mau-duty-2.md`](nhat-ky-tuan/_mau-duty-2.md)) — chốt tuần, tạo `QĐ-xxx` nếu cần, copy 3 số chính vào § Tổng kết.

### Lịch 3 tuần

| Tuần | Ngày | Kiểu data | Nhóm trưởng (random T2) |
|---|---|---|---|
| 01 | 14–20/09/2026 | 2D | Task A: @__ · Task B: @__ |
| 02 | 21–27/09/2026 | Human Keypoint | Task A: @__ · Task B: @__ |
| 03 | 28/09–04/10/2026 | 3D LiDAR | Task A: @__ · Task B: @__ |

## Quy ước

- **Mã**: `P-001`, `QĐ-001`, đánh số tăng dần. Không dùng lại số của mục đã bỏ.
- **Nhắc người**: bằng handle GitHub, ví dụ `@thanh-vien-a` (hiện để `@empty`, thay khi có handle thật).
- **Link CVAT**: trỏ tới đúng job và frame (`.../jobs/<id>?frame=<n>`), không trỏ tới cả task —
  người đọc phải mở ra là thấy ngay chỗ có vấn đề.
- **Mục guideline**: ghi số mục (`§3.2`) để ai cũng tra lại được.
- **Person-bit**: `*-annotate.md` trước **16:00**, `*-review-*.md` trước **20:00** (T4 review trước **21:00** để họp T5). Link chéo cùng ngày bắt buộc.
- **Nộp T4**: làm nhiêu nộp bấy. **T7**: đóng batch trước 20:00.
- **Vòng review:** `HHuy → Long → PHuy → Mạnh → Cường → HHuy` — cố định 3 tuần.
