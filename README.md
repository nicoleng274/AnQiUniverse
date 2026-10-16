# 安崎 Universe

Trang fan không chính thức tổng hợp bài hát, sân khấu live và MV của **安崎 (An Qi / An Kỳ)**.
An unofficial fan site collecting 安崎's songs, live stages and music videos.

**Xem trang:** https://nicoleng274.github.io/AnQiUniverse/

Mỗi trang có link riêng để chia sẻ: `#listen`, `#live`, `#artist`, `#songs`, `#stages`, `#mv`. Từng bài, sân khấu hay MV cũng có link riêng, ví dụ `#s-yyw` (月牙湾); bấm **Copy link** trong bảng chi tiết để lấy.

- **Universe**: trang chủ, mỗi vòng quỹ đạo là một năm (2020 → 2026), mỗi hành tinh là một bài hát.
- **Artist**: hồ sơ, kênh chính thức, dòng thời gian.
- **Songs / Stages / MV**: danh sách bài hát, sân khấu theo chương trình, video YouTube.
- Ba ngôn ngữ: English · 中文 · Tiếng Việt.

Trang không tự phát nhạc. Mỗi nút mở thẳng Spotify, YouTube, Bilibili, QQ音乐, 网易云 hoặc 酷狗, nên lượt nghe được tính trên nền tảng chính thức.

## Phòng nghe nhạc (Listen) và chat

Trang **Listen** nhúng trình phát YouTube và Spotify ngay trong web, bên cạnh là khung chat cho fan.
Link nghe nhạc để chia sẻ: https://nicoleng274.github.io/AnQiUniverse/#listen

- **YouTube (mặc định):** ai cũng nghe được trọn bài, không cần tài khoản. Có album **ANQI**, 16 bài hát (bản audio từ kênh 安崎 Topic hoặc MV chính thức) và 9 video MV. Tự bấm phát thì được tính lượt xem YouTube.
- **Spotify:** lượt nghe chỉ được tính khi người nghe đã đăng nhập Spotify trên trình duyệt đó và nghe từ 30 giây. Chưa đăng nhập thì chỉ có bản nghe thử 30 giây, trang sẽ hiện cảnh báo màu cam.
- **YouTube:** tính lượt xem khi người xem tự bấm phát.
- Trình phát chỉ chạy khi trang được mở qua web (GitHub Pages). Bản xem trước trên claude.ai không nhúng được trình phát.

### Tab Live: xem livestream Douyin, Weibo và chat cùng fan

Link chia sẻ: https://nicoleng274.github.io/AnQiUniverse/#live

Douyin và Weibo không cho trang khác nhúng livestream (không có trình phát nhúng chính thức, trang live chặn iframe, link luồng video có chữ ký và hết hạn nhanh), và phần bình luận trong live chỉ dùng được trong app của họ. Vì vậy tab **Live** trong phòng nghe nhạc:

- có nút mở thẳng Douyin và trang Weibo của 安崎 (trong app nếu điện thoại có cài, không thì mở web). Xem trên nền tảng chính thức nên vẫn được tính vào số người xem của phòng live;
- tạm dừng nhạc đang phát, để khung chat bên cạnh cho fan nói chuyện trong lúc xem;
- tin nhắn gửi từ tab này có nhãn `🔴 LIVE · Douyin` hoặc `🔴 LIVE · Weibo` (theo nút vừa bấm), để mọi người biết đang nói về buổi live.

Nút Douyin hiện mở trang tìm kiếm 安崎 trên Douyin. Khi có link trang cá nhân (`https://www.douyin.com/user/…`) hoặc phòng live (`https://live.douyin.com/…`), dán vào `u` của dòng `douyin` trong `LIVE` ở `index.html` để nút mở thẳng.

### Bật GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, thư mục `/ (root)` → Save.
Trang sẽ chạy ở `https://nicoleng274.github.io/AnQiUniverse/`.

### Bật khung chat (Firebase, miễn phí)

1. Vào [console.firebase.google.com](https://console.firebase.google.com), tạo project mới (có thể tắt Google Analytics).
2. **Build → Authentication → Get started → Sign-in method → Anonymous → Enable.**
3. **Build → Firestore Database → Create database**, chọn vị trí `asia-southeast1 (Singapore)`, chế độ *production*.
4. Trong Firestore, mở tab **Rules**, dán toàn bộ nội dung file [`firestore.rules`](firestore.rules) rồi bấm **Publish**.
5. **Project settings → Your apps → Web (`</>`)**, đăng ký app, copy đoạn `firebaseConfig`.
6. Dán vào `const FIREBASE_CONFIG = …` trong `index.html` (hoặc gửi cho người quản lý trang).

Luật chat: ai cũng đọc được; mỗi người gửi tối đa 1 tin mỗi 3 giây, tên tối đa 24 ký tự, tin tối đa 300 ký tự. Muốn xoá tin nhắn xấu: Firestore → `rooms/main/messages` → xoá document đó.

Lưu ý: Spotify, YouTube và Firebase đều bị chặn ở Trung Quốc đại lục nếu không dùng VPN.

## Chạy thử

Mở `index.html` bằng trình duyệt, hoặc bật GitHub Pages cho nhánh `main` (thư mục gốc).

## Cập nhật link

Dữ liệu nằm ở đầu thẻ `<script>` trong `index.html`:

- `SONGS`: bài hát. Thêm `yt`, `bili`, `qq`, `ncm`, `kg` (URL đầy đủ) để nút mở thẳng bài trên nền tảng đó. Để trống thì nút mở trang tìm kiếm.
- `SHOWS`: sân khấu live theo chương trình.
- `MVS`: video trên kênh YouTube.
- `CHANNELS`: các kênh chính thức.
- `LIVE`: nút mở livestream Douyin, Weibo ở tab Live.

## Nguồn

- Tiểu sử, dòng thời gian: [Baidu Baike](https://baike.baidu.com/item/%E5%AE%89%E5%B4%8E/22831154)
- Bài hát, lượt nghe, ảnh bìa: Spotify (cập nhật 07.10.2026)
- Video: YouTube [@babymonsteranqi](https://www.youtube.com/channel/UCEjFkvV5lTsZVPzGdDj8JDw)

Ảnh bìa, ảnh nghệ sĩ và thumbnail video thuộc về chủ sở hữu tương ứng.
