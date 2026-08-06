# prompt-kit

Mirror **công khai** của bộ hướng dẫn phiên làm việc dùng cho AI agent (Claude Code, Cursor, Codex, Gemini CLI…).

Mục đích: agent nào **không đọc được file local** (cloud agent, sandbox, máy khác) thì fetch qua raw URL.

| File | Dùng khi |
|------|----------|
| [`m1.md`](m1.md) | Mở **việc mới** — lấy STAMP, neo trạng thái |
| [`m2.md`](m2.md) | **Tiếp việc cũ** / sau khi tràn context |
| [`k1.md`](k1.md) | Hết chat nhưng việc **chưa xong** (checkpoint) |
| [`k2.md`](k2.md) | Việc **đã xong** |
| [`blocks.md`](blocks.md) | Mẫu block `## Chat Sessions` + `## Work Log` |
| [`report.md`](report.md) | **Người dùng thường** báo cáo công việc qua chatbot bất kỳ → khối JSON `worklog/v1` |

Raw URL:

```
https://raw.githubusercontent.com/hacmieu/prompt-kit/main/m1.md
```

## Nguyên tắc

- **SSOT là repo riêng (private)**, thư mục `templates/prompt/`. Repo này chỉ là **bản mirror** — đừng sửa trực tiếp ở đây.
- Không chứa secret, host, IP, token. Chỉ là quy ước làm việc.
- Đơn vị đo là **việc**, không phải cuộc chat: một việc = một `STAMP` = một `work_id`, có thể trải nhiều cuộc chat.
