# ☁️ Szz Cloud Project - Virtual Environment

<p align="center">
  <img src="https://img.shields.io/badge/Status-Stable-green.svg" alt="Status">
  <img src="https://img.shields.io/badge/Platform-GitHub%20Codespaces-blue" alt="Platform">
  <img src="https://img.shields.io/badge/OS-Ubuntu%20|%20Windows%20Style-orange" alt="OS">
</p>

---

## 👨‍💻 Đội Ngũ Phát Triển (Developers)
* **Project Owner:** `@sonw0106`
* **Lead Developer:** `@ph.linh.dev0109`
* **Community:** [D4F Community](https://discord.gg/QBWW7Jms6F)

---

## 📖 Hướng Dẫn Sử Dụng Siêu Chi Tiết (A-Z)

### Bước 1: Khởi tạo môi trường GitHub Codespaces
1. Tại Repository này, bạn nhấn vào nút **Code** (màu xanh).
2. Chọn tab **Codespaces**.
3. Nhấn vào **Create codespace on main** (Dấu cộng). Đợi khoảng 30 giây để GitHub chuẩn bị máy chủ.

### Bước 2: Chạy mã nguồn Szz Cloud
1. Khi màn hình đen (Terminal) hiện ra ở phía dưới, bạn hãy copy toàn bộ đoạn **Installation Code** ở mục dưới cùng của trang này.
2. Dán (Ctrl+V) vào Terminal và nhấn **Enter**.
3. Đợi hệ thống tự động cài đặt trong khoảng 1-2 phút. Khi thấy dòng chữ **✅ KÍCH HOẠT THÀNH CÔNG!** hiện ra là xong.

### Bước 3: Kết nối vào giao diện máy tính (VNC)
1. Nhìn xuống thanh menu phía dưới cùng của GitHub, chọn tab **PORTS** (nằm cạnh tab Terminal).
2. Tại dòng cổng **6080**, bạn nhìn sang cột **Visibility**, nhấn vào chữ **Private** để chuyển nó thành **Public** (Bắt buộc để có thể truy cập).
3. Tại cột **Local Address**, nhấn vào biểu tượng **quả địa cầu** (hoặc link địa chỉ) để mở máy ảo trên trình duyệt.

### Bước 4: Tận hưởng
* Một tab mới sẽ mở ra, bạn sẽ thấy giao diện máy tính Ubuntu phong cách Windows.
* Mọi dữ liệu bạn lưu trong thư mục `config` sẽ không bị mất khi bạn khởi động lại.

---

## 🛠️ Mã Nguồn Cài Đặt (Installation Code)

*Copy và dán đoạn này vào Terminal:*

```bash
cat << 'EOF' > szz_cloud.sh
#!/bin/bash
clear

# --- THÔNG TIN DỰ ÁN ---
OWNER1="sonw0106"
OWNER2="ph.linh.dev0109"
SERVER_NAME="D4F Community"
DISCORD_SV="[https://discord.gg/QBWW7Jms6F](https://discord.gg/QBWW7Jms6F)"

# --- MÀU SẮC ---
CYAN='\033[0;36m'
GREEN='\033[0;32m'
PURPLE='\033[0;35m'
YELLOW='\033[1;33m'
WHITE='\033[1;37m'
NC='\033[0m'

# --- LOGO KHỞI ĐỘNG ---
echo -e "${CYAN}"
echo "  ███████╗███████╗███████╗     ██████╗██╗      ██████╗ ██╗   ██╗██████╗ "
echo "  ██╔════╝██╔════╝╚══███╔╝    ██╔════╝██║     ██╔═══██╗██║   ██║██╔══██╗"
echo "  ███████╗█████╗    ███╔╝     ██║     ██║     ██║   ██║██║   ██║██║  ██║"
echo "  ╚════██║██╔══╝   ███╔╝      ██║     ██║     ██║   ██║██║   ██║██║  ██║"
echo "  ███████║███████╗███████╗    ╚██████╗███████╗╚██████╔╝╚██████╔╝██████╔╝"
echo "  ╚══════╝╚══════╝╚══════╝     ╚═════╝╚══════╝ ╚═════╝  ╚═════╝ ╚═════╝ "
echo -e "                   PREMIUM CLOUD OS - WINDOWS STYLE${NC}"
echo "------------------------------------------------------------------------"
echo -e "${WHITE}  OWNERS:${NC} ${YELLOW}$OWNER1${NC} & ${YELLOW}$OWNER2${NC}"
echo -e "${WHITE}  SERVER:${NC} ${GREEN}$SERVER_NAME${NC}"
echo -e "${WHITE}  DISCORD:${NC} ${CYAN}$DISCORD_SV${NC}"
echo "------------------------------------------------------------------------"

echo -e "${CYAN}[*]${NC} Đang khởi tạo Szz Cloud VPS (D4F Community)..."
sudo apt update -y > /dev/null 2>&1
sudo apt install docker.io -y > /dev/null 2>&1
sudo docker rm -f szz_cloud > /dev/null 2>&1

echo -e "${CYAN}[*]${NC} Đang triển khai giao diện Windows Style..."
sudo docker run -d \
  --name szz_cloud \
  -p 6080:3000 \
  -e TITLE="Szz Cloud - $OWNER1 & $OWNER2" \
  -e TZ=Asia/Ho_Chi_Minh \
  --shm-size="2gb" \
  lscr.io/linuxserver/webtop:ubuntu-xfce

echo "------------------------------------------------------------------------"
echo -e "${GREEN}✅ KÍCH HOẠT THÀNH CÔNG!${NC}"
echo -e "🚀 Thực hiện BƯỚC 3 trong hướng dẫn để vào máy máy ảo."
echo "------------------------------------------------------------------------"
EOF

chmod +x szz_cloud.sh
./szz_cloud.sh
