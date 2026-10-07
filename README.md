## 1. Phân tích lỗi và cách sửa

- Lỗi: Truy cập thuộc tính động bằng Dot Notation thay vì Bracket Notation
  - Đoạn mã sai: const basePrice = bookingReservation.priceKey;
  - Nguyên nhân: Dùng dấu chấm (.priceKey) khiến JS tìm thuộc tính có tên cố định là "priceKey", mà đối tượng không có thuộc tính này nên trả về undefined. Khi lấy undefined tính toán tiếp làm phụ thu và tổng tiền đều bị NaN
  - Cách sửa: Đổi thành bookingReservation[priceKey] để JS lấy giá trị của biến priceKey làm tên thuộc tính cần tìm

## 2. Bảng Test Cases đối chứng

| STT | Trường hợp kiểm thử | Dữ liệu đầu vào | Kết quả sai thực tế | Kết quả đúng mong đợi |
| --- | --- | --- | --- | --- |
| TC01 | Lấy giá phòng qua biến động priceKey | priceKey = "roomPrice", roomPrice = 1500000 | basePrice: undefined | basePrice: 1500000 |
| TC02 | Tính phụ thu và tổng tiền thanh toán | checkInHour = 9, basePrice = 1500000 | Phụ thu: NaN, Tổng tiền: NaN | Phụ thu nhận phòng sớm: 450000, Tổng số tiền thanh toán: 1950000 |
