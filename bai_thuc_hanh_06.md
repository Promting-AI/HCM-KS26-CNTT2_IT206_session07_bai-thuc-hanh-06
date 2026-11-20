# Yêu cầu đầu ra:

## Promt: File 1: Danh sách sinh viên và mã sinh viên.

```markdown
**Context:** Tôi là trợ lý đào tạo tại Trung tâm CNTT. Lớp có 30 sinh viên học Java cơ bản. Dưới đây là File 1: danh sách sinh viên và mã sinh viên.

**Request:** Hãy đọc File 1 và chuyển thành một bảng có cấu trúc.

**Explanation:** Mã sinh viên là khóa định danh chính. Sau này tôi sẽ dùng mã để ghép với các file khác, nên mã phải chính xác. Có thể có sinh viên trùng tên hoặc dòng bị lặp.

**Action:**
1. Trích xuất 2 cột: Mã SV, Họ tên.
2. Giữ nguyên mã và tên như trong file, không sửa, không đoán.
3. Nếu thiếu mã hoặc thiếu tên, ghi "Thiếu dữ liệu".
4. Sau bảng, liệt kê riêng: dòng trùng mã SV, các họ tên trùng nhau (kèm mã SV), và tổng số dòng đọc được.

**Tone:** Ngắn gọn, chính xác, trung lập.

**Extras:** Chỉ trả về bảng markdown và danh sách bất thường. Không giải thích thêm. Không tự thêm sinh viên.


```

## Promt: File 2: Kết quả điểm chuyên cần và điểm bài tập.

```markdown
**Context:** Tôi là trợ lý đào tạo tại Trung tâm CNTT. Lớp 30 sinh viên học Java cơ bản. Dưới đây là File 2: điểm chuyên cần và điểm bài tập.

**Request:** Hãy đọc File 2 và chuyển thành một bảng có cấu trúc.

**Explanation:** Điểm mỗi đầu điểm theo thang 0–10. Dữ liệu này sẽ được ghép với file khác bằng Mã SV, nên không được dùng họ tên để nhận diện.

**Action:**
1. Trích xuất các cột: Mã SV, Họ tên, Chuyên cần, Bài tập.
2. Nếu có nhiều cột điểm bài tập, giữ nguyên từng cột như trong file, chưa tính trung bình.
3. Ô trống hoặc không có điểm thì ghi "Thiếu dữ liệu". Tuyệt đối không tự điền điểm.
4. Sau bảng, liệt kê riêng: sinh viên thiếu điểm (nêu rõ thiếu cột nào), dòng trùng mã SV, và điểm ngoài khoảng 0–10.

**Tone:** Ngắn gọn, chính xác, trung lập.

**Extras:** Chỉ trả về bảng markdown và danh sách bất thường. Không sửa điểm. Không suy đoán nguyên nhân điểm thấp.

```

## Promt: File 3: Kết quả kiểm tra giữa kỳ.

```markdown
**Context:** Tôi là trợ lý đào tạo tại Trung tâm CNTT. Lớp 30 sinh viên học Java cơ bản. Dưới đây là File 3: kết quả kiểm tra giữa kỳ.

**Request:** Hãy đọc File 3 và chuyển thành một bảng có cấu trúc.

**Explanation:** Điểm giữa kỳ theo thang 0–10. Cấu trúc file này có thể khác các file còn lại, nên chỉ lấy đúng thông tin cần thiết.

**Action:**
1. Trích xuất các cột: Mã SV, Họ tên, Giữa kỳ.
2. Ô trống hoặc không có điểm thì ghi "Thiếu dữ liệu". Không tự điền.
3. Sau bảng, liệt kê riêng: sinh viên thiếu điểm, dòng trùng mã SV (nếu trùng mà điểm khác nhau, ghi rõ cả hai giá trị, không tự chọn), và điểm ngoài khoảng 0–10.

**Tone:** Ngắn gọn, chính xác, trung lập.

**Extras:** Chỉ trả về bảng markdown và danh sách bất thường. Không suy đoán nguyên nhân điểm thấp.

```

## Promt: File 4: Kết quả thi cuối kỳ và nhận xét của giảng viên.

```markdown
**Context:** Tôi là trợ lý đào tạo tại Trung tâm CNTT. Lớp 30 sinh viên học Java cơ bản. Dưới đây là File 4: kết quả thi cuối kỳ và nhận xét của giảng viên.

**Request:** Hãy đọc File 4 và chuyển thành một bảng có cấu trúc.

**Explanation:** Điểm cuối kỳ theo thang 0–10. Nhận xét của giảng viên là thông tin tham khảo, không dùng để tính điểm.

**Action:**
1. Trích xuất các cột: Mã SV, Họ tên, Cuối kỳ, Nhận xét GV.
2. Chép nhận xét đúng nguyên văn, không viết lại, không diễn giải.
3. Ô trống hoặc không có điểm thì ghi "Thiếu dữ liệu". Không tự điền.
4. Sau bảng, liệt kê riêng: sinh viên thiếu điểm, dòng trùng mã SV (nếu trùng mà điểm khác nhau, ghi rõ cả hai giá trị, không tự chọn), và điểm ngoài khoảng 0–10.

**Tone:** Ngắn gọn, chính xác, trung lập.

**Extras:** Chỉ trả về bảng markdown và danh sách bất thường. Không suy đoán nguyên nhân sinh viên có điểm thấp, kể cả khi nhận xét của giảng viên có nhắc đến.

```
## Promt: Đối chiếu dữ liệu giữa 4 file.
 
```markdown
**Context:** Tôi là trợ lý đào tạo tại Trung tâm CNTT. Lớp 30 sinh viên học Java cơ bản. Tôi đã đọc riêng 4 file và có 4 bảng: Bảng 1 (Mã SV, Họ tên), Bảng 2 (Chuyên cần, Bài tập), Bảng 3 (Giữa kỳ), Bảng 4 (Cuối kỳ, Nhận xét GV). Dưới đây là 4 bảng đó.
 
**Request:** Hãy đối chiếu 4 bảng, ghép thành một bảng tổng hợp duy nhất cho 30 sinh viên, tính điểm tổng kết, phân loại Đạt / Chưa đạt và liệt kê các trường hợp bất thường.
 
**Explanation:**
- Mã SV là khóa định danh chính. Có sinh viên trùng tên, nên tuyệt đối không ghép dữ liệu chỉ dựa trên họ tên.
- Thang điểm mỗi đầu điểm là 0–10.
- Công thức: Tổng kết = 10% Chuyên cần + 20% Bài tập + 30% Giữa kỳ + 40% Cuối kỳ.
- Sinh viên đạt học phần khi Tổng kết từ 5,0 trở lên.
- Nếu thiếu dữ liệu, phải ghi "Thiếu dữ liệu", không được tự điền điểm.
- Không được suy đoán nguyên nhân sinh viên có điểm thấp hoặc thiếu điểm.
 
**Action:**
1. Ghép 4 bảng theo Mã SV. Mỗi Mã SV chỉ có 1 dòng trong bảng tổng hợp.
2. Nếu một Mã SV không có trong bảng nào đó, ghi "Thiếu dữ liệu" ở các cột điểm tương ứng. Không tự điền điểm.
3. Kiểm tra và liệt kê bất thường, nêu rõ Mã SV, file liên quan và loại lỗi:
   - Mã SV trùng trong cùng một file (nếu điểm khác nhau thì ghi cả hai giá trị, không tự chọn dòng nào).
   - Mã SV có ở file này nhưng không có ở file khác.
   - Cùng Mã SV nhưng họ tên khác nhau giữa các file.
   - Các sinh viên trùng họ tên (kèm Mã SV để phân biệt).
   - Sinh viên thiếu điểm (nêu rõ thiếu đầu điểm nào).
   - Điểm ngoài khoảng 0–10.
   - Tổng số sinh viên khác 30.
4. Tính Tổng kết cho sinh viên có đủ 4 đầu điểm hợp lệ. Làm tròn 1 chữ số thập phân (đề xuất), rồi so với 5,0. Ghi Kết quả là "Đạt" hoặc "Chưa đạt".
5. Sinh viên thiếu bất kỳ đầu điểm nào, hoặc có dữ liệu trùng chưa rõ: Tổng kết ghi "Thiếu dữ liệu", Kết quả ghi "Chưa xác định" (đề xuất), không tự tính.
 
**Tone:** Ngắn gọn, chính xác, trung lập.
 
**Extras:**
- Đầu ra gồm 3 phần theo thứ tự: (1) Bảng tổng hợp gồm các cột Mã SV, Họ tên, Chuyên cần, Bài tập, Giữa kỳ, Cuối kỳ, Tổng kết, Kết quả; (2) Danh sách bất thường dạng bảng; (3) Thống kê: số sinh viên Đạt, Chưa đạt, Chưa xác định và tỷ lệ phần trăm.
- Không dùng Nhận xét GV để sửa điểm hoặc để kết luận.
- Không tự thêm hoặc bớt sinh viên.
```

## 1/ Bảng kết quả tổng hợp 30 sinh viên
 
| Mã SV | Họ tên | Chuyên cần | Bài tập | Giữa kỳ | Cuối kỳ | Tổng kết | Kết quả |
|---|---|---|---|---|---|---|---|
| SV001 | Nguyễn Hoàng Anh | 8,5 | 6,5 | 7,5 | 9,0 | 8,0 | Đạt |
| SV002 | Trần Thị Bình | 10,0 | 8,0 | 7,0 | 6,5 | 7,3 | Đạt |
| SV003 | Lê Hoàng Cường | 8,0 | 6,0 | 4,5 | 4,0 / 6,0 (trùng) | Thiếu dữ liệu | Chưa xác định |
| SV004 | Phạm Thị Dung | 6,5 | 4,5 | 4,5 | 2,0 | 3,7 | Chưa đạt |
| SV005 | Nguyễn Văn An | 8,5 | 7,5 | 7,5 | 6,5 | 7,2 | Đạt |
| SV006 | Võ Minh Đức | 9,5 | 8,5 | 8,5 | 3,5 | 6,6 | Đạt |
| SV007 | Đặng Thu Hà | 7,5 | 9,0 | Thiếu dữ liệu | 7,5 | Thiếu dữ liệu | Chưa xác định |
| SV008 | Bùi Quang Huy | 8,0 | 9,0 | 7,0 | 7,0 | 7,5 | Đạt |
| SV009 | Hoàng Thị Lan | Thiếu dữ liệu | Thiếu dữ liệu | 4,5 | 6,0 | Thiếu dữ liệu | Chưa xác định |
| SV010 | Ngô Thanh Hải | 6,0 | 3,5 | 4,0 | 3,0 | 3,7 | Chưa đạt |
| SV011 | Trần Thị Hoa | 9,0 | 7,0 | 8,0 | 6,5 | 7,3 | Đạt |
| SV012 | Đỗ Văn Khánh | 7,5 | 8,0 | 7,5 | 7,0 | 7,4 | Đạt |
| SV013 | Lý Thị Kim | 5,0 | 5,0 | 5,0 | 4,9 | 5,0 | Đạt |
| SV014 | Lê Minh Quân | 7,5 | 9,0 | 7,5 | 7,0 | 7,6 | Đạt |
| SV015 | Phan Thị Mai | 8,0 | 7,5 | 7,5 | 3,5 | 6,0 | Đạt |
| SV016 | Dương Văn Nam | 8,0 | 6,0 | 7,5 | 7,0 | 7,1 | Đạt |
| SV017 | Vũ Thị Ngọc | 5,5 | 5,0 | 5,0 | 5,5 | 5,3 | Đạt |
| SV018 | Nguyễn Văn An | 7,0 | 9,5 | 7,0 | 4,0 | 6,3 | Đạt |
| SV019 | Trịnh Quốc Phong | 10,0 | 6,5 | 6,0 | 8,0 | 7,3 | Đạt |
| SV020 | Đinh Thị Phương | 8,5 | 7,5 | 8,5 | 7,5 | 7,9 | Đạt |
| SV021 | Hồ Minh Quang | 6,0 | Thiếu dữ liệu | 5,0 | 5,0 | Thiếu dữ liệu | Chưa xác định |
| SV022 | Mai Thị Quỳnh | 4,0 | 4,5 | 3,5 | 3,5 | 3,8 | Chưa đạt |
| SV023 | Cao Văn Sơn | 9,5 | 7,5 | 6,5 | 8,5 | 7,8 | Đạt |
| SV024 | Lương Thị Thảo | 9,0 | 8,0 | 11 (ngoài 0–10) | 8,0 | Thiếu dữ liệu | Chưa xác định |
| SV025 | Tạ Quốc Thắng | 8,5 | 7,5 | 6,0 | 5,5 | 6,4 | Đạt |
| SV026 | Trần Thị Hoa | 10,0 | 8,0 | 3,5 | 7,0 | 6,5 | Đạt |
| SV027 | Châu Minh Tuấn | 8,0 | 6,5 | 6,5 | 7,0 | 6,9 | Đạt |
| SV028 | Lâm Thị Uyên | 9,5 | 7,0 | 6,5 | Thiếu dữ liệu | Thiếu dữ liệu | Chưa xác định |
| SV029 | Huỳnh Văn Vinh | 3,0 | 3,0 | 2,0 | 4,5 | 3,3 | Chưa đạt |
| SV030 | Phùng Thị Yến | 8,0 | 6,0 | 5,5 | 5,0 | 5,7 | Đạt |
 
**Quy tắc áp dụng:** Tổng kết = 10% CC + 20% BT + 30% GK + 40% CK. Làm tròn 1 chữ số thập phân (đề xuất). Đạt khi Tổng kết ≥ 5,0. Thiếu điểm, điểm ngoài 0–10 hoặc trùng Mã SV khác điểm: Tổng kết ghi "Thiếu dữ liệu", Kết quả ghi "Chưa xác định" (đề xuất).
 
## 2/ Báo cáo thống kê tỷ lệ đạt và chưa đạt
 
| Kết quả | Số SV | Tỷ lệ trên 30 SV | Tỷ lệ trên 24 SV có điểm tổng kết |
|---|---|---|---|
| Đạt | 20 | 66,7% | 83,3% |
| Chưa đạt | 4 | 13,3% | 16,7% |
| Chưa xác định | 6 | 20,0% | – |
| **Tổng** | **30** | **100,0%** | **100,0%** |
 
**Ghi chú:** SV013 có Tổng kết chưa làm tròn là 4,96, làm tròn thành 5,0 nên xếp Đạt. Nếu không làm tròn, SV013 là Chưa đạt (khi đó: Đạt 19, Chưa đạt 5). Cần giảng viên xác nhận quy tắc làm tròn (D2b).
 
## 3/ Danh sách các trường hợp bất thường
 
| STT | Mã SV | File | Loại bất thường | Cách xử lý |
|---|---|---|---|---|
| 1 | SV005, SV018 | File 1 | Trùng họ tên "Nguyễn Văn An" | Phân biệt bằng Mã SV, không ghép theo tên |
| 2 | SV011, SV026 | File 1 | Trùng họ tên "Trần Thị Hoa" | Phân biệt bằng Mã SV, không ghép theo tên |
| 3 | SV009 | File 2 | Không có trong file | Chuyên cần, Bài tập: Thiếu dữ liệu |
| 4 | SV021 | File 2 | Ô Bài tập để trống | Bài tập: Thiếu dữ liệu |
| 5 | SV007 | File 3 | Ô Giữa kỳ để trống | Giữa kỳ: Thiếu dữ liệu |
| 6 | SV016 | File 3 | Dòng trùng, cùng điểm 7,5 | Gộp thành 1 dòng, tính bình thường |
| 7 | SV024 | File 3 | Điểm giữa kỳ 11, ngoài khoảng 0–10 | Không dùng; Tổng kết: Thiếu dữ liệu |
| 8 | SV003 | File 4 | Trùng Mã SV, điểm cuối kỳ khác nhau (4,0 và 6,0) | Không tự chọn; Tổng kết: Thiếu dữ liệu |
| 9 | SV028 | File 4 | Ô Cuối kỳ để trống | Cuối kỳ: Thiếu dữ liệu |
| 10 | SV014 | File 1, 4 | Họ tên khác nhau: "Lê Minh Quân" (File 1, 2, 3) và "Lê Minh Quang" (File 4) | Ghép theo Mã SV, giữ tên File 1 |
 
**Tổng:** 10 mục bất thường. 6 sinh viên chưa xác định kết quả: SV003, SV007, SV009, SV021, SV024, SV028. Số sinh viên đủ 30, không có Mã SV lạ ngoài File 1.
 
## 4/ Báo cáo nhận xét tình hình học tập (khoảng 500 từ)
 
Lớp có 30 sinh viên học phần Java cơ bản. Trong đó, 24 sinh viên có đủ 4 đầu điểm hợp lệ nên được tính điểm tổng kết. 6 sinh viên chưa thể tính điểm do thiếu điểm, có điểm ngoài thang 0–10 hoặc có dữ liệu trùng nhưng khác điểm. Các nhận xét dưới đây chỉ mô tả số liệu, không giải thích nguyên nhân.
 
Về kết quả học phần, 20 sinh viên đạt (66,7% cả lớp), 4 sinh viên chưa đạt (13,3%) và 6 sinh viên chưa xác định (20,0%). Nếu chỉ tính 24 sinh viên đã có điểm tổng kết, tỷ lệ đạt là 83,3% và tỷ lệ chưa đạt là 16,7%. Có một trường hợp đạt sát ngưỡng: SV013 có điểm tổng kết chưa làm tròn là 4,96, được làm tròn thành 5,0 theo quy tắc làm tròn một chữ số thập phân (đề xuất). Nếu không làm tròn, sinh viên này thuộc nhóm chưa đạt, vì vậy quy tắc làm tròn cần được giảng viên xác nhận.
 
Về điểm tổng kết, trung bình của 24 sinh viên là 6,32. Điểm cao nhất là 8,0 (SV001), điểm thấp nhất là 3,3 (SV029). Về phân bố, 4 sinh viên có điểm dưới 5,0; 6 sinh viên từ 5,0 đến dưới 6,5; 13 sinh viên từ 6,5 đến dưới 8,0; 1 sinh viên từ 8,0 trở lên. Phần lớn sinh viên tập trung ở khoảng từ 6,5 đến dưới 8,0.
 
Về từng đầu điểm, tính trên số sinh viên có điểm hợp lệ, chuyên cần có điểm trung bình cao nhất là 7,72 (29 sinh viên). Bài tập đạt trung bình 6,84 (28 sinh viên), giữa kỳ đạt 6,05 (28 sinh viên) và cuối kỳ đạt 5,92 (28 sinh viên). Như vậy, điểm trung bình giảm dần theo thứ tự chuyên cần, bài tập, giữa kỳ, cuối kỳ. Số sinh viên có điểm dưới 5,0 ở từng đầu điểm lần lượt là 2 (chuyên cần), 4 (bài tập), 7 (giữa kỳ) và 8 (cuối kỳ).
 
Một số sinh viên có chênh lệch lớn giữa các đầu điểm. SV006 có chuyên cần 9,5, bài tập 8,5, giữa kỳ 8,5 nhưng cuối kỳ 3,5. SV026 có giữa kỳ 3,5 trong khi các đầu điểm còn lại từ 7,0 đến 10,0. Báo cáo chỉ ghi nhận sự chênh lệch này, không đưa ra lý do.
 
Về chất lượng dữ liệu, có 10 mục bất thường được ghi nhận: 2 cặp sinh viên trùng họ tên, 1 sinh viên không có trong file chuyên cần và bài tập, 3 ô điểm để trống, 1 điểm ngoài khoảng 0–10, 1 Mã SV trùng với điểm khác nhau, 1 dòng trùng cùng điểm và 1 họ tên viết khác nhau giữa các file. Việc đối chiếu bằng Mã SV giúp tránh nhầm điểm giữa các sinh viên trùng tên.
 
Việc cần làm tiếp theo là giảng viên bổ sung hoặc xác nhận điểm cho 6 sinh viên chưa xác định (SV003, SV007, SV009, SV021, SV024, SV028). Sau khi có điểm, tỷ lệ đạt và chưa đạt sẽ được tính lại cho đủ 30 sinh viên.
