# NAS: Cách chạy Server "vĩnh viễn" trên NAS

Hiện tại bạn đang chạy lệnh node ws-server.js thủ công. Nếu bạn tắt cửa sổ terminal, server sẽ chết. Để nó chạy ngầm mãi mãi trên Synology:

Cách 1: Dùng PM2 (Khuyên dùng)

    Cài PM2: npm install pm2 -g

    Chạy server: pm2 start ws-server.js

    Lưu trạng thái: pm2 save

Cách 2: Dùng Task Scheduler của Synology

    Vào Control Panel > Task Scheduler.

    Create > Triggered Task > User-defined script.

    Trong phần Task Settings, dán lệnh:
    Bash

    cd /volume2/ws/ws && /usr/local/bin/node ws-server.js &

