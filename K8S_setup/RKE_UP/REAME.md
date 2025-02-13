## Sử dụng RKE để triểnkhai cụm K8S
Sau khi đã cài đặt các điều kiện cần thiết lên môi trường server đến bước này việc triển khai cụm K8S lên khá đơn giản.
Chúng ta cần chuẩn bị:
 * File binary: rke, helm, kubectl:
 * File rke config: https://rke.docs.rancher.com/example-yamls#minimal-clusteryml-example
 * Kết nối ssh từ server chạy rke đến các server cần cài k8s

Các bước thực hiện như sau:
1. Trên server chạy RKE thực hiện gen key và copy ssh key id đến các server cần cài k8s
2. Cấp quyền thực thi cho các file binary
3. Tại thư mục chứa file config chạy lệnh: rke up --config config_file.yaml
4. Copy file kube config sinh ra sau khi chạy lênh rke up vào ~/.kube/config
5. Thế là xong

Một số lưu ý:
- Phiên bản k8s phải được hỗ trợ bởi file binary rke. Các file binary thường hỗ trợ một vài phiên bản k8s
- Nếu cụm k8s nằm trong môi trường nội bộ không có kết nối internet thì cấu hình sử dụng private Registry
- Trong trường hợp OS phiên bản cũ có thể cấu hình bỏ qua check phiên bản docker và sử dụng dockerd như container runtime
- Cluster IP range nên chọn giải không nằm trong các giải IP private mà công ty đã sử dụng
- args pod-eviction-timeout không còn hỗ trợ, nếu gặp lỗi hãy loại bỏ arg này