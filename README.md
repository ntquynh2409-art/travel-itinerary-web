Họ và tên: _Nguyễn Thủy Quỳnh_
MSSV: _24127528_

**AI Travel Planner**

**Tính năng chính**
 - Tạo lịch trình động: Nhận kế hoạch du lịch chi tiết theo ngày (Sáng/Trưa/Tối) chỉ bằng cách nhập điểm đi, điểm đến, thời gian và sở thích.
 - Backend LLM mạnh mẽ: Sử dụng mistral (thông qua Ollama) chạy trên Colab/Kaggle để tạo ra các gợi ý du lịch sáng tạo và thực tế.
 - Xác thực người dùng: Tích hợp Firebase Authentication cho phép người dùng đăng ký và đăng nhập an toàn.
 - Lưu trữ lịch sử: Tự động lưu mọi lịch trình đã tạo vào Cloud Firestore, giúp người dùng dễ dàng xem lại các chuyến đi cũ trong tab "Lịch sử".

**Công nghệ sử dụng**
 - Frontend: Streamlit
 - LLM Backend: Ollama (Mistral)
 - Database & Auth: Google Firebase (Authentication & Cloud Firestore)
 - Deployment (Backend): Google Colab / Kaggle (với Cloudflare Tunnel)
 - Core: Python 3

**Cài đặt & Khởi chạy**
1. Backend (Chạy trên Colab/Kaggle)
 - Mở file notebook .ipynb trên Google Colab hoặc Kaggle.
 - Chạy các cell để cài đặt Ollama, tải model mistral và tạo Cloudflare Tunnel.
 - Copy file firebase.json (Service Account Key) vào thư mục của Colab.
 - Copy URL trycloudflare.com mà Ollama tạo ra.

2. Frontend (Chạy trên máy local hoặc Streamlit Cloud)
 - Clone repository này:
$ git clone https://github.com/ntquynh2409-art/travel-itinerary-web.git
$ cd travel-itinerary-web
 - Tạo môi trường ảo và cài đặt thư viện:
$ python -m venv venv
$ source venv/bin/activate  (Trên Windows: venv\Scripts\activate)
$ pip install -r requirements.txt
(Nội dung requirements.txt)
streamlit
requests
firebase-admin
 - Tạo file ollama_url.txt và dán URL từ Bước 1 vào đó.
 - Chạy ứng dụng Streamlit:
$ streamlit run app.py
