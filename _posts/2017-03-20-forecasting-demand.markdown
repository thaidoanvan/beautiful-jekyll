---
layout : post
title : "Forecasting Demand"
date : 2017-03-21 00:35:00 +0700
categories : SCM Fundamental
--- 

*Trong bài viết này, tôi sẽ giới thiệu về Forecast Demand và một số methods cơ bản dùng trong Forecast Demand dưới góc nhìn quản trị chuỗi cung ứng*
# Demand
Quản trị chuỗi cung ứng là tất cả những việc cần làm nhằm kết nối cung và cầu. Chính vì vậy, việc hiểu cũng như việc dự đoán cầu là một bước quan trọng  và cũng là bước đầu tiên trong việc thiết kế một chuỗi cung ứng.  Chúng ta dự đoán cầu nhằm phục vụ việc hoạch định nguồn lực, quản lý tồn kho hay lên kế hoạch vận tải, .... 
Về cầu, chúng ta cần phải trả lời 3 câu hỏi chính:
* Làm thế nào để tạo ra nhu cầu cho sản phẩm?
* Ước lượng nhu cầu sản phẩm?
* Cần làm gì để đáp ứng lượng cầu đó?


## Dự báo cầu
Có 3 levels:
* *Strategic* : Thường dự báo trong khoảng thời gian tính theo năm, nhằm mục đích lên kế hoạch kinh doanh, lên kế hoạch về nguồn lực, các chiến lược đầu tư
* *Tactical*: Dự báo trong khoảng thời gian tính theo quý, tháng, tuần, nhằm lên kế hoạch bán hàng, tồn kho hay hoạch định về nhân lực
* *Operational*: Dự báo trong khoảng thời gian tính theo ngày, giờ cho các hoạt động vận hành như kế hoạch vận tải, sản xuất...


## Các facts về forecasting:
* __Dự báo luôn luôn sai.__  
Vì Cầu là một biến ngẫu nhiên liên tục, việc dự đoán chính xác gía trị của cầu là bất khả thi. Khi dự báo cầu, chúng ta nên đưa ra một khoảng gía trị của cầu. Đồng thời đưa thêm sai số của dự báo. Sai số này được tính dựa trên các lần dự báo trong quá khứ.
* __Dự báo với một tập hợp lớn(dựa trên aggregate product, location, time, ...) thì càng chính xác hơn dự báo với từng item riêng lẻ.__  
Cụ thể, việc dự báo cầu của 1 sản phẩm của 1 thành phố sẽ có độ chính xác cao hơn việc dự đoán cầu đối với một cửa hàng cụ thể trong thành phố đó, dự báo cầu của đồ uống sẽ có accuracy cao hơn dự báo cầu đối với cà phê đá.
* __Time horizon càng lớn thì độ chính xác càng giảm.__  
Dự báo cầu của ngày mai sẽ có độ chính xác cao hơn việc dự báo cầu của sản phẩm đó tại thời điểm 3 tháng sau

## Các hướng tiếp cận đối với Forecasting
* Tiếp cận chủ quan  
Bao gồm các phương pháp như làm survey khách hàng, phỏng vấn nhóm, tham khảo ý kiến từ các chuyên gia (someones you think they know the demand)...
* Tiếp cận khách quan  
Gồm các phương pháp như xây dựng mô hình kinh tế lượng, time series, ...

## Chất lượng của dự báo
Việc ra quyết định đối với chất lượng của dự báo dựa trên việc tối thiểu hóa Total cost = Cost of Forecasting + Cost of Error in Forecasting.
![forecast-cost-vs-accuracy](/assets/images/forecast-accuracy-cost.png)
Chất lượng của dự báo được đánh gía đựa trên độ chính xác và phương sai của dự báo. Các thưóc đo của chất lượng có thể kể đến như: MSE, MAPE, RMSE,... thông thường ta sẽ sử dụng RMSE để đo lường chất lượng của dự báo. RMSE đưọc tính bằng công thức:  
$$ \mathbf{X}\_{n,p} = \mathbf{A}\_{n,k} \mathbf{B}\_{k,p} $$
$$ \mathsf{Data = PCs} \times \mathsf{Loadings} $$

