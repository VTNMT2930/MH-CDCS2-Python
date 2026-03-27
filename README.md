# 🚀 Project Name

Real Estate Price Prediction / Dự đoán giá bất động sản

---

# 📷 Demo

- Notebook: `Source_2200009905_VoTrungNhan.ipynb`
- Dữ liệu mẫu: `real_estate_listings.csv`
- Demo chính: huấn luyện mô hình Random Forest và XGBoost để dự đoán giá nhà, trực quan hóa phân phối dữ liệu và tầm quan trọng của đặc trưng.

---

# ✨ Features

- Xử lý dữ liệu giá bất động sản từ file CSV.
- Chuẩn hóa giá (tỷ/triệu) về đơn vị VNĐ bằng hàm `convert_price_v2`.
- Trích xuất diện tích đất từ chuỗi mô tả bằng `extract_land_area`.
- Tiền xử lý tự động: xử lý missing values, chuẩn hóa đặc trưng số, one-hot encoding cho biến phân loại.
- Huấn luyện và so sánh 2 mô hình hồi quy: Random Forest và XGBoost.
- Đánh giá mô hình bằng MAE, RMSE, R².
- Trực quan hóa dữ liệu và kết quả mô hình (histogram, boxplot, heatmap, scatter thực tế vs dự đoán, feature importance).

---

# 🛠 Tech Stack

- **Ngôn ngữ**: Python
- **Thư viện phân tích dữ liệu**: `pandas`, `numpy`
- **Học máy**: `scikit-learn`, `xgboost`
- **Trực quan hóa**: `matplotlib`, `seaborn`
- **Môi trường chạy**: Jupyter Notebook / VS Code Jupyter

---

# 🏗 System Architecture

Kiến trúc đơn giản, chạy hoàn toàn trong Notebook:

1. **Data Source**: File CSV `real_estate_listings.csv` chứa thông tin bất động sản.
2. **Data Processing Layer**:
   - Hàm xử lý giá và diện tích (`convert_price_v2`, `extract_land_area`).
   - Pipeline tiền xử lý với `ColumnTransformer` (numeric + categorical pipeline).
3. **Model Layer**:
   - `RandomForestRegressor` (scikit-learn).
   - `XGBRegressor` (xgboost).
4. **Evaluation & Visualization**:
   - Tính toán MAE, RMSE, R².
   - Vẽ các biểu đồ phân phối và feature importance.

Hiện tại project **chỉ là mô hình phân tích ngoại tuyến** (offline), chưa có backend/API hay frontend riêng.

---

# 📂 Project Structure

```bash
TieuLuan_2200009905_VoTrungNhan/
├── Source_2200009905_VoTrungNhan.ipynb   # Notebook chính: xử lý dữ liệu, huấn luyện & đánh giá mô hình
├── real_estate_listings.csv              # Dữ liệu bất động sản dạng bảng
└── README.md                             # Tài liệu mô tả dự án
```

---

# ⚙️ Installation & Setup

## 1. Yêu cầu môi trường

- Python 3.8+
- Jupyter Notebook hoặc VS Code với Jupyter Extension

## 2. Cài đặt thư viện

Tạo môi trường ảo (khuyến khích) và cài đặt các thư viện cần thiết:

```bash
python -m venv .venv
.venv\Scripts\activate
pip install pandas numpy scikit-learn matplotlib seaborn xgboost
```

## 3. Chạy Notebook

1. Mở file `Source_2200009905_VoTrungNhan.ipynb` bằng Jupyter hoặc VS Code.
2. Đảm bảo file dữ liệu `real_estate_listings.csv` nằm cùng thư mục với notebook.
3. Chạy lần lượt các cell từ trên xuống dưới.

---

# 🗄 Database Schema

Project sử dụng **file CSV** thay cho cơ sở dữ liệu truyền thống. Cấu trúc chính của `real_estate_listings.csv` (theo kỳ vọng trong notebook):

- `Location`: Vị trí, khu vực của bất động sản.
- `Price`: Giá bất động sản (dạng chuỗi, ví dụ: `5 tỷ 500 triệu`, `2.3 tỷ`, `900 triệu`) – được chuyển về VNĐ.
- `Type of House`: Loại hình nhà (nhà phố, căn hộ, biệt thự, ...).
- `Land Area`: Diện tích đất (chuỗi có thể kèm đơn vị, ví dụ `50 m²`, `Ngang 4m x Dài 10m`).
- `Bedrooms`: Số phòng ngủ.
- `Toilets`: Số phòng vệ sinh.
- `Total Floors`: Tổng số tầng.
- `Main Door Direction`: Hướng cửa chính.
- `Balcony Direction`: Hướng ban công.
- `Legal Documents`: Tình trạng pháp lý (sổ hồng, sổ đỏ, giấy tay, ...).

Nếu cần đưa vào CSDL (MySQL/PostgreSQL, …), có thể tạo bảng `real_estate_listings` với các cột tương ứng, trong đó `Price` và `Land Area` nên lưu ở kiểu số (BIGINT/FLOAT).

---

# 🔌 API Endpoints

Hiện tại project **chưa triển khai API**. Mô hình được sử dụng trực tiếp trong Notebook.

Gợi ý nếu mở rộng thành dịch vụ web:

- `POST /api/predict` – Nhận thông tin bất động sản (JSON) và trả về giá dự đoán.
- `GET /api/health` – Kiểm tra trạng thái dịch vụ.

---

## 👨‍💻 Author

**Võ Trung Nhân**

- 📧 Email: [nhantrung297@gmail.com](mailto:nhantrung297@gmail.com)
- 💼 LinkedIn: [https://www.linkedin.com/in/vtn2907/](https://www.linkedin.com/in/vtn2907/)
- 🐙 GitHub: [@VTNMT2930](https://github.com/VTNMT2930)
- 🌐 Portfolio: [https://nhanit.io.vn/](https://nhanit.io.vn/)

---

<div align="center">
  <p>Made with ❤️ by Nhân IT</p>
  <p>⭐ Star this repo if you find it helpful!</p>
</div>
