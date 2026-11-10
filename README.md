# Personal Cashflow v2.0

Ứng dụng quản lý tài chính cá nhân bằng React + Vite, triển khai được trên Vercel Hobby miễn phí.

## Tính năng
- Tổng quan: tài sản ròng ước tính, thu chi tháng, tiền khả dụng, dư nợ thẻ, dư nợ vay.
- Sổ giao dịch: thu, chi, chuyển khoản, mua bằng thẻ, thanh toán thẻ, phí/lãi thẻ, vay, trả nợ, mua tài sản/đầu tư.
- Tài khoản tiền: tiền mặt, ngân hàng, ví điện tử; số dư đầu kỳ và số dư tính từ sổ giao dịch.
- Thẻ tín dụng: ngân hàng, 4 số cuối, hạn mức, dư nợ đầu kỳ, ngày chốt sao kê, ngày đến hạn, hạn mức khả dụng.
- Vay & công nợ: khoản vay, gốc ban đầu, lãi suất và dư nợ sau các lần trả gốc.
- Tài sản & đầu tư: giá trị ước tính hiện tại.
- Xuất CSV; sao lưu/khôi phục JSON; responsive desktop/mobile.

## Chạy trên Windows
1. Cài Node.js LTS: https://nodejs.org
2. Mở Terminal tại thư mục dự án.
3. Chạy `npm install`, sau đó `npm run dev`.
4. Mở URL local Vite in ra (thường là http://localhost:5173).

## Deploy Vercel miễn phí
1. Đưa toàn bộ thư mục lên GitHub.
2. Vào https://vercel.com → Add New → Project → import repository.
3. Build command `npm run build`, output directory `dist` (Vercel thường tự nhận diện Vite).
4. Nhấn Deploy. Vercel cấp tên miền `*.vercel.app`.

## Hạch toán thẻ tín dụng
- `Chi bằng thẻ tín dụng`: ghi nhận chi tiêu và tăng dư nợ thẻ.
- `Thanh toán thẻ`: giảm số dư tài khoản thanh toán và giảm dư nợ thẻ; KHÔNG ghi nhận thêm chi phí, tránh tính trùng.
- `Phí / lãi thẻ`: hiện được ghi nhận vào dư nợ thẻ và chi tiêu.

## Lưu ý quan trọng
- Phiên bản này lưu dữ liệu trong localStorage trên trình duyệt/thiết bị hiện tại; không tự đồng bộ nhiều thiết bị và không có đăng nhập.
- Sao lưu JSON định kỳ. Xóa dữ liệu trình duyệt có thể làm mất dữ liệu ứng dụng.
- Đây là sổ theo dõi thủ công, không kết nối API ngân hàng và không tự lấy sao kê. Không nhập số thẻ đầy đủ, CVV, PIN, mật khẩu ngân hàng.
- Dư nợ vay hiện theo dõi trả gốc; lãi vay cần ghi riêng như khoản chi. Giá trị tài sản/đầu tư là số người dùng tự cập nhật.
- Vercel Hobby phù hợp dự án cá nhân; hạn mức miễn phí có thể thay đổi theo chính sách Vercel.
