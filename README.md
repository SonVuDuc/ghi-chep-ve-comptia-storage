# Một số ghi chép về Networking CompTIA Storage+

# 2. Storage Device

Có 3 hình thức lưu trữ:
 * **Disk drive**: ổ đĩa cơ học
 * **Solid-state drive**: ổ đĩa thể rắn  
 * **Tape drive**: ổ băng

Disk, solid-state và tape đều thuộc kiểu **persistent storage** hay **nonvolatile**, tức là dữ liệu không bị mất đi khi ta dừng cấp điện cho chúng.

## The Mechanical Disk Drive

### The Anatomy of a Disk Drive

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

#### Read/Write heads

Còn được gọi là đầu đọc ghi, là một bộ phận nằm trên bề mặt đĩa từ, đảm nhận vai trò đọc ghi dữ liệu. Đầu đọc ghi được gắn vào **actuator assembly** và được điều khiển bởi firmware.

Đầu đọc có công dụng đọc dữ liệu dưới dạng từ hoá trên bề mặt đĩa hoặc từ hoá lên mặt đĩa để ghi dữ liệu

Số lượng đầu đọc ghi luôn bằng số mặt hoạt động được của đĩa.

##### Flying Height

Đầu đọc ghi không thực sự nằm trên bề mặt đĩa từ, mà nằm phía trên đĩa từ một khoảng gọi là **Flying height** (độ cao bay).

Độ cao bay được đo bằng nanomet.

![image](https://user-images.githubusercontent.com/32956424/118072240-9093aa80-b3d3-11eb-89d2-4864de0c3b79.png)

Vị trí của đầu đọc ghi phải cực kỳ chính xác đối với từng sector trên đĩa.

Nếu đầu đọc ghi nằm ở sai vị trí, dữ liệu sẽ bị đọc ghi sai chỗ, dẫn đến data corruption (hư hỏng dữ liệu)

































