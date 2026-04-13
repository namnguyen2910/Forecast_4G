#  Mobile Subscriber 4G Upgrade Prediction
1. Giới thiệu
   - Dự án phân tích và xây dựng mô hình dự đoán khả năng thuê bao di động chuyển sang sử dụng 4G, dựa trên dữ liệu hành vi sử dụng dịch vụ.
2. Các kĩ năng sử dụng
   - Python Libraries : Pandas | Matplotlib | Seaborn | Scikit-learn
   - Data Processing: Xử lý NULL | Label Encoding | MinMaxScaler | Feature Engineering
   - Machine Learning: Logistic Regression | SVM | Decision Tree | Random Forest
   - Evaluation: Confusion Matrix | Precision | Recall | F1-Score
3. Tập dữ liệu của dự án:
- Bộ dữ liệu là file định dạng .csv gồm 200.000 dòng và 182 cột.
- Các biến dữ liệu bao gồm:
  + 3 biến dữ liệu danh mục: thiet_bi, ha_tang,tuoi_khach_hang_cut_level.
  + 3 biến dữ liệu danh mục nhị phân: thuc_4g, is_dcom, is_sim_4g.
  + 17 biến dữ liệu số: cuoc_goc_gprs, nod_psll_thoai,so_lan_nap_the, nod_psll_data, so_lan_nap_topup ....
- Các biến này đều có 10 giá trị tương ứng với 10 tháng gần nhất trừ các biến tuoi_khach_hang_cut_leve và user_id
- Bộ dữ liệu có chứa giá trị NULL (12262 giá trị)
4. Nội dung chính
B1: Xử lý tiền dữ liệu
- Đọc và làm sạch dữ liệu từ file CSV
- Xử lý giá trị NULL bằng fillna(0) cho các cột số
- Encode biến danh mục: chuyển thiết bị (4G/5G → 1/0), hạ tầng mạng (4G → 1/0)
- Label Encoding cho cột độ tuổi khách hàng
- Tạo tập dữ liệu chuỗi thời gian 5 tháng liên tiếp, chuẩn hóa tên feature theo từng kỳ
- Gán nhãn target: 1 = chuyển sang dùng 4G, 0 = không chuyển

B2: Chuẩn bị dữ liệu đầu vào
- Loại bỏ cột không cần thiết (thuc_4g, user_id), tách features / target
- Chuẩn hoá toàn bộ features về [0, 1] bằng MinMaxScaler
- Chia tập train/test theo tỷ lệ 80/20, random_state=42

B3: Huấn luyện mô hình và so sánh 4 mô hình phân loại:
- Logistic Regression – max_iter=250
- LinearSVC – Support Vector Machine tuyến tính
- Decision Tree – max_depth=16, min_samples_split=7, max_leaf_nodes=30
- Random Forest – n_estimators=100, max_depth=10, min_samples_split=6

B4: Đánh giá kết quả
- So sánh độ chính xác train/test của cả 4 mô hình để phát hiện overfitting
- Confusion Matrix trực quan hóa kết quả dự đoán
- Báo cáo Precision, Recall, F1-Score theo từng nhãn

5. Đánh giá
- So sánh hiệu suất mô hình:
