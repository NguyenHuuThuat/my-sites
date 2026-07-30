# my-sites

Nơi lưu và publish các trang HTML (bài giảng, demo, landing page thử nghiệm...) lên GitHub Pages, thông qua 1 tool chạy ngay trong trình duyệt — không cần cài git, không cần dòng lệnh.

## Cấu trúc repo

```
my-sites/
├── deploy-tool.html          # Tool publish — mở file này bằng trình duyệt để dùng
├── publish-github.sh         # (tuỳ chọn) bản dòng lệnh, publish qua git CLI
├── publish-vps.sh            # (tuỳ chọn) bản publish lên VPS tự host
├── nginx-vps.conf            # (tuỳ chọn) config nginx mẫu cho phương án VPS
├── token.local.example.js    # Mẫu file cấu hình token, copy thành token.local.js
├── .gitignore                # Chặn token.local.js không bị lỡ tay commit
├── README.md                 # File này
└── projects/                 # Mỗi thư mục con = 1 trang đã publish
    ├── ai-powerbi-l1/
    ├── mlops-beginner/
    └── .../
```

## Cách publish 1 trang mới

1. Mở `deploy-tool.html` bằng trình duyệt (Chrome/Edge khuyên dùng).
2. Bấm **⚙ Cấu hình** → điền GitHub username, tên repo (`my-sites`), Personal Access Token (quyền `Contents: Read and write`, chỉ scope vào repo này). Xem `token.local.example.js` nếu muốn tool tự điền token mỗi lần mở, khỏi dán tay.
3. Kéo-thả file `.html` hoặc `.zip` (kèm ảnh) vào ô, đặt **Tên dự án**, bấm **Publish**.
4. Trang sẽ live tại: `https://<user>.github.io/my-sites/projects/<ten-du-an>/`

Mỗi lần publish, tool tự động: đẩy file lên `projects/<ten-du-an>/`, cập nhật danh sách bên dưới trong README này, tất cả trong **cùng 1 commit**.

## Lưu lịch sử publish vào Excel

Trong tool, bấm **📊 Kết nối file Excel lịch sử** 1 lần, chọn file `deploy-history.xlsx` — từ đó mỗi lần publish sẽ tự ghi thêm 1 dòng vào đúng file đó (chỉ hoạt động trên Chrome/Edge).

## Bảo mật

- Token GitHub **không** được nhúng vào `deploy-tool.html` hay bất kỳ file nào trong repo này — nó chỉ nằm trong `token.local.js` (bị `.gitignore` chặn) hoặc gõ tay mỗi phiên.
- Vì `deploy-tool.html` nằm trong repo nên cũng sẽ được GitHub Pages phục vụ công khai tại `.../my-sites/deploy-tool.html` — không sao vì file không chứa bí mật gì.

## Giới hạn cần biết

GitHub Pages khuyến nghị repo dưới 1GB, file đơn lẻ dưới 100MB — phù hợp cho HTML + ảnh, chưa phù hợp cho video nặng.

---

## Danh sách trang đã publish

Mục dưới đây tự động cập nhật mỗi lần publish, không nên sửa tay.

<!-- DEPLOY_LIST_START -->
<!-- DEPLOY_LIST_DATA
[{"slug":"ai-powerbi-l1","url":"https://nguyenhuuthuat.github.io/my-sites/projects/ai-powerbi-l1/","time":"30/07/2026 12:48:34"},{"slug":"mlops-beginner","url":"https://nguyenhuuthuat.github.io/my-sites/projects/mlops-beginner/","time":"30/07/2026 12:55"}]
DEPLOY_LIST_DATA -->

| Dự án | URL | Thời gian |
|---|---|---|
| ai-powerbi-l1 | [Xem trang](https://nguyenhuuthuat.github.io/my-sites/projects/ai-powerbi-l1/) | 30/07/2026 12:48:34 |
| mlops-beginner | [Xem trang](https://nguyenhuuthuat.github.io/my-sites/projects/mlops-beginner/) | 30/07/2026 12:55 |
<!-- DEPLOY_LIST_END -->
