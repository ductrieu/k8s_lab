# Triển khai hệ thống K8S
### Hiện nay có rất nhiều tool có thể sử dụng để triển khai một cụm K8S như:
* Kubeadm
* KubeSpay
* RKE/RKE2
* Rancher
### Mỗi cách đều có ưu nhược điểm nhanh. Đối với dự án này tôi sẽ sử dụng RKE để setup cụm K8S. Lý do lựa chọn RKE là các cấu hình setup được viết trong cùng 1 file config rất dẽ kiểm soát và cập nhật. Ngoài ra RKE còn hỗ trợ công cụ để backup và restore cụm, triển khai ở môi trường internet hạn chế  phù hợp với môi trường làm việc thực tế

### Hướng dẫn cài đặt RKE có thể tham khả thêm ở đây: https://rke.docs.rancher.com/
### Trong bài lab này tôi sẽ kết hợp sử dụng ansible để cấu hình các thiết lập ban đầu trên các server và sử dụng RKE để triển khai cụm K8S 

