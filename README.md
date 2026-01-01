# ☁️ Szz Cloud Project - Virtual Environment

<p align="center">
  <img src="https://img.shields.io/badge/Status-Stable-green.svg" alt="Status">
  <img src="https://img.shields.io/badge/Platform-GitHub%20Codespaces-blue" alt="Platform">
  <img src="https://img.shields.io/badge/OS-Ubuntu%20|%20Windows%20Style-orange" alt="OS">
</p>

---

## 👨‍💻 Đội Ngũ Phát Triển (Developers)
Dự án được xây dựng và duy trì bởi:
* **Project Owner:** `@sonw0106`
* **Lead Developer:** `@ph.linh.dev0109`

---

## 🚀 Tính Năng Nổi Bật
- **Ubuntu Desktop Pro:** Môi trường Linux đầy đủ, cực kỳ ổn định.
- **Windows UI Style:** Giao diện được thiết kế theo phong cách Windows 11 quen thuộc.
- **High Performance:** Tối ưu hóa 2GB Shared Memory giúp lướt web mượt mà.
- **Security:** Bảo mật và an toàn trên hạ tầng GitHub.

---

## 💬 Liên Hệ & Hỗ Trợ
* **Discord Server:** [Szz Cloud Community](https://discord.gg/QBWW7Jms6F)
* **Discord ID:** `sonw0106` | `ph.linh.dev0109`

---

## 🛠️ Mã Nguồn Cài Đặt (Installation Code)

Bạn chỉ cần copy toàn bộ đoạn code dưới đây, dán vào **Terminal** của GitHub Codespaces và nhấn **Enter**:

```bash
cat << 'EOF' > szz_cloud.sh
#!/bin/bash
clear

# --- THÔNG TIN DỰ ÁN ---
OWNER1="sonw0106"
OWNER2="ph.linh.dev0109"
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
echo -e "${WHITE}  DISCORD:${NC} ${GREEN}$DISCORD_SV${NC}"
echo "------------------------------------------------------------------------"

echo -e "${CYAN}[*]${NC} Đang khởi tạo Szz Cloud VPS..."
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
echo -e "🚀 Truy cập: Tab PORTS -> Cổng 6080 -> PUBLIC"
echo "------------------------------------------------------------------------"
EOF

chmod +x szz_cloud.sh
./szz_cloud.sh
