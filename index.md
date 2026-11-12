# BẢN BÀN GIAO CUỘC TRÒ CHUYỆN – NHÓM 22 / CÁC CÔNG NGHỆ LẬP TRÌNH HIỆN ĐẠI

> Cập nhật: **13/11/2026**. Tài liệu Markdown để mở trong VS Code và tiếp tục ôn thực hành/vấn đáp. Ghi nhận **những gì người dùng đã báo cáo hoặc có ảnh chứng minh**, không coi đoạn code được hướng dẫn là đã kiểm thử nếu chưa có xác nhận. Các mã ở phần phụ lục được **giữ nguyên như những đoạn đã được gửi trong cuộc trò chuyện**; những chỗ chưa hoàn thiện được ghi chú bên ngoài khối code.

## 0. TÓM TẮT NHANH – ĐỌC TRƯỚC KHI TIẾP TỤC

- **Mục tiêu:** Ôn thi vấn đáp ngẫu nhiên thành viên nhóm, luyện các bài thực hành tại chỗ của đề tài _Tìm hiểu hệ sinh thái Google: Apps Script, AppSheet, Looker Studio, Firebase_; hiểu kiến trúc đồ án từ vựng **Vocab App**.
- **Vai trò cá nhân:** Phụ trách **Phần B – AppSheet**; báo cáo cá nhân đã chốt **V3, tối giản đen trắng, khoảng 10 trang**, tập trung ba bài thực hành cửa hàng xe đạp; **không nhận phần quản trị từ vựng là việc cá nhân đã triển khai hoàn chỉnh**.
- **Đã có ảnh xác nhận:** Website **Chương 4 Firebase Realtime Database ghi được user**, Console xuất hiện `Đã ghi dữ liệu lên Firebase.`; dashboard **Chương 5 Looker Studio đã hiện KPI/biểu đồ/bảng**.
- **Chưa có ảnh xác nhận hoàn tất:** Firebase đăng nhập Google Chương 5 sau khi sửa domain; Firestore CRUD + Security Rules Chương 6; hai Calculated Fields Looker Chương 6; 12 đề thực hành trong PDF.
- **Đang dừng:** Vừa đọc hai tài liệu `huong-dan-chi-tiet.pdf` (12 đề, 30 trang) và `HD CNLTHD.docx` (17 trang), đã **phân loại lộ trình và ôn lý thuyết Đề 5–6**, nhưng **chưa thao tác/kiểm thử Đề 5 trên AppSheet**. Bước phù hợp nhất để tiếp tục: **Đề 5 – cải tiến Bot cảnh báo và chặn tồn kho âm**, sau đó Đề 6 – Ref và Virtual Column. Có thể chuyển sang đề khác nếu người dùng chỉ định.

### Đề xuất câu mở đầu cho cuộc chat mới

> Mình tiếp tục ôn 12 đề thực hành của Nhóm 22 từ file `README_TIEP_TUC_ON_TAP.md`. Mình là người phụ trách AppSheet. Hãy hướng dẫn **Đề 5** theo từng bước trực tiếp trong AppSheet; hỏi/kiểm tra kết quả từng bước và giúp xử lý lỗi thực tế. Chú ý chưa đụng vào dữ liệu/project nhóm nếu chưa tạo bản sao.

---

## 1. Nguồn tài liệu, tên file và sản phẩm đã tạo

### Tài liệu người dùng đã cung cấp

| Tên file                                   | Nội dung                                                                                      | Vai trò                                          |
| ------------------------------------------ | --------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `Báo cáo_CCNLTHĐ(1).docx`                  | Báo cáo nhóm, phần A Apps Script, B AppSheet, C Looker, D Firebase, E đồ án tổng hợp          | Căn cứ môn học chính                             |
| `Báo cáo cá nhân - Phạm Thanh Tuấn(1).pdf` | Báo cáo tham khảo, phần Looker Studio                                                         | Tham khảo bố cục và Chương 3–6                   |
| `Báo cáo cá nhân - Nguyễn Đình Hùng.pdf`   | Báo cáo cá nhân tham khảo                                                                     | Đối chiếu văn phong và cách ghi công việc        |
| `huong-dan-chi-tiet.pdf`                   | 30 trang, **12 đề thực hành**, trang 14–17 là AppSheet đề 5–6                                 | Tài liệu ôn thi hiện tại                         |
| `HD CNLTHD.docx`                           | 17 trang hướng dẫn Vocab Demo, Dictionary, AppSheet, Looker, Apps Script, Firebase            | Demo đồ án chung                                 |
| `index.html`, `main.js` (tải lên trước đó) | **Bản ban đầu** của Chương 4 Firebase                                                         | Lưu nguyên văn bên dưới; có lỗi import ở bản gốc |
| `de-thuc-hanh.pdf`, `dap-an.pdf`           | Được **nhắc đến trong** `huong-dan-chi-tiet.pdf`, **chưa được tải lên** trong cuộc trò chuyện | Nếu cần đối chiếu đề gốc thì phải xin file       |

### Các artifact đã tạo trong cuộc trò chuyện

- `Bao_cao_ca_nhan_Le_Van_Thong_AppSheet.docx` / `.pdf` – báo cáo AppSheet V1.
- `Bao_cao_ca_nhan_AppSheet_Le_Van_Thong_PHAN_TICH_TRIEN_KHAI.docx` / `.pdf` – V2; có chương về tích hợp hệ thống từ vựng nên **không chọn làm bản cuối**.
- **`Bao_cao_ca_nhan_Le_Van_Thong_AppSheet_V3_Toi_gian.docx` / `.pdf`** – **bản đã chốt**: phong cách học thuật đen trắng, mục lục đơn giản, không biến phần thiết kế quản trị từ vựng thành thành tích cá nhân.
- `Bang_cong_no_theo_anh.xlsx` – bảng công nợ dựng từ ảnh, **24 dòng, 6 cột**; dùng làm dữ liệu Hello World Looker Studio.
- Mã nguồn Firebase Chương 4/5/6 ở cuối tài liệu này và các thư mục cùng gói ZIP.

> Khi chuyển môi trường VS Code, hãy chép kèm các file nguồn và giữ cấu trúc thư mục. Các bản DOCX/PDF/XLSX trên **là tên gốc**, không phải đường dẫn tuyệt đối trên máy người dùng.

## 2. Quyết định đã chốt cho báo cáo cá nhân AppSheet

- Dùng **V3 tối giản**, không trang trí màu rực hoặc mục lục dạng slide.
- Tập trung **Phần B – AppSheet**: (1) Form nhập liệu xe đạp, (2) Khách hàng–Đơn hàng quan hệ 1–N, (3) Bot email cảnh báo tồn kho.
- Trong báo cáo **nhóm**, AppSheet được thiết kế cho quản trị từ vựng Vocab App, nhưng **không ghi trong báo cáo cá nhân như phần đã triển khai/kiểm thử trực tiếp** nếu thiếu chứng cứ.
- Vấn đáp có thể hỏi **cả công nghệ nhóm**, không chỉ phần mình làm. Phải trả lời được _công nghệ làm gì → thực hành ra sao → tại sao dùng → dữ liệu đi đâu → bảo mật thế nào_.
- Phải phân biệt **thiết kế**, **code mẫu**, **đã chạy thành công**, và **chưa kiểm thử**.

## 3. Các bài AppSheet đã học và đề tiếp theo

### AppSheet trong báo cáo nhóm (Phần B)

- **Chương 5:** Google Sheets `Bicycle Store` (bảng `Xe Đạp`), tạo AppSheet từ nguồn có sẵn, Form View, thêm/sửa/xóa dữ liệu, cấu hình cột Key.
- **Chương 6:** bảng `Khách Hàng` (Key `Mã KH`), `Đơn Hàng` (Key `Mã ĐH`); cột `Mã KH` trong đơn hàng có Type **Ref**, Source Table **Khách Hàng**; tự sinh danh sách đơn hàng liên quan (Related...); quan hệ **1 khách hàng → N đơn hàng**.
- **Chương 7:** Automation Bot khi hàng trong `Xe Đạp` được **Updates**, điều kiện gốc theo báo cáo `[SoLuongTon] < 5` (hoặc cột tên có dấu), Send an Email.

### Đề 5 trong `huong-dan-chi-tiet.pdf` trang 14–15 – CHƯA THỰC HÀNH TRỰC TIẾP

**Điều kiện:** Có bản sao Google Sheets Bicycle Store, AppSheet app, Bot email của Chương 7.

**Thay condition từ `x < 5` thành chỉ cảnh báo khi băng qua ngưỡng:**

```appsheet
AND([_THISROW_BEFORE].[Số lượng tồn] >= 5, [_THISROW_AFTER].[Số lượng tồn] < 5)
```

**Chặn tồn kho âm – tại Valid If của cột Số lượng tồn:**

```appsheet
[_THIS] >= 0
```

**Email subject:**

```text
Cảnh báo tồn kho: <<[Tên xe]>> còn <<[Số lượng tồn]>>
```

**Kiểm thử đề 5:**

| Xe            | Tồn trước → sau | Mong đợi                         |
| ------------- | --------------: | -------------------------------- |
| XB001 MTB X1  |          10 → 9 | Lưu, không gửi mail              |
| XB002 Road R2 |           6 → 4 | Lưu, gửi đúng 1 email            |
| XB003 City C3 |           3 → 2 | Lưu, không gửi mail              |
| XB004 MTB T4  |          4 → -1 | Bị `Valid If` từ chối, không lưu |

Bẫy: điều kiện **BEFORE/AFTER** chỉ có ý nghĩa đúng trong ngữ cảnh cập nhật. Chọn đúng tên cột thực tế; `SoLuongTon` và `Số lượng tồn` **không tự thay thế cho nhau**.

### Đề 6 trong PDF trang 16–17 – CHƯA THỰC HÀNH TRỰC TIẾP

- Google Sheets Bicycle Store có `Khách Hàng`: Mã KH, Tên KH, Email; `Đơn Hàng`: Mã ĐH, Mã KH, Ngày Mua, **ThanhTien** (đề yêu cầu thêm nếu bảng cũ chưa có).
- AppSheet → Data → Đơn Hàng → **Regenerate structure** để nhận cột mới. Đặt `ThanhTien` kiểu Number/Price.
- Đảm bảo cột `Mã KH` của `Đơn Hàng` là Ref đến `Khách Hàng`.
- Thêm **3 Virtual Column** trong `Khách Hàng`:

```appsheet
COUNT([Related Đơn Hàngs])
```

```appsheet
SUM([Related Đơn Hàngs][ThanhTien])
```

```appsheet
IF([SoDonHang] >= 3, "VIP", "Thường")
```

- Tên cột ảo lần lượt: `SoDonHang`, `TongChi`, `HangKhach`.
- Kết quả dự kiến: KH01 = 3 đơn, 10.000.000, VIP; KH02 = 1 đơn, 1.200.000, Thường; KH03 = 0 đơn, 0, Thường. Thêm đơn 1.000.000 cho KH03 → 1 đơn, 1.000.000.
- **Virtual Column** chỉ tính trong AppSheet, không phải cột lưu vật lý trong Google Sheets. Tên `Related Đơn Hàngs` chỉ là ví dụ, phải chọn đúng cột AppSheet sinh ra.

## 4. Firebase – tiến độ, lỗi và các bài Chương 4–6

**Project Firebase cá nhân:** `demo1-498b8` (khác với project demo Vocab của nhóm).

- Auth domain: `demo1-498b8.firebaseapp.com`
- Realtime Database URL đúng (khu vực Asia Southeast 1): `https://demo1-498b8-default-rtdb.asia-southeast1.firebasedatabase.app`
- Firebase cấu hình client có trong mã nguồn đầy đủ ở phần cuối. **`apiKey` config client không phải service-account private key**. Tuyệt đối không đưa service-account JSON/private key vào mã web hay Markdown công khai.

### Chương 4 – đã có ảnh Console báo ghi thành công

- File đầu tiên người dùng tải lên: `index.html`, `main.js`; `index.html` có nút `#addUser`, `#status`; `main.js` ban đầu import kiểu npm không có bundler và thiếu import Realtime Database.
- Sau khi chuyển sang CDN và bổ sung `getDatabase`, `ref`, `push`, `set`, đã gặp cảnh báo `Database lives in a different region`; sửa đúng `databaseURL` là **Asia Southeast 1**.
- Lỗi `favicon.ico 404`: không ảnh hưởng chức năng. Cảnh báo `[Violation] Permissions policy violation: unload is not allowed in this document` không làm thao tác ghi thất bại.
- **Ảnh có `Đã ghi dữ liệu lên Firebase. main.js:43`** sau khi nhấn thêm user: đủ bằng chứng hàm ghi trả về thành công. Chưa có ảnh Realtime Database → Data để xác nhận trực quan nhánh `users`.

### Chương 5 – Google Sign-In; chưa có ảnh xác nhận sửa xong

- Đã hướng dẫn bật **Firebase Authentication → Sign-in method → Google**, thêm giao diện Login / Logout / tên & email.
- Ảnh chụp lỗi `auth/unauthorized-domain`; Console ghi rõ `127.0.0.1` không được cho phép. Đã hướng dẫn thêm **`127.0.0.1`** trong Authentication → Settings → Authorized domains (không `http://`, không `:5500`) rồi tải lại.
- Người dùng sau đó nói “oke tiếp chương 6”, nhưng **không có ảnh mới chứng minh đăng nhập Google thành công**.

### Chương 6 – Firebase Auth + Cloud Firestore + Security Rules; mới được hướng dẫn

- Chương 6 **dùng Cloud Firestore (Collection → Document)**, không phải Realtime Database của Chương 4.
- Thiết kế ứng dụng To-do: Google Login, thêm/sửa/xóa công việc, `onSnapshot()` xem realtime, `where("uid","==", uid)` để lọc công việc người đăng nhập.
- Dữ liệu `tasks/{docId}` chứa `text`, `uid`, `name`, `createdAt`.
- Security Rules ở phần code cuối: `request.auth.uid` phải bằng chủ sở hữu; chỉ cho sửa `text` (các trường khác không được sửa). Đây là code **đã hướng dẫn**, **chưa xác nhận Publish/test**.
- Bài kiểm thử cần làm: A thêm/sửa/xóa; B không đọc/sửa được task A; đăng xuất/đăng nhập lại thấy đúng dữ liệu.

**Quan trọng khi chuyển sang PDF Đề 9:** Rules của bài Chương 6 chỉ cho sửa `text`, nên **không cho phép cập nhật `done`**. Phải **chủ động sửa Rules** có kiểm soát trước khi dùng `updateDoc(...,{ done: true })`. Không sửa ngầm trong code được lưu nguyên văn ở phụ lục.

## 5. Looker Studio – Chương 3–6 đã học và kết quả dashboard

### Chương 3: Hello World – công nợ

- File `Bang_cong_no_theo_anh.xlsx` chuyển thành Google Sheets, **24 dòng/6 cột**: `ngày phát sinh`, `tên con nợ`, `tên chủ nợ`, `số tiền nợ`, `ghi chú`, `Trạng thái`.
- Trong Looker Studio: Blank Report → Google Sheets → chọn nguồn → Add chart Table/Heatmap.
- **Dimension:** `tên con nợ`; **Metric:** Record Count. Đếm số **dòng phát sinh nợ**, không SUM số tiền để ra số lần nợ. Có thể chọn bảng nhiệt.
- Chưa có ảnh thực hành bài công nợ được xác nhận.

### Chương 4: các khái niệm và Blending Data

- Data Source, Dimension, Metric, Chart, Report, Filter, Control, Theme & Layout, Sharing, Blending Data.
- Bài minh họa: `so khach(Date, SoKhach)` JOIN `doanh thu(Date, DoanhThu)` theo `Date`; cả hai cột khóa phải cùng kiểu dữ liệu và cùng mức chi tiết để không nhân dòng.

### Chương 5: Dashboard nhập kho – **đã có ảnh**

- Nguồn Google Sheets theo báo cáo nhóm: `https://docs.google.com/spreadsheets/d/1lZMhiy3B-Rkr1ls5NrMB1aHzaH0ERB-PNO9-94ZChic/edit`
- Các cột: `ngay_nhap`, `ten_san_pham`, `hang_sx`, `sl_nhap`, `sl_xuat`, `sl_ton`, `gia_nhap`, `tong_tien`, `nhap_kho_id`…
- Đã có ảnh dashboard `Dashboard theo dõi nhập hàng và tồn kho` với **KPI số lượng nhập 31.785, tổng tiền nhập 471.260.000.000, số lượng tồn 27.234**; có donut theo hãng, biểu đồ đường, bảng chi tiết.
- Đã chỉ ra **biểu đồ đường đang sắp xếp tháng sai thứ tự thời gian**. Cần chọn Dimension dạng Year Month từ `ngay_nhap`, Sort theo ngày **Ascending**; không Sort theo `sl_nhap`.
- Các số KPI **chỉ xác nhận xuất hiện trên giao diện, chưa được đối chiếu Google Sheets**.
- Có thể thêm bộ lọc hãng (`hang_sx`), Date range, tên/đơn vị KPI.

### Chương 6: Calculated Fields – mới hướng dẫn, chưa có ảnh kết quả

```sql
GiaTriTonKho = sl_ton * gia_nhap
```

```sql
TyLeHangTon = SUM(sl_ton) / SUM(sl_nhap)
```

- Đây là công thức **theo báo cáo nhóm Chương 6**, tỷ lệ hàng tồn **theo số lượng**, dạng %.
- Với hai KPI ảnh trên, tỷ lệ 27.234 / 31.785 ≈ **85,68%** chỉ là kiểm tra sơ bộ khi cùng phạm vi dữ liệu/lọc, **chưa xác nhận bằng calculated field**.
- Nên tránh chia cho 0, và không SUM tỷ lệ đã tổng hợp một lần nữa.

**Khác biệt cần nhớ:** Báo cáo cá nhân Tuấn và **PDF Đề 7** dùng tỷ lệ theo **giá trị tiền**:

```sql
SUM(sl_ton * gia_nhap) / SUM(tong_tien)
```

Công thức này **khác** công thức `SUM(sl_ton)/SUM(sl_nhap)` trong Chương 6 báo cáo nhóm. Nếu thầy hỏi, giải thích rõ **tỷ lệ giá trị tiền** vs **tỷ lệ số lượng**; không đánh đồng.

## 6. 12 đề trong `huong-dan-chi-tiet.pdf` – bản đồ ôn thi

|  Đề | Công nghệ         | Đầu vào/chính sách                                         | Kết quả dự kiến                                                  | Trạng thái            |
| --: | ----------------- | ---------------------------------------------------------- | ---------------------------------------------------------------- | --------------------- |
|   1 | Apps Script       | PropertiesService + LockService cấp mã phiếu               | `PH-0001`, `PH-0002`, `PH-0003`, reset rồi `PH-0001`             | Chưa thực hành        |
|   2 | Apps Script/Forms | Form 6 câu, có 3 phản hồi; đóng khi đạt giới hạn           | Limit 3 → đóng; limit 5 → mở                                     | Chưa thực hành        |
|   3 | Apps Script       | Installable `onFormSubmit` gửi email nếu hài lòng <= 2     | Điểm 2 gửi mail, 4 bỏ qua                                        | Chưa thực hành        |
|   4 | Apps Script       | Thêm 1 câu Checkbox, tránh trùng, di chuyển vị trí 3, xóa  | Form 6→7→7→6                                                     | Chưa thực hành        |
|   5 | AppSheet          | Điều kiện băng qua ngưỡng và Valid If                      | 10→9 không mail, 6→4 mail, 3→2 không, 4→−1 lỗi                   | **Đang chuẩn bị làm** |
|   6 | AppSheet          | Ref + 3 Virtual Columns                                    | KH01 3/10 triệu/VIP; KH02 1/1,2 triệu; KH03 0                    | Chưa thực hành đề mới |
|   7 | Looker            | 4 dòng hàng tồn + CASE phân loại, tỷ lệ giá trị            | Tồn 287 triệu; lọc Sắp hết 66 triệu                              | Chưa thực hành đề mới |
|   8 | Firebase          | Rules cho tasks; xác thực UID + độ dài text 1–200          | 8 case allow/deny                                                | Chưa thực hành đề mới |
|   9 | Firebase          | task `done` + `onlyPending`, realtime                      | 4 task, lọc còn 2; không thấy task người khác                    | Chưa thực hành đề mới |
|  10 | Vocab Apps Script | `Filter.gs`: level/pos/keyword, không phân biệt hoa thường | test 5 trường hợp; `A1`→cat,dog; `b1+noun`→eagle; `CA`→cat,Camel | Chưa thực hành        |
|  11 | Vocab Apps Script | `Import.gs`: slug chủ đề, loại trùng (topic,word)          | nhập 4, bỏ 2; pets, wild-animals                                 | Chưa thực hành        |
|  12 | Looker Vocab      | `NhomLevel` + `COUNT_DISTINCT(topic)` + bộ lọc             | tất cả 8 từ/4 chủ đề/5-2-1; Animal 5/2/3-2-0                     | Chưa thực hành        |

### Công thức/trọng điểm đề 7 (PDF trang 18–19)

Data test 4 dòng:

| ten_xe  | hang  | sl_ton | gia_nhap | tong_tien |
| ------- | ----- | -----: | -------: | --------: |
| MTB X1  | Giant |      3 | 10000000 |  50000000 |
| Road R2 | Giant |     12 |  8000000 | 120000000 |
| City C3 | Trek  |     25 |  5000000 | 150000000 |
| MTB T4  | Trek  |      4 |  9000000 |  63000000 |

```sql
CASE
  WHEN sl_ton < 5 THEN "Sắp hết"
  WHEN sl_ton < 20 THEN "Bình thường"
  ELSE "Dồi dào"
END
```

- `GiaTriTonKho = sl_ton * gia_nhap`.
- `TyLeHangTon = SUM(sl_ton * gia_nhap) / SUM(tong_tien)`.
- Không lọc: tổng 287.000.000; Giant 126.000.000 & 74,12%; Trek 161.000.000 & 75,59%. Lọc `Sắp hết`: còn 66.000.000; tỷ lệ 58,41%.

### Trọng điểm Đề 8 và 9 (PDF trang 20–24)

- Đề 8: rules tạo/đọc/sửa/xóa dựa trên UID. `resource.data` là bản ghi hiện tại; `request.resource.data` là bản ghi sau ghi. Có ràng buộc `text` độ dài 1–200; dùng Rules Playground để kiểm tra quyền.
- Đề 9: thêm `done: false`; tích checkbox → `updateDoc` cho `done`; lọc `where("uid","==",uid)` và `where("done","==",false)`; `onSnapshot` cập nhật ngay. **Phải mở Rules cho `done`** và kiểm tra tương thích với các task cũ chưa có trường `done`.
- Code PDF cho Đề 9 dùng DOM ID `login`, `logout`, `user-info`, `task-area`, `addTask`... còn code Chương 6 đã được trợ lý gửi dùng `loginBtn`, `logoutBtn`, `userInfo`, `taskSection`, `taskForm`... → **không dán lẫn từng đoạn mà không sửa ID**.

### Đề 10, 11, 12 (PDF trang 25–30)

- `Filter.gs`: `filterWords(words,opt)` chuẩn hóa level uppercase, pos/partOfSpeech và keyword lowercase; lọc AND giữa điều kiện; trả `[]` nếu không khớp.
- `Import.gs`: `toTopicSlug_()` chuyển `Wild Animals` thành `wild-animals`; `Set` loại trùng case-insensitive theo `(topicKey,word)`; output test `imported=4`, `skipped=2`.
- Looker Vocab: `CASE WHEN level IN ("A1","A2") THEN "Cơ bản" WHEN level IN ("B1","B2") THEN "Trung cấp" ELSE "Nâng cao" END`; **Số chủ đề = `COUNT_DISTINCT(topic)`**, không phải COUNT(topic).

### Những điều phải kiểm tra trước khi chép code từ PDF

- PDF có một số dấu nháy cong `’` và backtick hiển thị bất thường sau khi trích xuất; **không đảm bảo copy từ PDF dán vào Apps Script là chạy ngay**. Khi làm đề phải đối chiếu mã nguồn hiển thị đúng cú pháp.
- Các đề được thiết kế để chạy trên **bản sao / môi trường test**, không cần đụng cấu hình nhóm thật nếu có bài test độc lập.

## 7. Đồ án Vocab App theo `HD CNLTHD.docx` (17 trang)

### Nguồn/tên cần tìm

- Google Sheets **Dictionary**: `https://docs.google.com/spreadsheets/d/1imfnK-GrAJ5aaO2aEjPQf9fes-T4W1adlIwVValk_Mc/edit?gid=1110444184#gid=1110444184`.
- Looker Studio demo nhóm: `https://datastudio.google.com/reporting/e0941398-45c9-462c-a695-5b42cb524110`.
- Apps Script demo nhóm: `https://script.google.com/u/0/home/projects/1Bo8aAxy665NWM8aurpKAdRArbU8gb02V3Qn63rD3huSMCSFP0NuZ84Hn/edit`.
- AppSheet demo nhóm: `https://www.appsheet.com/template/AppDef?appName=VocabAdmin-343041352&appId=d55c5108-84cb-4b1e-a10c-a1eff2285b79&quickStart=False#UX.Views.Animal`.
- Project Firebase nhóm được nhắc: `vocab-demo`. **Khác với** project Firebase cá nhân `demo1-498b8`. Quyền truy cập các URL **chưa được xác nhận** trong cuộc trò chuyện.

### Cách hệ thống hoạt động (theo hai tài liệu nhóm)

1. Dữ liệu từ vựng gốc trong Google Sheets **Dictionary** (nhiều tab).
2. AppSheet **Vocab Admin** có thể sửa/thêm từ tại các bảng; thay đổi ghi về Sheets. Trên bản demo tài liệu ghi **Animal** và **Communication** đang có dữ liệu dùng được; các tab khác nhiều tab trống/lỗi.
3. Apps Script xử lý/nhập từ theo `topic`, tổ chức thành dữ liệu trong Cloud Firestore. `Import.gs` thuộc luồng import, `Filter.gs` thuộc lọc từ, `Auth.gs` thuộc xác thực/ủy quyền, `Data.gs` đọc dữ liệu.
4. Firestore lưu theo nhánh **`flashcard/{sheetName}/words/{topicKey}`** và dữ liệu phục vụ Web App; có thể xem `flashcard` → `Animal` → `words`.
5. Web App cho người học đăng nhập, chọn topic, lọc **Level** và **Part of Speech**, xuất Excel danh sách đang hiển thị.
6. Looker Studio đọc nguồn thống kê từ Sheets/`DashboardData`, hiển thị KPI và biểu đồ.

**Quan sát/hạn chế được tài liệu Word ghi nhận:**

- File hướng dẫn cho biết chức năng Google Sign-In của **Vocab Demo nhóm** đang vướng quyền và không hoạt động trong bản demo được mô tả. Điều này **không phải** trạng thái của Firebase project cá nhân `demo1`.
- Theo tài liệu, nút **Làm mới dữ liệu** dùng để cập nhật dữ liệu hiển thị; không suy ra mọi thay đổi trong Sheets/AppSheet đều đồng bộ tức thì với mọi thành phần nếu chưa kiểm thử.
- File hướng dẫn khuyên **tạo bản sao Dictionary trên Drive cá nhân** để thao tác, không làm hỏng nguồn nhóm.
- Trên Apps Script có menu do `onOpen()` tạo, có lệnh **Firestore → Import sheet lên Firestore**; **không chạy lại trên dự án chung** nếu không có sự đồng ý nhóm, vì có thể ghi đè/nhân dữ liệu.
- Các biến cấu hình trong Script Properties gồm ID Sheet và Firebase service account. **Không tạo/chia sẻ/private key** khi chỉ ôn vấn đáp; không lưu credentials vào README công khai.
- Tài liệu Word có thông tin đăng nhập demo. **Không sao chép mật khẩu vào bản bàn giao** vì là thông tin đăng nhập; tra tại nguồn qua kênh nhóm khi thật sự cần, đề nghị thay nếu đã bị phát tán.

### Câu hỏi dễ bị thầy hỏi

- AppSheet khác Google Sheets thế nào? AppSheet là UI quản trị; Sheets giữ dữ liệu gốc.
- Vì sao Apps Script nằm giữa Sheets và Firestore? Vì cần xử lý, biến đổi/gom dữ liệu theo chủ đề trước khi ghi vào Firestore.
- Firestore khác Realtime Database thế nào? Firestore tổ chức collection/documents; Realtime Database dạng cây JSON.
- `Filter.gs` xử lý gì? Lọc level, từ loại, keyword, có chuẩn hóa hoa/thường.
- `Import.gs` xử lý gì? Đọc Sheets, gom theo topic, tránh bản ghi rỗng/trùng, chuẩn hóa khóa topic, đẩy dữ liệu lên Firestore (test PDF đề 11 chỉ in log, **không ghi Firestore thật**).
- Looker Studio có phải database không? Không, là công cụ báo cáo và trực quan hóa nguồn dữ liệu.
- Công nghệ nào đã hoàn thiện ở mức nào? Trình bày đúng giới hạn thực nghiệm; đặc biệt Google Sign-In trên demo nhóm có hạn chế.

## 8. Lịch sử lỗi quan trọng và cách tiếp tục kiểm tra

| Ngữ cảnh      | Lỗi/triệu chứng                                                                       | Hướng xử lý đã xác định                                                                      |
| ------------- | ------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Firebase Ch4  | `getDatabase is not defined` / import npm khi chạy Live Server thuần (bản upload gốc) | Đã hướng dẫn đổi sang import CDN đầy đủ                                                      |
| Firebase Ch4  | `Database lives in a different region`                                                | Sửa `databaseURL` sang `...asia-southeast1.firebasedatabase.app`                             |
| Firebase Ch4  | `favicon.ico 404`                                                                     | Không ảnh hưởng đến ghi Database                                                             |
| Firebase Ch4  | `unload is not allowed in this document`                                              | Cảnh báo trình duyệt, Console vẫn ghi thành công                                             |
| Firebase Ch5  | `auth/unauthorized-domain`, domain `127.0.0.1`                                        | Authentication → Settings → Authorized domains → thêm `127.0.0.1`                            |
| Firebase Ch6  | `permission-denied` (nếu xuất hiện)                                                   | Xác minh Firestore Rules đã Publish, người dùng đăng nhập, `uid` khớp và truy vấn có lọc UID |
| Firebase Đề 9 | Cập nhật `done` bị từ chối nếu giữ Rules chỉ cho sửa `text`                           | Sửa **Rules** cho phép chủ sở hữu sửa `done` trước khi test                                  |
| Looker Ch5    | Tháng ở biểu đồ đường không theo thứ tự                                               | Dimension `ngay_nhap` Year Month; Sort theo thời gian tăng dần                               |
| Looker Ch6    | Giá trị KPI sai hoặc tràn                                                             | Kiểm tra SUM, kiểu số, bộ lọc, số thu gọn, so sánh Sheets                                    |

**Không coi `đã hướng dẫn sửa` = `đã xác nhận sửa thành công`.**

---

## 9. PHỤ LỤC – TOÀN BỘ CODE FIREBASE ĐÃ CÓ TRONG CUỘC TRÒ CHUYỆN

Các đoạn dưới đây được lưu theo từng giai đoạn, **giữ nguyên từng nội dung đã upload hoặc đã được trợ lý gửi**, không hợp nhất/sửa ngầm. Đặt trong các thư mục riêng khi dùng VS Code để tránh vô tình ghi đè lên bài cũ.

**Ghi chú về tình trạng:**

- `Firebase_Chuong4_BanGoc_*`: đúng byte từ các file đã upload; `main.js` **có lỗi import/thiếu hàm**, không nên chạy nguyên trạng.
- `Firebase_Chuong4_BanDaSua/main.js`: bản mẫu trợ lý gửi; biến `databaseURL` còn **placeholder** `DAN_DATABASE_URL_CUA_M_VAO_DAY` như tin nhắn gốc. **Người dùng đã tự sửa URL đúng khi chạy thực tế**, nhưng không cung cấp file `main.js` đã lưu sau sửa.
- `Firebase_Chuong5_Auth`: code đã hướng dẫn, chưa có bằng chứng sau sửa `unauthorized-domain`.
- `Firebase_Chuong6_Tasks`: code đã hướng dẫn, chưa có bằng chứng chạy thành công.
- **Không xác nhận SDK CDN 12.19.0/13.2.0 còn phù hợp cho môi trường mới:** đây là phiên bản **giữ nguyên theo đoạn đã gửi**, cần kiểm tra thực tế nếu có lỗi import.

### 9.1. CHƯƠNG 4 – index.html BẢN GỐC NGƯỜI DÙNG UPLOAD

**File:** `Firebase_Chuong4_BanGoc_index.html`

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Demo Firebase</title>
    <script type="module" src="main.js"></script>
  </head>

  <body style="font-family: sans-serif; text-align: center; margin-top: 50px">
    <h1>🔥 Kết nối Firebase Realtime Database</h1>

    <button id="addUser" style="padding: 10px 20px; font-size: 16px">
      Thêm user
    </button>

    <p
      id="status"
      style="margin-top: 20px; font-weight: bold; color: green"
    ></p>
  </body>
</html>
```

### 9.2. CHƯƠNG 4 – main.js BẢN GỐC NGƯỜI DÙNG UPLOAD

**File:** `Firebase_Chuong4_BanGoc_main.js`

```javascript
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyAqP0QXWF8wea7U9uXtWKDFonrEaRSZc_c",
  authDomain: "demo1-498b8.firebaseapp.com",
  projectId: "demo1-498b8",
  storageBucket: "demo1-498b8.firebasestorage.app",
  messagingSenderId: "331010125454",
  appId: "1:331010125454:web:920edf606847d8b10b63df",
  measurementId: "G-1ZMSX0CT8L",
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const database = getDatabase(app);

document.querySelector("#addUser").addEventListener("click", async () => {
  const status = document.querySelector("#status");

  try {
    const userRef = push(ref(database, "users"));

    await set(userRef, {
      name: "Người dùng mới",
      createdAt: Date.now(),
    });

    status.textContent = "Đã thêm user!";
  } catch (error) {
    console.error(error);
    status.textContent = `Không thêm được user: ${error.message}`;
  }
});
```

### 9.3. CHƯƠNG 4 – index.html GIAO DIỆN GIỮ NGUYÊN

**File:** `Firebase_Chuong4_BanDaSua/index.html`

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Demo Firebase</title>
    <script type="module" src="main.js"></script>
  </head>

  <body style="font-family: sans-serif; text-align: center; margin-top: 50px">
    <h1>🔥 Kết nối Firebase Realtime Database</h1>

    <button id="addUser" style="padding: 10px 20px; font-size: 16px">
      Thêm user
    </button>

    <p
      id="status"
      style="margin-top: 20px; font-weight: bold; color: green"
    ></p>
  </body>
</html>
```

### 9.4. CHƯƠNG 4 – main.js MẪU ĐÃ GỬI (CÒN PLACEHOLDER URL)

**File:** `Firebase_Chuong4_BanDaSua/main.js`

```javascript
import { initializeApp } from "https://www.gstatic.com/firebasejs/13.2.0/firebase-app.js";

import {
  getDatabase,
  ref,
  push,
  set,
} from "https://www.gstatic.com/firebasejs/13.2.0/firebase-database.js";

// Cấu hình Firebase của m
const firebaseConfig = {
  apiKey: "AIzaSyAqP0QXWF8wea7U9uXtWKDFonrEaRSZc_c",
  authDomain: "demo1-498b8.firebaseapp.com",
  databaseURL: "DAN_DATABASE_URL_CUA_M_VAO_DAY",
  projectId: "demo1-498b8",
  storageBucket: "demo1-498b8.firebasestorage.app",
  messagingSenderId: "331010125454",
  appId: "1:331010125454:web:920edf606847d8b10b63df",
  measurementId: "G-1ZMSX0CT8L",
};

// Khởi tạo Firebase
const app = initializeApp(firebaseConfig);

// Kết nối Realtime Database
const database = getDatabase(app);

// Xử lý nút Thêm user
document.querySelector("#addUser").addEventListener("click", async () => {
  const status = document.querySelector("#status");

  try {
    const userRef = push(ref(database, "users"));

    await set(userRef, {
      name: "Người dùng mới",
      createdAt: Date.now(),
    });

    status.style.color = "green";
    status.textContent = "Đã thêm user thành công!";
    console.log("Đã ghi dữ liệu lên Firebase.");
  } catch (error) {
    console.error(error);
    status.style.color = "red";
    status.textContent = `Lỗi: ${error.message}`;
  }
});
```

**URL được khẳng định đúng trong lượt gỡ lỗi sau đó (dán thay placeholder nếu tái dựng Chương 4):** `https://demo1-498b8-default-rtdb.asia-southeast1.firebasedatabase.app`

### 9.5. CHƯƠNG 5 – index.html Auth

**File:** `Firebase_Chuong5_Auth/index.html`

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase Authentication Demo</title>
    <script type="module" src="./main.js"></script>
  </head>
  <body style="font-family: Arial; text-align: center; margin-top: 50px;">
    <h1>🔥 Firebase Authentication Demo</h1>

    <button id="loginBtn">Đăng nhập Google</button>
    <button id="logoutBtn" hidden>Đăng xuất</button>

    <p id="userInfo">Chưa đăng nhập</p>

    <hr />

    <h3>Kiểm tra Realtime Database</h3>
    <button id="addUser" disabled>Thêm user</button>

    <p id="status" role="status"></p>
  </body>
</html>
```

### 9.6. CHƯƠNG 5 – main.js Auth + Realtime Database

**File:** `Firebase_Chuong5_Auth/main.js`

```javascript
import { initializeApp } from "https://www.gstatic.com/firebasejs/12.19.0/firebase-app.js";

import {
  getDatabase,
  ref,
  push,
  set,
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-database.js";

import {
  getAuth,
  GoogleAuthProvider,
  signInWithPopup,
  signOut,
  onAuthStateChanged,
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-auth.js";

// 1. Cấu hình Firebase
const firebaseConfig = {
  apiKey: "AIzaSyAqP0QXWF8wea7U9uXtWKDFonrEaRSZc_c",
  authDomain: "demo1-498b8.firebaseapp.com",
  databaseURL:
    "https://demo1-498b8-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "demo1-498b8",
  storageBucket: "demo1-498b8.firebasestorage.app",
  messagingSenderId: "331010125454",
  appId: "1:331010125454:web:920edf606847d8b10b63df",
  measurementId: "G-1ZMSX0CT8L",
};

// 2. Khởi tạo Firebase
const app = initializeApp(firebaseConfig);
const database = getDatabase(app);
const auth = getAuth(app);
const provider = new GoogleAuthProvider();

// 3. Lấy các phần tử HTML
const loginBtn = document.getElementById("loginBtn");
const logoutBtn = document.getElementById("logoutBtn");
const userInfo = document.getElementById("userInfo");
const addUserBtn = document.getElementById("addUser");
const status = document.getElementById("status");

// Hàm thông báo
function showStatus(message, isError = false) {
  status.textContent = message;
  status.style.color = isError ? "red" : "green";
}

// 4. Xử lý đăng nhập Google
loginBtn.addEventListener("click", async () => {
  try {
    await signInWithPopup(auth, provider);
    showStatus("Đăng nhập Google thành công!");
  } catch (error) {
    console.error("Lỗi đăng nhập:", error);
    showStatus("Lỗi: " + error.message, true);
  }
});

// 5. Xử lý đăng xuất
logoutBtn.addEventListener("click", async () => {
  try {
    await signOut(auth);
    showStatus("Đã đăng xuất!");
  } catch (error) {
    console.error("Lỗi đăng xuất:", error);
    showStatus("Lỗi: " + error.message, true);
  }
});

// 6. Theo dõi trạng thái đăng nhập
onAuthStateChanged(auth, (user) => {
  if (user) {
    userInfo.textContent = `Xin chào ${user.displayName || "Người dùng"} - ${user.email}`;

    loginBtn.hidden = true;
    logoutBtn.hidden = false;
    addUserBtn.disabled = false;

    console.log("Đã đăng nhập:", user.uid);
  } else {
    userInfo.textContent = "Chưa đăng nhập";

    loginBtn.hidden = false;
    logoutBtn.hidden = true;
    addUserBtn.disabled = true;
  }
});

// 7. Giữ lại tính năng thêm user ở Chương 4
addUserBtn.addEventListener("click", async () => {
  if (!auth.currentUser) {
    showStatus("Vui lòng đăng nhập trước!", true);
    return;
  }

  try {
    const userRef = push(ref(database, "users"));

    await set(userRef, {
      name: "Người dùng mới",
      createdAt: Date.now(),
    });

    showStatus("Đã thêm user vào Realtime Database!");
    console.log("Đã ghi dữ liệu lên Firebase.");
  } catch (error) {
    console.error("Lỗi ghi dữ liệu:", error);
    showStatus("Lỗi: " + error.message, true);
  }
});
```

### 9.7. CHƯƠNG 6 – index.html Task Manager

**File:** `Firebase_Chuong6_Tasks/index.html`

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase - Quản lý công việc</title>
    <script type="module" src="./main.js"></script>
  </head>

  <body style="font-family: Arial; max-width: 650px; margin: 50px auto;">
    <h1>🔥 Firebase Task Manager</h1>

    <!-- Đăng nhập và đăng xuất -->
    <button id="loginBtn">Đăng nhập Google</button>
    <button id="logoutBtn" hidden>Đăng xuất</button>

    <p id="userInfo">Chưa đăng nhập</p>

    <hr />

    <!-- Quản lý công việc -->
    <div id="taskSection" hidden>
      <h2>Danh sách công việc của tôi</h2>

      <form id="taskForm">
        <input
          type="text"
          id="taskInput"
          placeholder="Nhập công việc mới"
          maxlength="500"
          required
        />
        <button type="submit">Thêm Task</button>
      </form>

      <ul id="taskList"></ul>
    </div>

    <p id="status" role="status"></p>
  </body>
</html>
```

### 9.8. CHƯƠNG 6 – main.js Task Manager (FULL)

**File:** `Firebase_Chuong6_Tasks/main.js`

```javascript
import { initializeApp } from "https://www.gstatic.com/firebasejs/12.19.0/firebase-app.js";

import {
  getAuth,
  GoogleAuthProvider,
  signInWithPopup,
  signOut,
  onAuthStateChanged,
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-auth.js";

import {
  getFirestore,
  collection,
  addDoc,
  query,
  where,
  onSnapshot,
  doc,
  updateDoc,
  deleteDoc,
  serverTimestamp,
} from "https://www.gstatic.com/firebasejs/12.19.0/firebase-firestore.js";

// 1. Cấu hình Firebase
const firebaseConfig = {
  apiKey: "AIzaSyAqP0QXWF8wea7U9uXtWKDFonrEaRSZc_c",
  authDomain: "demo1-498b8.firebaseapp.com",
  databaseURL:
    "https://demo1-498b8-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "demo1-498b8",
  storageBucket: "demo1-498b8.firebasestorage.app",
  messagingSenderId: "331010125454",
  appId: "1:331010125454:web:920edf606847d8b10b63df",
  measurementId: "G-1ZMSX0CT8L",
};

// 2. Khởi tạo Firebase
const app = initializeApp(firebaseConfig);
const auth = getAuth(app);
const db = getFirestore(app);
const provider = new GoogleAuthProvider();

// 3. Lấy các phần tử HTML
const loginBtn = document.getElementById("loginBtn");
const logoutBtn = document.getElementById("logoutBtn");
const userInfo = document.getElementById("userInfo");
const taskSection = document.getElementById("taskSection");
const taskForm = document.getElementById("taskForm");
const taskInput = document.getElementById("taskInput");
const taskList = document.getElementById("taskList");
const status = document.getElementById("status");

let stopTaskListener = null;

function showStatus(message, error = false) {
  status.textContent = message;
  status.style.color = error ? "red" : "green";
}

// 4. Đăng nhập Google
loginBtn.addEventListener("click", async () => {
  try {
    await signInWithPopup(auth, provider);
    showStatus("Đăng nhập thành công!");
  } catch (error) {
    console.error(error);
    showStatus(error.message, true);
  }
});

// 5. Đăng xuất
logoutBtn.addEventListener("click", async () => {
  try {
    await signOut(auth);
    showStatus("Đã đăng xuất!");
  } catch (error) {
    console.error(error);
    showStatus(error.message, true);
  }
});

// 6. Theo dõi trạng thái đăng nhập
onAuthStateChanged(auth, (user) => {
  // Ngừng theo dõi dữ liệu của tài khoản cũ
  if (stopTaskListener) {
    stopTaskListener();
    stopTaskListener = null;
  }

  taskList.replaceChildren();

  if (user) {
    userInfo.textContent = `Xin chào ${user.displayName || "Người dùng"} (${user.email})`;

    loginBtn.hidden = true;
    logoutBtn.hidden = false;
    taskSection.hidden = false;

    // Tải công việc của tài khoản hiện tại
    loadTasks(user.uid);
  } else {
    userInfo.textContent = "Chưa đăng nhập";

    loginBtn.hidden = false;
    logoutBtn.hidden = true;
    taskSection.hidden = true;
  }
});

// 7. Thêm công việc
taskForm.addEventListener("submit", async (event) => {
  event.preventDefault();

  const user = auth.currentUser;
  const text = taskInput.value.trim();

  if (!user || !text) return;

  try {
    await addDoc(collection(db, "tasks"), {
      text: text,
      uid: user.uid,
      name: user.displayName || "",
      createdAt: serverTimestamp(),
    });

    taskInput.value = "";
    showStatus("Đã thêm công việc!");
  } catch (error) {
    console.error(error);
    showStatus(error.message, true);
  }
});

// 8. Đọc danh sách công việc realtime
function loadTasks(uid) {
  const q = query(collection(db, "tasks"), where("uid", "==", uid));

  stopTaskListener = onSnapshot(
    q,
    (snapshot) => {
      taskList.replaceChildren();

      if (snapshot.empty) {
        const empty = document.createElement("li");
        empty.textContent = "Chưa có công việc nào.";
        taskList.appendChild(empty);
        return;
      }

      snapshot.forEach((taskDoc) => {
        const data = taskDoc.data();

        const li = document.createElement("li");
        li.style.marginBottom = "12px";

        const title = document.createElement("span");
        title.textContent = data.text + "  ";

        const editBtn = document.createElement("button");
        editBtn.textContent = "Sửa";

        const deleteBtn = document.createElement("button");
        deleteBtn.textContent = "Xóa";

        // 9. Sửa công việc
        editBtn.addEventListener("click", async () => {
          const newText = prompt("Nhập nội dung mới:", data.text);

          if (newText === null) return;

          const value = newText.trim();

          if (!value || value.length > 500) {
            showStatus("Nội dung phải từ 1 đến 500 ký tự.", true);
            return;
          }

          try {
            await updateDoc(doc(db, "tasks", taskDoc.id), {
              text: value,
            });

            showStatus("Đã sửa công việc!");
          } catch (error) {
            console.error(error);
            showStatus(error.message, true);
          }
        });

        // 10. Xóa công việc
        deleteBtn.addEventListener("click", async () => {
          if (!confirm("Bạn muốn xóa công việc này?")) {
            return;
          }

          try {
            await deleteDoc(doc(db, "tasks", taskDoc.id));
            showStatus("Đã xóa công việc!");
          } catch (error) {
            console.error(error);
            showStatus(error.message, true);
          }
        });

        li.append(title, editBtn, " ", deleteBtn);
        taskList.appendChild(li);
      });
    },
    (error) => {
      console.error("Lỗi tải tasks:", error);
      showStatus("Không tải được tasks: " + error.message, true);
    },
  );
}
```

### 9.9. CHƯƠNG 6 – Firestore Rules (FULL)

**File:** `Firebase_Chuong6_Tasks/firestore.rules`

```javascript
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {

    match /tasks/{taskId} {

      // Chỉ chủ sở hữu được tạo công việc
      allow create: if request.auth != null
        && request.resource.data.uid == request.auth.uid;

      // Chỉ chủ sở hữu được đọc hoặc xóa
      allow read, delete: if request.auth != null
        && resource.data.uid == request.auth.uid;

      // Chỉ chủ sở hữu được sửa nội dung công việc
      allow update: if request.auth != null
        && resource.data.uid == request.auth.uid
        && request.resource.data.uid == request.auth.uid
        && request.resource.data.diff(resource.data)
             .affectedKeys().hasOnly(['text'])
        && request.resource.data.text is string;
    }
  }
}
```

## 10. CHECKLIST THỰC HÀNH CÒN DANG DỞ

- [ ] Đề 5: tạo bản sao Bicycle Store / ứng dụng test riêng; bảo đảm 4 xe đúng mã và tồn ban đầu.
- [ ] Đề 5: sửa Condition Bot dùng BEFORE/AFTER và Valid If chống tồn âm; chạy **4 test**; chụp ảnh email/log.
- [ ] Đề 6: thêm `ThanhTien` vào Đơn Hàng, regenerate structure; xem lại `Mã KH` Ref; tạo 3 Virtual Columns; kiểm tra KH01/KH02/KH03.
- [ ] Đề 7: tạo bảng 4 dòng `Data_De7`; tạo `GiaTriTonKho`, `TrangThaiTon`, tỷ lệ theo **giá trị tiền**; chạy lọc `Sắp hết`.
- [ ] Đề 8: trên **project test cá nhân**, chỉnh/kiểm thử Rules 8 trường hợp; không thay rules của nhóm nếu chưa được cho phép.
- [ ] Đề 9: làm task `done`/lọc realtime; **chỉnh Rules tương thích**; kiểm tra hai tài khoản.
- [ ] Đề 1–4: tạo Apps Script test độc lập, Form 6 câu (PDF trang 5–7), chạy bốn đề theo log mong đợi.
- [ ] Đề 10, 11: chạy test mã `Filter.gs`, `Import.gs` bằng mảng mẫu, **không ghi đè dữ liệu thật**.
- [ ] Đề 12: tạo DashboardData test 8 dòng; KPI 8/4 và lọc Animal 5/2.
- [ ] Looker Ch5: sửa biểu đồ tháng theo thứ tự thời gian, kiểm tra 3 KPI so với nguồn.
- [ ] Looker Ch6: tạo 2 trường, chụp ảnh KPI thực tế; làm rõ tỷ lệ số lượng/giá trị.
- [ ] Firebase Ch5: xác nhận đăng nhập Google thành công với ảnh (không chỉ “đã thêm domain”).
- [ ] Firebase Ch6: tạo Firestore, Publish Rules, kiểm thử CRUD và quyền A/B; chụp ảnh.
- [ ] Vocab Demo: mở link nhóm bằng tài khoản có quyền; thao tác trên **bản sao** Dictionary; hiểu luồng import, không tạo private key hoặc chạy import lại một cách tùy tiện.

---

## 11. ĐANG DỪNG Ở ĐÂU (PHẢI GIỮ NGUYÊN KHI MỞ CHAT MỚI)

**Điểm dừng chính xác:** Sau khi gửi hai tài liệu `huong-dan-chi-tiet.pdf` và `HD CNLTHD.docx`, người dùng nhờ “tiếp tục ôn 2 file này”. Trợ lý đã **đọc và tóm tắt cả hai**, lập bảng 12 đề, giải thích công thức của Đề 5 (Bot băng qua ngưỡng, chống tồn kho âm) và Đề 6 (Ref + Virtual Column), nêu kiến trúc Vocab App, và **đề nghị bắt đầu thực hành Đề 5**. **Chưa có ảnh hay phản hồi chứng minh người dùng đã thao tác Đề 5**, cũng chưa có kết quả Đề 6–12.

**Bước tiếp theo khuyến nghị:** mở bản sao ứng dụng **Bicycle Store / Xe Đạp** trong AppSheet → Automation → Bot cảnh báo tồn kho → thay Condition thành `AND([_THISROW_BEFORE].[Số lượng tồn] >= 5, [_THISROW_AFTER].[Số lượng tồn] < 5)` → thiết lập `Valid If` là `[_THIS] >= 0` → kiểm thử 4 xe của đề. Nếu m muốn ôn Apps Script hoặc đồ án trước thì đổi theo ưu tiên.

**Nguyên tắc tiếp tục:** hướng dẫn từng bước, không đoán người dùng đã làm xong; nếu phát sinh lỗi hãy dựa vào ảnh/chính file mã mới nhất. Không nhầm Firebase cá nhân `demo1-498b8` với Firebase Vocab của nhóm `vocab-demo`.
