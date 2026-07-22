# Cat Cakery — Website tĩnh

Cấu trúc thư mục:
```
.
├── index.html      # toàn bộ trang web (1 file)
├── vercel.json      # cấu hình cache/clean URL cho Vercel
└── images/           # ảnh sản phẩm + logo
    ├── logo.jpg
    ├── banh-dua.jpg
    ├── banh-chuoi.jpg
    ├── banh-trungmuoi.jpg
    ├── banh-custom.jpg
    ├── banh-caneles.jpg
    └── banh-trungthu.jpg
```

Đây là site tĩnh (không cần build, không cần Node/npm) nên deploy lên Vercel rất nhanh. Chọn 1 trong 2 cách dưới đây.

## Cách 1 — Deploy bằng Vercel CLI (nhanh nhất, không cần GitHub)

1. Cài Node.js nếu máy chưa có (tải tại nodejs.org).
2. Mở Terminal, cài Vercel CLI:
   ```
   npm i -g vercel
   ```
3. Vào đúng thư mục chứa `index.html` (thư mục vừa tải về), chạy:
   ```
   vercel
   ```
4. Lần đầu chạy, Vercel sẽ hỏi:
   - Đăng nhập (chọn GitHub/Google/Email để tạo tài khoản Vercel miễn phí nếu chưa có)
   - "Set up and deploy?" → gõ **Y**
   - "Link to existing project?" → gõ **N**
   - "What's your project's name?" → đặt tên, ví dụ `cat-cakery`
   - "In which directory is your code located?" → để mặc định `./`
   - Framework Preset → chọn **Other** (site tĩnh, không cần build)
5. Đợi vài giây, Vercel trả về link dạng `https://cat-cakery.vercel.app` — vậy là web đã sống.
6. Muốn cập nhật sau này: sửa file rồi chạy lại `vercel --prod` trong đúng thư mục đó.

## Cách 2 — Deploy qua GitHub + Vercel Dashboard (dễ quản lý lâu dài)

1. Tạo 1 repo mới trên GitHub (ví dụ `cat-cakery-website`), upload toàn bộ các file/folder ở trên vào repo (kéo-thả trên GitHub web hoặc dùng Git).
2. Vào https://vercel.com → đăng nhập bằng GitHub.
3. Bấm **Add New → Project**, chọn repo `cat-cakery-website` vừa tạo.
4. Ở bước cấu hình: Framework Preset chọn **Other**, để nguyên Build Command và Output Directory (trống, vì không cần build).
5. Bấm **Deploy**. Sau khi xong, Vercel cấp link `https://cat-cakery-website.vercel.app`.
6. Từ giờ, mỗi lần bạn sửa file và push lên GitHub, Vercel sẽ tự động deploy lại — không cần làm thủ công nữa.

## Gắn domain riêng (tuỳ chọn)

Nếu sau này mua domain riêng (vd. catcakery.vn):
1. Vào project trên Vercel → tab **Settings → Domains**.
2. Nhập domain, Vercel sẽ cho 1-2 bản ghi DNS (loại A hoặc CNAME).
3. Vào nơi bạn mua domain (Mắt Bão, PA Vietnam, Namecheap...), thêm đúng bản ghi DNS đó.
4. Đợi DNS cập nhật (thường 10 phút – vài giờ) là domain trỏ thẳng vào website.

## Việc cần bạn làm thêm sau này

- Giá của "Bánh chuối choco", "Bánh bông lan trứng muối", "Bánh kem theo yêu cầu", "Bánh trung thu" đang để "Liên hệ giá" vì ảnh gốc không có giá — gửi mình giá thật để điền vào `index.html` (tìm đúng dòng `<div class="price">...`).
- Ảnh "Bánh kem theo yêu cầu" mình dùng tạm ảnh bánh trang trí con ong (file gốc không có tên rõ ràng) — nếu đây không đúng sản phẩm bạn muốn, cứ gửi ảnh khác để mình thay.
- Địa chỉ cụ thể của tiệm vẫn chưa có trong web (Facebook chặn crawl tự động) — gửi mình địa chỉ để thêm vào phần Liên hệ.
