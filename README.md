# The1ight · Mobile Agent — Học liệu

Tài liệu hướng dẫn cho lớp **Mobile Agent** của The1ight.

## Hướng dẫn hiện có

| # | Hướng dẫn | Mở |
|---|---|---|
| 1 | 1 bot Telegram, nhiều profile Hermes theo từng topic | [Đọc online](https://qnn5342.github.io/mobile-agent-guides/) |
| 2 | Nhắn tin với AI bằng giọng nói, miễn phí (Whisper local) | [Đọc online](https://qnn5342.github.io/mobile-agent-guides/huong-dan-2-voice-note-mien-phi.html) |

Bạn cũng có thể tải file `.html` về và mở bằng trình duyệt:

- `huong-dan-1-bot-nhieu-profile-theo-topic.html`
- `huong-dan-2-voice-note-mien-phi.html`

## Hướng dẫn 2 — Nhắn tin với AI bằng giọng nói

Workflow: gửi voice note cho bot Telegram → Hermes tự chuyển giọng nói thành chữ **trên máy** bằng Whisper local → bot gửi lại transcript để kiểm tra → AI đọc và trả lời.

Hai lớp hoàn toàn độc lập, đây là điểm nhiều bạn hiểu sai:

- **Nghe → chữ**: Whisper local, miễn phí, không cần API key, audio không gửi lên dịch vụ trả tiền.
- **Hiểu → trả lời**: model AI của Hermes, chi phí theo gói/API anh chị đã có từ buổi trước.

Điểm hay bị kẹt nhất — bài này dành hẳn một bước cho nó:

1. `stt.provider: local` **không tự tạo ra** khả năng nghe. Máy phải có engine thật: hoặc lệnh `whisper`, hoặc gói `faster-whisper` trong môi trường của Hermes.
2. Mặc định `stt.language` của Hermes là `en`. Người nói tiếng Việt **phải** đặt `vi`, nếu không transcript sẽ sai ngôn ngữ.
3. Cần cả `ffmpeg`, vì voice note Telegram ở định dạng `.ogg/opus`.
4. Sau mỗi lần sửa config phải `hermes gateway restart`.

## Lưu ý

- Các `chat_id`, `thread_id` và token trong tài liệu chỉ là **số mẫu**. Dùng số thật của nhóm bạn.
- Không đưa bot token hay API key vào repo này.
- Lệnh và menu có thể thay đổi theo phiên bản Hermes. Khi khác với tài liệu, tin theo `hermes <lệnh> --help` trên máy bạn.
