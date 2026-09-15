# Hướng dẫn viết Person-bit

**Bạn đang viết một person-bit.** Nhiệm vụ của bạn là ghi lại những gì đã xảy ra khi bạn gán nhãn hoặc review ảnh hôm nay. Viết bằng **ngôn ngữ tự nhiên** — câu chuyện trôi chảy, không cần bảng biểu cứng nhắc. Agent của mentor sẽ trích xuất dữ liệu có cấu trúc (số lượng, P-xxx, verdict, link frame) từ phần prose của bạn.

## Những gì BẠN PHẢI ghi

### Annotator (`*-annotate.md`)

Mỗi person-bit phải chứa các phần sau:

1. **Metadata** — ngày, handle của bạn, handle reviewer, cross-link tới file review
2. **Numbers** — bạn làm bao nhiêu ảnh (Task A, Task B, Tổng)
3. **What happened** — 3–5 câu prose: cái gì hoạt động tốt, cái gì gây nhầm lẫn, frame nào gặp vấn đề, có gap guideline nào không → có tạo `P-xxx` chưa
4. **Terrible frames** — cho mỗi frame bị mờ/che khuất/mơ hồ: link + lý do + đề xuất (giữ / bỏ / hỏi mentor). Viết prose, không viết bảng.
5. **Blocker** — có/không + `P-xxx` nếu có
6. **Cross-link verification** — xác nhận reviewer đúng theo rotation và cross-link chính xác

### Reviewer (`*-review-*.md`)

Mỗi person-bit phải chứa các phần sau:

1. **Metadata** — ngày, handle bạn, handle annotator, link file annotate nguồn
2. **Numbers** — bạn review bao nhiêu ảnh (Task A, Task B, Total)
3. **What you found** — 3–5 câu prose: đánh giá chất lượng tổng thể, lỗi hệ thống hay lỗi cá biệt, frame nào có lỗi và guideline nào áp dụng
4. **Terrible frames** — cho mỗi frame annotator đánh dấu tệ: bạn đồng ý hay không đồng ý và tại sao. Prose.
5. **Verdict** — Pass / Return whole job / Pass with conditions (một trong 3 lựa chọn)
6. **Escalate to P-xxx?** — có/không, nếu có mô tả và link tới backlog hoặc nói "to create"
7. **Suggestion for tomorrow** — 1–2 dòng prose

## Những gì bạn KHÔNG cần

Bạn không cần điền bảng, checkbox, hay formatting cứng nhắc. Agent của mentor sẽ trích xuất structured info từ prose của bạn. Viết rõ ràng là đủ, chỉ cần đảm bảo ghi đầy đủ các data points ở trên.

## Ví dụ

### Ví dụ annotator (phần terrible frames)

> Frame 142 — xe bị mờ sau trụ điện, khoảng 30% visible. Đề xuất giữ vì occlusion là edge case quan trọng cho training. Frame 201 — người ngồi trên xe máy, guideline §3.2 mơ hồ về việc có nên vẽ box riêng cho người trên xe hay không. Đề xuất hỏi mentor.

### Ví dụ reviewer (phần what you found)

> Chất lượng tổng thể tốt — HHuy luôn dùng separate box cho mỗi người theo §3.2. Hai lỗi hệ thống: đánh giá sai kích thước box cho pedestrian (3 frame, xem `?frame=8`, `?frame=64`, `?frame=120`), và đôi khi bỏ sót vật thể nhỏ ở cạnh ảnh. Có vẻ mang tính hệ thống chứ không phải cá biệt — đánh dấu để thảo luận P-xxx tại Duty 1.

## Deadline

- Annotate: **16:00** cùng ngày
- Review: **20:00** cùng ngày (review T4: **21:00** để chuẩn bị Duty 1)
- Cross-link: cùng ngày, cùng người

## Vòng review (không đổi trừ khi có QĐ)

`HHuy → Long → PHuy → Mạnh → Cường → HHuy`
