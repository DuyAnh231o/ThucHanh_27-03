## PHẦN 1: MÔ HÌNH HÓA QUY TRÌNH (BUSINESS FLOW)
1.1. Use Case Diagram (Mô tả)
Actors
•	Admin 
•	Customer 
•	Warehouse Staff 
Use Cases chính
Admin
•	Quản lý sản phẩm 
•	Quản lý biến thể (màu sắc, kích thước) 
•	Cập nhật tồn kho 
Customer
•	Xem danh sách sản phẩm 
•	Xem chi tiết sản phẩm 
•	Chọn biến thể sản phẩm 
•	Thêm vào giỏ hàng 
•	Đặt hàng 
•	Thanh toán 
Warehouse Staff
•	Xem đơn hàng 
•	Cập nhật trạng thái kho 
•	Xác nhận xuất hàng 

1.2. Activity Diagram (Luồng đặt hàng)

## PHẦN 2: ĐẶC TẢ CHỨC NĂNG (FUNCTIONAL REQUIREMENTS)
User Stories (chuẩn format)
Nhóm Customer
1.	
Là một khách hàng, tôi muốn xem danh sách sản phẩm để lựa chọn sản phẩm phù hợp.
2.	
Là một khách hàng, tôi muốn xem chi tiết sản phẩm (giá, biến thể, tồn kho) để đưa ra quyết định mua hàng.
3.	
Là một khách hàng, tôi muốn chọn biến thể (màu sắc, kích thước) để mua đúng sản phẩm mong muốn.
4.	
Là một khách hàng, tôi muốn thêm sản phẩm vào giỏ hàng để chuẩn bị thanh toán.
5.	
Là một khách hàng, tôi muốn thanh toán qua VNPay hoặc MoMo để tiện lợi và nhanh chóng.
6.	
Là một khách hàng, tôi muốn biết trạng thái đơn hàng sau khi thanh toán để theo dõi đơn.

Nhóm Admin (PIM trọng tâm)
7.	
Là một Admin, tôi muốn tạo và cập nhật sản phẩm để quản lý danh mục bán hàng.
8.	
Là một Admin, tôi muốn quản lý biến thể sản phẩm (màu, size) để phục vụ nhiều lựa chọn cho khách hàng.
9.	
Là một Admin, tôi muốn cập nhật tồn kho theo thời gian thực để đảm bảo số lượng chính xác.

Nhóm Warehouse
10.	
Là nhân viên kho, tôi muốn xem đơn hàng để chuẩn bị đóng gói.
11.	
Là nhân viên kho, tôi muốn cập nhật trạng thái xuất kho để hệ thống theo dõi chính xác.

## PHẦN 3: ĐẶC TẢ DỮ LIỆU (DATA SCHEMA)
3.1. Partner (Khách hàng)
•	CustomerID 
•	Tên khách hàng 
•	Loại khách hàng (Guest / Member / B2B / B2C) 
•	Email 
•	Số điện thoại 
•	Địa chỉ giao hàng 
•	Mã số thuế (MST) (nếu là công ty) 

3.2. Product (Sản phẩm - PIM)
•	ProductID 
•	Tên sản phẩm 
•	SKU 
•	Barcode 
•	Giá bán 
•	Thuế VAT 
•	Mô tả 
•	Danh mục 
•	Trạng thái (Active / Inactive) 
Product Variant
•	VariantID 
•	ProductID 
•	Màu sắc 
•	Kích thước 
•	Giá riêng (nếu có) 
•	Số lượng tồn kho 

3.3. Order (Đơn hàng)
•	OrderID 
•	Số đơn hàng 
•	CustomerID 
•	Ngày đặt 
•	Tổng tiền 
•	Phương thức thanh toán 
•	Trạng thái: 
o	Draft 
o	Confirmed 
o	Cancelled 

3.4. Order Detail
•	OrderDetailID 
•	OrderID 
•	ProductID 
•	VariantID 
•	Số lượng 
•	Đơn giá