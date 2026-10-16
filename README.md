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

### Tab Live: xem live cùng nhau và chat

Link chia sẻ: https://nicoleng274.github.io/AnQiUniverse/#live

**Ai được chia sẻ live.** Chỉ người được quản lý trang cho phép mới dán link hoặc chia sẻ màn hình được; fan khác chỉ xem và chat. Cách cho phép (làm một lần cho chính bạn):

1. Mở tab Live, bấm mục **📡 Chia sẻ live**: trang hiện một mã.
2. Vào Firestore → **Start collection** `hosts` (lần đầu) → **Add document**, *Document ID* là mã đó, thêm một trường bất kỳ (ví dụ `name`: tên người đó) → Save.
3. Tải lại trang là thấy ô dán link và nút **Chia sẻ màn hình**. Muốn thu hồi thì xoá document đó.

Mã gắn với trình duyệt: đổi máy, đổi trình duyệt hoặc xoá dữ liệu trang thì mã đổi, cần thêm lại.

**Dán link live.** Ghi tên sự kiện rồi dán link. Mọi người thấy trong danh sách **Đang live** (12 giờ gần nhất):

- **YouTube, Bilibili** (link `live.bilibili.com/<số phòng>` hoặc video `BV…`): bấm **▶ Xem ở đây** là xem ngay trên trang, khung chat ở bên cạnh.
- **Douyin, Weibo, TikTok**: các nền tảng này không cho trang nào khác nhúng live, kể cả khi người xem đã đăng nhập (họ chặn bằng header của chính họ, trang web không gỡ được). Nút **Mở ↗** mở live trong app trên điện thoại, còn trên máy tính thì mở một cửa sổ nhỏ cạnh trang. Muốn mọi người xem ngay trên trang thì dùng **Chia sẻ màn hình**.
- Dán được nguyên đoạn chia sẻ từ app (ví dụ `7.66 复制打开抖音，看看… https://v.douyin.com/…/`), trang tự lấy link. Chỉ nhận link từ Douyin, TikTok, Weibo, Bilibili (cả `b23.tv`), YouTube.
- Tối đa 1 link mỗi phút. Người được cho phép gỡ được mọi link trong danh sách (nút **Gỡ**).

**Chia sẻ màn hình.** Mở live ở một tab khác, bấm **🖥 Chia sẻ màn hình**, chọn tab đó và bật **Chia sẻ âm thanh của thẻ** (Share tab audio). Mọi người bấm **▶ Xem ở đây** trong danh sách Đang live.

- Người chia sẻ cần dùng máy tính, Chrome hoặc Edge. Người xem dùng điện thoại hay máy tính đều được.
- Hình và tiếng đi thẳng từ trình duyệt người chia sẻ tới từng người xem (WebRTC), không qua máy chủ nào, nên **tối đa 8 người xem cùng lúc** (đổi ở `SCREEN.max` trong `index.html`). Mạng upload cần khoảng 1,5 Mbps cho mỗi người xem. Muốn nhiều người xem hơn thì phát lại lên YouTube hoặc Bilibili (ví dụ bằng OBS) rồi dán link.
- Một số mạng (mạng công ty, vài mạng di động) chặn kết nối trực tiếp. Nếu có người xem không vào được, thêm một máy chủ TURN vào `SCREEN.ice`.
- Xem qua màn hình chia sẻ không được tính vào lượt xem của buổi live gốc.

**Vietsub tự động.** Tích ô **Vietsub tự động (tiếng Trung → tiếng Việt)** trước hoặc trong lúc chia sẻ màn hình. Người xem thấy phụ đề tiếng Việt trên video (nút CC để ẩn, xem toàn màn hình vẫn có).

- Chạy hoàn toàn trong Chrome của người chia sẻ, miễn phí, không cần tài khoản hay khoá API: Chrome nghe âm thanh tab đang chia sẻ để nhận dạng tiếng Trung (Web Speech API, Chrome 135 trở lên), rồi dịch sang tiếng Việt bằng bộ dịch có sẵn của Chrome (Translator API, Chrome 138 trở lên, máy tính). Lần đầu Chrome tải bộ dịch Trung–Việt về máy, trang hiện phần trăm.
- Cần **Google Chrome 138 trở lên trên máy tính**. Edge và trình duyệt khác chưa chắc có đủ hai tính năng này.
- Đây là dịch máy: chậm khoảng 1–3 giây, sai tên riêng và từ lóng, nói nhanh hay nhiều người nói cùng lúc thì kém, lúc hát gần như không dùng được. Phần nhận dạng giọng nói của Chrome gửi âm thanh tới máy chủ Google.
- Người xem vào sau vẫn nhận phụ đề ngay câu đang chạy.

**Kênh của 安崎.** Nút mở thẳng Douyin và trang Weibo của 安崎. Nút Douyin hiện mở trang tìm kiếm 安崎 trên Douyin. Khi có link trang cá nhân (`https://www.douyin.com/user/…`) hoặc phòng live (`https://live.douyin.com/…`), dán vào `u` của dòng `douyin` trong `LIVE` ở `index.html`.

Khi ở tab Live, nhạc đang phát sẽ dừng. Tin nhắn gửi từ tab này có nhãn `🔴 LIVE · Douyin` (hoặc nền tảng vừa mở) để mọi người biết đang nói về buổi live.

### Bật GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, thư mục `/ (root)` → Save.
Trang sẽ chạy ở `https://nicoleng274.github.io/AnQiUniverse/`.

### Bật khung chat (Firebase, miễn phí)

1. Vào [console.firebase.google.com](https://console.firebase.google.com), tạo project mới (có thể tắt Google Analytics).
2. **Build → Authentication → Get started → Sign-in method → Anonymous → Enable.**
3. **Build → Firestore Database → Create database**, chọn vị trí `asia-southeast1 (Singapore)`, chế độ *production*.
4. Trong Firestore, mở tab **Rules**, dán toàn bộ nội dung file [`firestore.rules`](firestore.rules) rồi bấm **Publish**. Mỗi lần file này thay đổi (ví dụ khi thêm phần live của fan, chia sẻ màn hình) thì dán và Publish lại.
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
- `LIVE`: nút mở livestream Douyin, Weibo của 安崎 ở tab Live.
- `LIVE_HOSTS`: các nền tảng fan được chia sẻ link live. Thêm nền tảng thì sửa cả regex `url` trong `firestore.rules`.

## Nguồn

- Tiểu sử, dòng thời gian: [Baidu Baike](https://baike.baidu.com/item/%E5%AE%89%E5%B4%8E/22831154)
- Bài hát, lượt nghe, ảnh bìa: Spotify (cập nhật 07.10.2026)
- Video: YouTube [@babymonsteranqi](https://www.youtube.com/channel/UCEjFkvV5lTsZVPzGdDj8JDw)

Ảnh bìa, ảnh nghệ sĩ và thumbnail video thuộc về chủ sở hữu tương ứng.
