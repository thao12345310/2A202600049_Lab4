# Kết quả kiểm thử Lab 4 (TravelBuddy Agent)

Dưới đây là kết quả của 6 test case đã được tự động chạy và lấy kết quả từ console:

```text
======================================================================
TEST CASE 1: Tìm chuyến bay Hà Nội → Đà Nẵng (giá rẻ nhất)
======================================================================
[INPUT] Bạn: Cho tôi xem các chuyến bay từ Hà Nội đến Đà Nẵng

Gọi tool: search_flights ({'origin': 'Hà Nội', 'destination': 'Đà Nẵng'})
Trả lời trực tiếp
[OUTPUT] TravelBuddy: Dưới đây là các chuyến bay từ Hà Nội đến Đà Nẵng:

1. **VietJet Air**: 
   - Giờ bay: 08:30 → 09:50
   - Giá vé: 890.000đ (hạng economy)

2. **Bamboo Airways**: 
   - Giờ bay: 11:00 → 12:20
   - Giá vé: 1.200.000đ (hạng economy)

3. **Vietnam Airlines**: 
   - Giờ bay: 06:00 → 07:20
   - Giá vé: 1.450.000đ (hạng economy)

4. **Vietnam Airlines**: 
   - Giờ bay: 14:00 → 15:20
   - Giá vé: 2.800.000đ (hạng business)

Bạn có cần thêm thông tin gì khác không? Ví dụ như khách sạn ở Đà Nẵng hoặc ngân sách cho chuyến đi?


======================================================================
TEST CASE 2: Tìm khách sạn tại Phú Quốc (không giới hạn giá)
======================================================================
[INPUT] Bạn: Tôi muốn tìm khách sạn ở Phú Quốc

Trả lời trực tiếp
[OUTPUT] TravelBuddy: Bạn có thể cho mình biết thêm thông tin chi tiết không? Ví dụ như ngân sách tối đa mỗi đêm bạn dự định chi cho khách sạn, hoặc thời gian bạn dự định lưu trú ở Phú Quốc? Điều này sẽ giúp mình tìm kiếm khách sạn phù hợp nhất cho bạn!


======================================================================
TEST CASE 3: Lên kế hoạch chuyến đi Hà Nội → Hồ Chí Minh 3 ngày 2 đêm, ngân sách 5 triệu
======================================================================
[INPUT] Bạn: Tôi muốn đi từ Hà Nội vào Hồ Chí Minh, ở 2 đêm, ngân sách tổng khoảng 5 triệu VNĐ. Bạn tư vấn giúp tôi nhé!

Gọi tool: search_flights ({'origin': 'Hà Nội', 'destination': 'Hồ Chí Minh'})
Gọi tool: search_hotels ({'city': 'Hồ Chí Minh'})
Gọi tool: calculate_budget ({'total_budget': 5000000, 'expenses': 'vé máy bay: 950000, khách sạn: 360000'})
Trả lời trực tiếp
[OUTPUT] TravelBuddy: Chuyến bay:
- VietJet Air: 07:30 → 09:40, giá vé 950.000 VNĐ (hạng phổ thông)

Khách sạn:
- The Common Room: 180.000 VNĐ/đêm (ở 2 đêm tổng cộng 360.000 VNĐ, 2 sao, Quận 1)

Tổng chi phí ước tính:
- Vé máy bay: 950.000 VNĐ
- Khách sạn: 360.000 VNĐ
- **Tổng: 1.310.000 VNĐ**

Ngân sách còn lại của bạn là 3.690.000 VNĐ, bạn có thể xem xét việc tăng thêm tiêu chuẩn khách sạn hoặc lựa chọn thêm các hoạt động thú vị tại Hồ Chí Minh nhé!

Gợi ý thêm:
- Nếu bạn muốn ở khách sạn 3 sao, Cochin Zen Hotel có mức giá 550.000 VNĐ/đêm, tổng cộng 1.100.000 VNĐ cho 2 đêm.
- Bạn cũng có thể khám phá các món ăn ngon tại các quán ăn địa phương hoặc tham gia tour tham quan thành phố nếu muốn.


======================================================================
TEST CASE 4: Tìm khách sạn tại Đà Nẵng giá dưới 700,000đ/đêm
======================================================================
[INPUT] Bạn: Cho tôi xem khách sạn ở Đà Nẵng nhưng giá phải dưới 700000 đồng một đêm thôi nhé

Gọi tool: search_hotels ({'city': 'Đà Nẵng', 'max_price_per_night': 700000})
Trả lời trực tiếp
[OUTPUT] TravelBuddy: Dưới đây là một số khách sạn ở Đà Nẵng có giá dưới 700.000 đồng một đêm:

1. **Christina's Homestay** - 350.000đ/đêm | 2 sao | An Thượng
2. **Memory Hostel** - 250.000đ/đêm | 2 sao | Hải Châu
3. **Fivitel Danang** - 650.000đ/đêm | 3 sao | Sơn Trà

Nếu bạn cần thêm thông tin hoặc muốn đặt phòng, hãy cho mình biết nhé!


======================================================================
TEST CASE 5: Tư vấn chuyến đi HCM → Phú Quốc với ngân sách 3 triệu 2 ngày 1 đêm
======================================================================
[INPUT] Bạn: Mình muốn đi Phú Quốc từ Sài Gòn, 2 ngày 1 đêm, budget chỉ có 3 triệu thôi, tư vấn cho mình với!

Gọi tool: search_flights ({'origin': 'Sài Gòn', 'destination': 'Phú Quốc'})
Gọi tool: search_hotels ({'city': 'Phú Quốc'})
Trả lời trực tiếp
[OUTPUT] TravelBuddy: Chuyến bay:
Hiện tại không tìm thấy chuyến bay giữa Sài Gòn và Phú Quốc. Có thể bạn cần kiểm tra lại thời gian hoặc cách di chuyển khác như tàu cao tốc.

Khách sạn:
- 9Station Hostel: 200,000đ/đêm (2 sao, Dương Đông)
- Vinpearl Resort: 3,500,000đ/đêm (5 sao, Bãi Dài)
- Lahana Resort: 800,000đ/đêm (4 sao, Dương Đông)
- Sol by Meliá: 1,500,000đ/đêm (4 sao, Bãi Trường)

Tổng chi phí ước tính:
- Nếu bạn chọn 9Station Hostel, thì chi phí khách sạn cho 1 đêm là 200,000đ. Tuy nhiên, bạn cần phải tìm chuyến bay hoặc phương tiện di chuyển khác, vì hiện tại không có chuyến bay từ Sài Gòn đi Phú Quốc.

Gợi ý thêm:
- Bạn có thể xem xét việc đi tàu cao tốc từ Rạch Giá hoặc Hà Tiên đến Phú Quốc. 
- Nếu không, có thể xem xét lại thời điểm đi hoặc địa điểm du lịch khác phù hợp với ngân sách.


======================================================================
TEST CASE 6: Yêu cầu ngoài phạm vi du lịch – agent phải từ chối
======================================================================
[INPUT] Bạn: Bạn có thể giúp tôi viết code Python không?

Trả lời trực tiếp
[OUTPUT] TravelBuddy: Xin lỗi, mình không thể giúp bạn viết code Python. Nhưng nếu bạn cần tư vấn về du lịch, đặt phòng, vé máy bay hoặc bất kỳ thông tin nào liên quan đến chuyến đi, mình rất sẵn lòng hỗ trợ! Bạn có kế hoạch đi đâu không?
```
