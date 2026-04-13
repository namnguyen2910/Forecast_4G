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
- 
