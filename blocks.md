# Hai block bắt buộc ở cuối `reports/<STAMP>-*.md`

## Block `## Chat Sessions` — mỗi cuộc chat một dòng

```markdown
## Chat Sessions

| # | started_at | ended_at | Làm gì trong phiên | Kết phiên |
|---|-----------|----------|--------------------|-----------|
| 1 | 2026-08-06 10:24 | 2026-08-06 11:05 | Inventory pveE/F | K1 checkpoint |
| 2 | 2026-08-06 14:10 | ~ | Coverage matrix | ⚠️ tràn context (không kết) |
| 3 | 2026-08-07 09:00 | 2026-08-07 09:40 | Xong matrix + push | K2 done |
```

`ended_at = ~` nghĩa là phiên đó chết vì tràn context. Không bịa giờ.

## Block `## Work Log` — một việc một block, cập nhật dần

```markdown
## Work Log

| Field | Value |
|-------|-------|
| work_id | WORK-20260806-1024 |
| tenant / org_unit | cidare / — |
| workstream | ops |
| status | doing \| paused \| done \| cancelled |
| started_at | 2026-08-06 10:24 +07 |
| finished_at | 2026-08-07 09:40 +07 |
| duration_min | 121  ← TỔNG các Chat Sessions, không phải finished − started |
| lead_time_h | 23.3 ← finished − started (thời gian trôi) |
| outcome | ok \| partial \| blocked \| cancelled |
| report | 1–3 câu kết quả |
| next_actions | (K1 bắt buộc; K2 để trống hoặc ghi follow-up) |
| kb_links | memory/…md ; plans/…md ; reports/…md |
```

## Lưu ý

| Điểm | Xử lý |
|------|-------|
| 2 việc bắt đầu cùng phút | Hậu tố: `WORK-20260806-1024b` |
| Việc bỏ giữa đường | `status: cancelled` + lý do trong `report` |
| Việc chạy nhiều ngày | `duration_min` = tổng sessions; `lead_time_h` cho biết trôi bao lâu |
| Timezone | Luôn `+07` (Asia/Ho_Chi_Minh) |

Đích đến của hai block này: bảng Teable trên `db.hade.day` — chi tiết ERD ở ACC `plans/20260806_0927-teable-daily-worklog-plan.md`.
