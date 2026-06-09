# ChuyenDeTotNghiep2
Hướng dẫn cài đặt và chạy chương trình
#Giới thiệu  
Xây dựng hệ thống kho dữ liệu & phân tích hiệu quả hoạt động kinh doanh dựa trên 

#Cài đặt công cụ sử dụng & môi trường
- Python
- Pandas
- Owlready2
- RDFLib
- Streamlit
- Protégé
- Pellet Reasoner
- OWL
- SWRL
- SPARQL
Mở Terminal thực hiện lệnh cài đặt thư viện cốt lõi: pip install pandas owlready2 rdflib streamlit openpyxl

  #Quy trình vận hành hệ thống
Bước 1: Thiết kế cấu trúc nền tảng Ontology bằng Protégé
- Khởi động phần mềm Protégé
- Thực hiện thiết kế mô hihf tri thức lý thuyết 
- Tạo class, Object, data properties
- Lưu thư mục đặt tên (ví dụ: Online_Retail_Ontology.rdf) -> Thành được file dữ liệu trước suy diễn. 
Bước 2: Lập trình module ánh xa & nạp cá thể tự động
- Kích hoạt công cụ Jupyter Notebook tạo tệp mới và đặt tên (ví dụ: CDTN.ipynb)
- Tiến hành viết mã nguồn: Nạp dữ liệu từ file sạch, dùng thư viện owlready2 mở file Online_Retail_Ontology nãy vừa tạo ...
- Viết câu lệnh cuối để lưu lại toàn bộ cơ sở tri thức hoàn chỉnh (đầy đủ các lớp cấu trúc & dữ liệu cá thể sau suy diễn) -> Thành một file dữ liệu mới (ví dụ:CD2_Tuan2_Final_With_Segment.owl)
Bước 3: Kiểm tra kết quả
- Sau khi hệ thống đã sinh ra file CD2_Tuan2_Final_With_Segment.owl thì khởi động lại phần mềm Protégé và chọn file mở lên.
- Kích hoạt công cụ viết luật SWRLTab để hiển thị ra cửa sổ chứa các câu lệnh suy diễn
- Sau khi viết xong câu lệnh nhấn chạy câu lệnh 
- Thực thi bộ lý giải để chạy câu lệnh suy diễn dữ liệu:
  + Chọn trên thanh menu chính của Protégé chọn mục Reasoner.
  + Chọn bộ cấu hình bộ lập luận Pellet
  + Tiếp tục chọn Start Reasoner
- Kiểm tra Kết quả thựuc thi lệnh suy diễn
Bước 4: Tạo môi trường kiểm thử cú pháp truy vấn ngữ nghĩa mã nguồn
- Mở Jupyter Notebook tạo file mới (ví dụ: Test_Ontology.ipynb)
- Viết mã nguồn sử dụng thư viện rdflib để đọc file tri thức ngữ nghĩa cuối cùng (CD2_Tuan2_Final_With_Segment.owl).
- Chạy các câu lệnh đồ thị bằng ngôn ngữ SPARQL nhằm kiểm thử tính đúng đắn & tốc độ trích xuất thông tin.
Bước 5: lập trình giao diện Web (VSCode)
- Mở VSCode tạo file mã nguồn Python (ví dụ:GDCDTN.py)
- Sử dụng thư viện để viết giao diện theo luồng xủ lý:
  + Sử dụng rdflib nạp tệp tri thức đã suy diễn hoàn chỉnh CD2_Tuan2_Final_With_Segment.owl
  + Thiết lập giao diện bố cục dạng các thẻ Tab: tab1, tab2, tab3 = st.tabs(Khách hàng VIP, Cảnh báo, Khuyến nghị).
  + Bên trong mỗi Tab, viết các câu lệnh truy vấn ngữ nghĩa bằng ngôn ngữ SPARQL để quét vào file OWL thành phẩm, lấy ra danh sách các thực thể đã được phân loại sẵn, chuyển đổi định dạng từ Graph sang Bảng phẳng (Pandas DataFrame) và hiển thị lên màn hình thông qua hàm st.dataframe().
- Khởi chạy giao diện:
  + Mở Terminal tại VSCode chạy câu lệnh theo tên đã đặt (ví dụ:streamlit run GDCDTN.py)
  + Hệ thống sẽ khởi tạo một local server và tự động mở ra trình duyệt Web.
