# The1ight · Mobile Agent — Học liệu

Tài liệu hướng dẫn cho lớp **Mobile Agent** của The1ight.

## Hướng dẫn hiện có

| # | Hướng dẫn | Mở |
|---|---|---|
| 1 | Voice → Note bằng Claudian + Whisper local | [Đọc online](https://qnn5342.github.io/mobile-agent-guides/voice-to-note-claudian-local-whisper.html) |
| 2 | 1 bot Telegram, nhiều profile Hermes theo từng topic | [Đọc online](https://qnn5342.github.io/mobile-agent-guides/huong-dan-1-bot-nhieu-profile-theo-topic.html) |

Trang chủ [qnn5342.github.io/mobile-agent-guides](https://qnn5342.github.io/mobile-agent-guides/) liệt kê cả hai hướng dẫn.

Bạn cũng có thể tải file `.html` về và mở bằng trình duyệt:

- `voice-to-note-claudian-local-whisper.html`
- `huong-dan-1-bot-nhieu-profile-theo-topic.html`

## Hướng dẫn 1 — Voice → Note bằng Claudian + Whisper local

Workflow: ghi âm trong Obsidian bằng core plugin **Audio recorder**, giữ file audio gốc, chuyển giọng nói thành chữ bằng **Whisper chạy local** (miễn phí, audio không rời máy), rồi để **Claudian** điều khiển một AI Agent đọc transcript và bổ sung phần ghi chú có cấu trúc vào note.

Điểm cốt lõi của bài: agent không cần tự "nghe" audio. Nó chạy lệnh `whisper` qua shell, đọc file transcript, rồi sửa note — vault là working directory của agent.

## Lưu ý

- Các `chat_id`, `thread_id` và token trong tài liệu chỉ là **số mẫu**. Dùng số thật của nhóm bạn.
- Không đưa bot token hay API key vào repo này.
- Lệnh và menu có thể thay đổi theo phiên bản công cụ. Khi khác với tài liệu, tin theo trợ giúp của chính công cụ đó trên máy bạn.
