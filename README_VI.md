# Map Editor 2D cho Android

Gói này bọc file HTML Map Editor 2D hiện có trong một ứng dụng Android WebView. Mục tiêu là cài riêng trên điện thoại cá nhân, chạy giao diện toàn màn hình và tải trang từ tài nguyên nằm bên trong APK.

## Lưu ý quan trọng

- Đây là **mã nguồn dự án Android**, chưa phải file APK đã biên dịch.
- Môi trường tạo gói hiện tại không có Android SDK/Gradle cài sẵn nên chưa thể biên dịch và kiểm thử APK ngay tại đây.
- Các thao tác tạo map có thể chạy trong WebView, nhưng chức năng nhập/xuất tệp JSON/PNG cần kiểm thử trên điện thoại. Một số cách tải tệp dùng `blob:` trong trình duyệt có thể cần tích hợp Android bổ sung.
- Bản HTML được giữ nguyên, không chỉnh sửa logic generator trong gói này.

## Cách lấy APK mà không cần cài Android Studio

1. Tạo một repository GitHub mới và tải toàn bộ nội dung thư mục này lên repository.
2. Mở tab **Actions** của repository.
3. Chạy workflow **Build Android APK** bằng nút **Run workflow** (hoặc push lên nhánh `main`).
4. Khi workflow chạy xong, mở lần chạy đó và tải artifact `MapEditor2D-debug-apk`.
5. Giải nén artifact, lấy `app-debug.apk`, gửi sang điện thoại Android và mở để cài.
6. Nếu Android hỏi, cho phép cài ứng dụng từ nguồn đó. Chỉ cài APK do chính repository của ông tạo ra.

## Build trên máy tính có Android SDK

Nếu đã cài Java 17+, Gradle 8.9 và Android SDK Platform 35, chạy tại thư mục gốc:

```bash
gradle assembleDebug
```

APK đầu ra:

```text
app/build/outputs/apk/debug/app-debug.apk
```

## Kiểm tra sau khi cài

- Mở app và tạo thử map Forest/Dungeon.
- Thử Generate Again, undo/redo.
- Thử xuất JSON/PNG và nhập lại JSON.
- Đối chiếu JSON xuất ra với định dạng mà game chính đang đọc trước khi dùng map trong game.
