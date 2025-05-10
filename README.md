Dự án: Web Scraper cho Báo Chính Phủ
Dự án này là một công cụ web scraper giúp thu thập dữ liệu từ một bài viết cụ thể trên trang web Báo Chính Phủ. Công cụ sẽ thu thập các dữ liệu bao gồm tiêu đề, mô tả, hình ảnh chính và nội dung bài viết, sau đó lưu vào file Excel. Script được cài đặt để tự động chạy vào lúc 6h sáng mỗi ngày.

Yêu cầu
Python 3.6 trở lên

Các thư viện: requests, beautifulsoup4, pandas, openpyxl, schedule

Cài đặt
Clone repository: Đầu tiên, bạn cần clone dự án về máy tính của mình bằng lệnh sau:

git clone https://github.com/username/dự-án.git
cd dự-án
Thiết lập môi trường ảo (Tùy chọn): Khuyến khích sử dụng môi trường ảo để quản lý thư viện. Để tạo môi trường ảo, chạy lệnh sau:

python -m venv venv
Kích hoạt môi trường ảo:

Trên Windows:

.\venv\Scripts\activate
Trên macOS/Linux:

source venv/bin/activate
Cài đặt thư viện: Cài đặt các thư viện cần thiết bằng lệnh:

pip install -r requirements.txt
Hoặc nếu không có file requirements.txt, bạn có thể cài từng thư viện:

pip install requests beautifulsoup4 pandas openpyxl schedule
Sử dụng
Sau khi clone và cài đặt thư viện, bạn có thể chạy script để thu thập dữ liệu từ bài viết trên Báo Chính Phủ bằng lệnh:

python baitaplon.py
Script sẽ thu thập dữ liệu của bài viết, bao gồm tiêu đề, mô tả, hình ảnh, nội dung, và lưu vào một file Excel (dạng .xlsx).

Sau khi script chạy xong, bạn có thể kiểm tra file Excel được lưu trong thư mục chứa script với tên file bao gồm ngày và giờ (ví dụ: baochinhphu_20230510_060000.xlsx).

Lên lịch tự động
Để tự động chạy script vào lúc 6h sáng hàng ngày, bạn có thể sử dụng một trong các phương pháp sau:

Phương pháp 1: Sử dụng Task Scheduler (Windows)
Mở Task Scheduler trên máy Windows.

Chọn Create Basic Task.

Chọn Trigger là Daily, và thiết lập thời gian là 06:00 AM.

Chọn Action là Start a program.

Browse đến đường dẫn Python (python.exe):

Ví dụ: C:\Users\YourName\AppData\Local\Programs\Python\Python312\python.exe

Thêm đường dẫn đầy đủ đến script vào ô Add arguments:

Ví dụ: "C:\path\to\your\script\baitaplon.py"

Hoàn tất thiết lập và task sẽ tự động chạy vào lúc 6h sáng mỗi ngày.

Phương pháp 2: Sử dụng Python Scheduling
Bạn cũng có thể thiết lập lịch tự động ngay trong mã Python bằng cách sử dụng thư viện schedule. Dưới đây là cách thêm lịch trình vào mã:

import schedule
import time

# Định nghĩa công việc cần làm
schedule.every().day.at("06:00").do(run_scraper)

# Giữ cho chương trình chạy
while True:
    schedule.run_pending()
    time.sleep(60)
Bước 3: Chạy script nền
Sau khi thiết lập xong lịch tự động, bạn có thể để script chạy nền bằng cách sử dụng lệnh:

python baitaplon.py
Script sẽ kiểm tra mỗi phút và tự động thực thi vào đúng giờ đã lên lịch.

Giấy phép
Dự án này sử dụng Giấy phép MIT - xem chi tiết tại file LICENSE.
