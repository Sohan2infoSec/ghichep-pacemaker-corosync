# ghichep-pacemaker-corosync
Ghi chép về pacemaker corosync


___


# Nội dung

- [A. Tổng quan về High Availability](docs/ha-overview.md)
	+ [A.1 Giới thiệu về High Availability](docs/ha-overview.md#whatis-ha)
	+ [A.2 Các khái niệm, thuật ngữ cần biết trong HA](docs/ha-overview.md#concepts)
		+ [A.2.1 Cluster](docs/ha-overview.md#whatis-cl)
		+ [A.2.2 Resource](docs/ha-overview.md#resource)
		+ [A.2.3 Pacemaker](docs/ha-overview.md#pacemaker)
		+ [A.2.4 Corosync](docs/ha-overview.md#corosync)
		+ [A.2.5 Quorum](docs/ha-overview.md#quorum)
		+ [A.2.6 STONITH](docs/ha-overview.md#stonith)
		+ [A.2.7 Các port sử dụng cho HA cluster](docs/ha-overview.md#others-concept)

- [B. Tổng quan về pacemaker](docs/pacemaker-overview.md)
	- [B.1 Tổng quan về quorum](docs/quorum-overview.md)
	- [B.2 Tổng quan về STONITH/ fencing](docs/fencing-overview.md)
	- [B.3 Tổng quan về resource](docs/resource-overview.md)

- [1. Cài đặt pacemaker](docs/pacemaker-corosync-installing.md)
	- [1.1 Môi trường cài đặt](docs/pacemaker-corosync-installing.md#envir)
	- [1.2 Mô hình hệ thống](docs/pacemaker-corosync-installing.md#block)
	- [1.3 IP Plan](docs/pacemaker-corosync-installing.md#ipPlan)
	- [1.4 Cài đặt nginx và modules](docs/pacemaker-corosync-installing.md#nginx)
	- [1.5 Kiểm tra cài đặt nginx](docs/pacemaker-corosync-installing.md#test)
	- [1.6 Cài đặt pacemaker và corosync để tạo cluster cho nginx](docs/pacemaker-corosync-installing.md#pacemaker)
	- [1.7 Cấu hình để thêm các resources vào Cluster](docs/pacemaker-corosync-installing.md#configCluster)
	- [1.8 Thêm resource NGINX để pacemaker quản lý.](docs/pacemaker-corosync-installing.md#addResources)
	- [1.9 Quản lý các resource với Web-GUI](docs/pacemaker-corosync-installing.md#webgui)

- [2. Các câu lệnh của pacemaker](docs/cmd-pcmk.md)
- [3. Tạo và quản lý một cluster](docs/create-cluster-pcmk.md)
	- [3. 1  Tạo một cluster](docs/create-cluster-pcmk.md#create)
		- [3.1.1 Khởi động pacemaker](docs/create-cluster-pcmk.md#start)
		- [3.1.2 Xác thực các node tham gia vào cluster](docs/create-cluster-pcmk.md#authen)
		- [3.1.3 Cấu hình và khởi động các node trong cluster](docs/create-cluster-pcmk.md#cluster-nodes)
		- [3.1.4 Enable và Disable các dịch vụ cluster](docs/create-cluster-pcmk.md#ed-services)
	- [3.2 Quản lý các node trong cluster](docs/create-cluster-pcmk.md#man-node)
		- [3.2.1 Dừng các dịch vụ trong cluster](docs/create-cluster-pcmk.md#stop-node)
		- [3.2.2 Thêm node mới vào cluster](docs/create-cluster-pcmk.md#add-node)
		- [3.2.3 Xóa bỏ node trong cluster](docs/create-cluster-pcmk.md#rem-node)
	- [3.3 Xóa cấu hình cluster](docs/create-cluster-pcmk.md#rem-config)
	- [3.4 Hiển thị trạng thái cluster](docs/create-cluster-pcmk.md#disp-stat)

- [4. Tìm hiểu về cách quản lý các resource trong pacemaker](docs/resource-pacemaker.md)
	- [4.1. Tạo một resource](docs/resource-pacemaker.md#create)
	- [4.2. Các tính chất của resource](docs/resource-pacemaker.md#properties)
	- [4.3. Các tham số cụ thể về resource](docs/resource-pacemaker.md#parameter)
	- [4.4. Các tùy chọn cho resource](docs/resource-pacemaker.md#options)
	- [4.5. Các nhóm resource](docs/resource-pacemaker.md#groups)
		- [4.5.1. Các tùy chọn cho nhóm resource](docs/resource-pacemaker.md#options-group)
		- [4.5.2. Các gắn kết liên quan tới nhóm](docs/resource-pacemaker.md#stickness)
	- [4.6. Sự vận hành các resource](docs/resource-pacemaker.md#operations)
	- [4.7. Hiển thị cấu hình của resource](/resource-pacemaker.md#displaydocs-config)
	- [4.8. Chỉnh sửa các tham số cụ thể của resource](/resource-pacemaker.md#modifieddocs-parameters)
	- [4.9 Kích hoạt, vô hiệu hóa nhóm các resource](/resource-pacemaker.md#enablingdocs-disabling)
	- [4.10. Xóa các cảnh báo của các resource](docs/resource-pacemaker.md#cleanup)
- [5. Các ràng buộc trong pacemaker cho resource](docs/constraint-pacemaker.md)
	- [5.1. Ràng buộc vị trí](docs/constraint-pacemaker.md#location-constraints)
		- [5.1.1. Cấu hình một "Opt-In" Cluster](docs/constraint-pacemaker.md#opt-in)
		- [5.1.2. Cấu hình một "Opt-Out" Cluster](docs/constraint-pacemaker.md#opt-out)
	- [5.2. Ràng buộc về thứ tự](docs/constraint-pacemaker.md#order-constraints)
		- [5.2.1. Thứ tự cố định](docs/constraint-pacemaker.md#mand-order)
		- [5.2.2. Thứ tự linh động](docs/constraint-pacemaker.md#advi-order)
		- [5.2.3. Thứ tự tập hợp các resource](docs/constraint-pacemaker.md#sets-order)
		- [5.2.4. Xóa bỏ resource từ các ràng buộc thứ tự](docs/constraint-pacemaker.md#remove-order)
	- [5.3. Ràng buộc colocation của resources](docs/constraint-pacemaker.md#colocation-constraint)
	- [5.3.1. Vị trí cố định](docs/constraint-pacemaker.md#mand-place)
	- [5.3.2. Vị trí linh động](docs/constraint-pacemaker.md#advi-place)
	- [5.3.3. Colocation các tập hợp resource](docs/constraint-pacemaker.md#sets-place)
	- [5.3.4. Xóa bỏ ràng buộc colocation](docs/constraint-pacemaker.md#colocation-remove)
	- [5.4. Hiển thị cấu hình các ràng buộc](docs/constraint-pacemaker.md#display-constraints)

- [E.1 Cài đặt pacemaker và tạo nginx.](docs/master-resource-pcmk.md#install)
- [E.2 Cấu hình resource](docs/master-resource-pcmk.md#configure)
	- [E.2.1 Sử dụng câu lệnh](docs/master-resource-pcmk.md#cmd)
	- [E.2.2 Sử dụng giao diện website](docs/master-resource-pcmk.md#gui)
	- [E.2.3 Khởi động lại dịch vụ trong cluster](docs/master-resource-pcmk.md#star)

# Tài liệu tham khảo:

- [High Availability Add-on](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/High_Availability_Add-On_Overview/ch-introduction-HAAO.html)

- [Cluster Labs](http://clusterlabs.org/doc/en-US/Pacemaker/1.0/html/Pacemaker_Explained/index.html)
