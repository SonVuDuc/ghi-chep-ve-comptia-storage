# Một số ghi chép về Networking CompTIA Storage+

# 2. Storage Device - Thiết bị lưu trữ 

Có 3 hình thức của lưu trữ:
 * **Disk drive**: ổ đĩa cơ học
 * **Solid-state drive**: ổ đĩa thể rắn  
 * **Tape drive**: ổ băng

Disk, solid-state và tape đều thuộc kiểu **persistent storage** hay **nonvolatile**, tức là dữ liệu không bị mất đi khi ta dừng cấp điện cho chúng.

## 2.1. The Mechanical Disk Drive - Ổ đĩa cơ học

### 2.1.1. The Anatomy of a Disk Drive - Cấu tạo ổ đĩa cơ học

Ổ đĩa cơ học bao gồm 4 thành phần chính:
 * Platter
 * Read/write heads
 * Actuator assembly
 * Spindle motor

![image](https://user-images.githubusercontent.com/32956424/117912186-3dedbc00-b309-11eb-9b1d-98a599c7d533.png)

#### Platter

Còn được gọi là đĩa từ, hình dạng giống đĩa DVD, cấu tạo bằng nhôm hoặc thuỷ tinh, bề mặt được phủ một lớp vật liệu từ tính. Đây là nơi mà dữ liệu được lưu trữ. 

Hầu hết ổ cứng cơ thường có nhiều lớp đĩa từ.

![image](https://user-images.githubusercontent.com/32956424/117912489-d6843c00-b309-11eb-951a-aa9f5896537e.png)

Các đĩa từ đồng trục và quay cùng tốc độ với nhau. Dữ liệu được đọc/ghi trên bề mặt đĩa (gồm mặt trên và mặt dưới), thông qua **Read/Write heads** 

##### Track

Trên bề mặt đĩa từ được chia thành nhiều vòng tròn đồng tâm, gọi là các track

Track trên ổ đĩa không hề cố định từ nhà sản xuất, chúng có thể bị thay đổi khi format.

##### Sector

Trên track chia thành những phần nhỏ gọi là sector. Sector là đơn vị nhỏ nhất được chia ra để chứa dữ liệu.

Số lượng sector trên mỗi track là khác nhau từ vùng rìa đến tâm đĩa. Sector nằm gần rìa của đĩa sẽ chứa nhiều dữ liệu hơn

##### Cluster

Là tập hợp các sector nằm liền kề nhau

##### Cylinder

Tập hợp các track có dùng bán kính ở các đĩa khác nhau được gọi là cylinder. Một ổ đĩa có nhiều cylinder do có nhiều track

![image](https://user-images.githubusercontent.com/32956424/118074254-c175de80-b3d7-11eb-8c2d-625ec9468358.png)

#### Read/Write heads

Còn được gọi là đầu đọc ghi, là một bộ phận nằm trên bề mặt đĩa từ, có khả năng thay đổi từ tính của đĩa để đọc ghi dữ liệu. Đầu đọc ghi được gắn vào **actuator assembly** và được điều khiển bởi firmware.

Đầu đọc có công dụng đọc dữ liệu dưới dạng từ hoá trên bề mặt đĩa hoặc từ hoá lên mặt đĩa để ghi dữ liệu

Số lượng đầu đọc ghi luôn bằng số mặt hoạt động được của đĩa.

##### Flying Height

Đầu đọc ghi không thực sự nằm trên bề mặt đĩa từ, mà nằm phía trên đĩa từ một khoảng gọi là **Flying height** (độ cao bay).

Độ cao bay được đo bằng nanomet.

![image](https://user-images.githubusercontent.com/32956424/118072240-9093aa80-b3d3-11eb-89d2-4864de0c3b79.png)

Vị trí của đầu đọc ghi phải cực kỳ chính xác đối với từng sector trên đĩa.

Nếu đầu đọc ghi nằm ở sai vị trí, dữ liệu sẽ bị đọc ghi sai chỗ, dẫn đến data corruption (hư hỏng dữ liệu)

##### Head Crashes

Mặc dù đầu đọc ghi nằm trên đĩa từ nhưng không hề tiếp xúc với bề mặt đĩa, nếu đầu đọc ghi không may tiếp xúc với bề mặt đĩa, nó sẽ gây ra hiện tượng **Head crashes** - làm hỏng ổ cứng và khả năng từ tính của ổ, dẫn đến dữ liệu không thể truy cập được

##### Reading and Writing to the Platter

Đầu đọc ghi đảm nhận vai trò đọc ghi dữ liệu vào đĩa từ, thông qua khả năng thay đổi hướng từ tính của từng bit trên sector và track. 

Khi tiến hành ghi dữ liệu, đầu đọc ghi sẽ 

Ngược lại, khi đọc dữ liệu, đầu đọc ghi sẽ 

![image](https://user-images.githubusercontent.com/32956424/118077901-444e6780-b3df-11eb-9e77-b349cc39dfa6.png)

##### Heads and Internal Drive Addressing

Trên bề mặt các đĩa từ đều có đầu đọc ghi của riêng nó, kể cả mặt trên và mặt dưới. Do đó số đầu đọc ghi luôn nhiều hơn số đĩa từ

Ví dụ dưới đây là với 3 đĩa từ, thì sẽ có 6 đầu đọc ghi tương đương với từng mặt đĩa

![image](https://user-images.githubusercontent.com/32956424/118611557-2b7ef100-b7e7-11eb-8253-7e6d04c730d0.png)

Nội dung mục này nói về cơ chế đánh địa chỉ cylinder-head-sector (CHS). Để đánh địa chỉ cho từng vùng trong ổ đĩa, cần phải xác định cylinder number, head number và sector number.

Cylinder number cho biết số track, head number cho biết bề mặt nào của đĩa từ và sector number cho biết vị trí sector trên track.

Ví dụ trong hình là cylinder 512, head 0 và sector 33
  
![image](https://user-images.githubusercontent.com/32956424/118745849-4bfb8980-b881-11eb-9562-2cc035da8823.png)

### Tracks and Sectors

Trên bề mặt của tất cả đĩa từ đều được chia thành tracks và sectors.

![image](https://user-images.githubusercontent.com/32956424/118746524-9c271b80-b882-11eb-8b50-b5fd6b383ca9.png)

Trên bề mặt đĩa có nhiều tracks, chúng là những vòng tròn đồng tâm. Mỗi track được chia thành nhiều sector. 

Sector là đơn vị lưu trữ thông tin nhỏ nhất trong ổ đĩa, có kích thước 512 bytes mỗi sector. Giả sử nếu cần ghi 256 bytes, thì sẽ chỉ cần một sector để ghi 256 bytes đó, dung lượng còn lại sẽ bị bỏ phí. Tương tự, nếu cần ghi 1024 bytes thì sẽ cần 4 sector...

Trước đây, số lượng sector trên mỗi track là giống nhau, tuy nhiên, kích thước vật lý mỗi sector càng nhỏ dần khi ở gần tâm đĩa, mà mỗi sector chỉ có thể lưu trữ 512 bytes, dẫn đến những sector ở phía ngoài bị lãng phí không gian lưu trữ.

Do đó, để tối ưu không gian lưu trữ và tránh lãng phí, một kỹ thuật gọi là Zoned Data Recording (ZDR) đã ra đời. Hầu hết các ổ đĩa hiện này đều sử dụng công nghệ này. Là phương pháp tăng không gian lưu trữ của đĩa bằng các tăng số lượng sector trên các tracks bên ngoài, chia toàn bộ đĩa thành các zone khác nhau, các track cùng zone sẽ có lượng sector giống nhau, các tracks nằm ở gần tâm sẽ có ít sector hơn tracks ở ngoài.

![image](https://user-images.githubusercontent.com/32956424/118769435-5da55700-b8aa-11eb-8ab1-78534a25a5e7.png)

Ví dụ ở trên là đĩa được chia thành 3 zone: đỏ, xanh lá và trắng. Số lượng sector mỗi zone khác nhau và kích thước sector ở các zone cũng khác nhau





































