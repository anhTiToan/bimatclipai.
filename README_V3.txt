
Bí Mật Clip AI - V3 (Cloudflare Pages + Netlify CMS scaffold)
===========================================================

Nội dung package:
- Trang web tĩnh (index.html, about.html, services.html, blog.html, contact.html, privacy.html, disclaimer.html)
- Bài mẫu trong folder /posts/ (post1.html, post2.html, post3.html)
- /assets/css/style.css
- /admin/ (Netlify CMS scaffold: index.html + config.yml)
- README (this file)

MỤC TIÊU: Đây là bản demo để anh upload lên Cloudflare Pages. Tôi đã thêm scaffold cho Netlify CMS, tuy nhiên để CMS "login & publish" hoạt động hoàn chỉnh cần cấu hình OAuth/Git backend — có 2 lựa chọn chính:

OPTION A (ĐƠN GIẢN, HOẠT ĐỘNG NHANH, RECOMMENDED if you want full GUI editing)
- Host on Netlify (one-click) instead of Cloudflare Pages.
- Steps:
  1. Tạo repo GitHub và push toàn bộ nội dung của thư mục này.
  2. Đăng ký tài khoản Netlify, connect repo, deploy (Netlify hỗ trợ Netlify Identity & Git Gateway).
  3. Vào Netlify dashboard → Site settings → Identity → Enable Identity.
  4. Trong Identity → Services → enable Git Gateway.
  5. Trên Netlify site, vào Settings → Identity → Registration → enable (and optionally allow GitHub login).
  6. Netlify CMS sẽ hoạt động tại https://YOUR_SITE_URL/admin — đăng nhập bằng GitHub và bạn có thể tạo/sửa bài, Netlify sẽ commit thay đổi vào repo tự động.

LỢI ÍCH: không cần server, CMS hoạt động trơn tru, phù hợp nếu anh muốn viết bài trực tiếp qua giao diện.

OPTION B (GIỮ Cloudflare Pages, ít thay đổi, DỄ THỰC HIỆN)
- Giữ hosting trên Cloudflare Pages (như hiện tại) và quản lý nội dung bằng **GitHub web editor** (Hoàn toàn ổn để demo và update vài bài).
- Steps:
  1. Tạo repo GitHub và push nội dung của thư mục này.
  2. Trên Cloudflare Pages, connect project với repo GitHub và deploy từ branch main.
  3. Muốn thêm bài mới: tạo file HTML (hoặc markdown) trong /posts/ trên GitHub web UI → commit → Cloudflare Pages sẽ redeploy tự động.
- LỢI: Giữ Cloudflare Pages, không cần cấu hình Identity/Gateway. Nhược: không có WYSIWYG GUI, nhưng GitHub web editor khá dễ dùng.

OPTION C (GIẢI PHÁP TÙY BIẾN)
- Triển khai một GitHub OAuth proxy (ví dụ netlify-cms-proxy-server) trên một server nhỏ (Heroku / Render) và cấu hình admin/config.yml 'auth_endpoint' để dùng Netlify CMS trên Cloudflare Pages.
- PHỨC TẠP hơn, không đề xuất cho mục đích demo nhanh.

Contact form:
- Trong contact.html, form action hiện là Formspree placeholder:
  action="https://formspree.io/f/{FORMSPREE_ID}"
  - Để hoạt động, đăng ký Formspree và lấy ID form, thay vào chỗ {FORMSPREE_ID}. Formspree sẽ forward email tới hi@bimatclipai.com.
  - Hoặc giữ link mailto:hi@bimatclipai.com để người dùng gửi email từ client.

Tóm lại:
- Nếu anh muốn **WYSIWYG admin** hoạt động nhanh nhất → làm theo OPTION A (chỉ mất ~10 phút nếu anh tạo repo & chuyển host lên Netlify). Em có thể làm hết giúp anh nếu anh muốn.
- Nếu anh muốn **giữ Cloudflare Pages** → theo OPTION B: em sẽ hướng dẫn push repo & connect Cloudflare Pages; anh có thể edit bài qua GitHub web UI (rất đơn giản).

Anh muốn em tiếp tục: 
1) Tạo repo trên GitHub và push code + hướng dẫn chi tiết git commands (em làm file chuẩn sẵn và hướng dẫn) — em có thể hỗ trợ từng bước; hoặc
2) Hướng dẫn chi tiết cách deploy ZIP lên Cloudflare Pages rồi chuyển workflow sửa bài qua GitHub (Option B).
