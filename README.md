# SolarCrate Plugin

## Tổng Quan
**SolarCrate** là plugin Minecraft hoàn chỉnh được phát triển bởi **Omh** với hệ thống crate và key tự động hoàn toàn có thể tùy chỉnh và tương thích với **Spigot/Paper/Folia**.

**Thông Tin Plugin:**
- **Phiên bản**: 1.2 - R12
- **Tác giả**: OmhVN
- **Tương thích**: Paper/Folia
- **Database Systems:** SQLite.

## Danh Sách Lệnh

### Lệnh User
```bash
/solarcrate help                    # Hiển thị trợ giúp
/solarcrate time                    # Xem thời gian đến lần trao key tiếp theo
/solarcrate info                    # Xem thông tin về key của bạn
/solarcrate info <player>           # Xem thông tin key của player khác (Admin)
/solarcrate version                 # Xem phiên bản plugin
```

### **Lệnh Admin - Quản Lý Crate**
```bash
# Tạo và quản lý crate
/solarcrate create <tên>              # Tạo crate mới tại vị trí chính xác
/solarcrate delete <tên>              # Xóa crate hoàn toàn
/solarcrate edit <tên>                # Mở GUI chỉnh sửa.

# Di chuyển crate (tọa độ cải thiện)
/solarcrate movehere <tên>            # Di chuyển crate đến vị trí player chính xác
/solarcrate move <tên>                # Di chuyển crate đến nơi player nhìn
```

### **Lệnh Admin - Quản Lý Key**
```bash
# Trao key
/solarcrate give <key> <số>                    # Trao key cho bản thân
/solarcrate give <key> <player> <số>           # Trao key cho player cụ thể
/solarcrate keyall <crate> <số>                # Trao key cho tất cả online

# Thu hồi key  
/solarcrate take <key> <player> <số>           # Thu hồi từ 1 player
```

### **Lệnh Admin - Hệ Thống**
```bash
/solarcrate reload                    # Reload toàn bộ cấu hình
/solarcrate execute                   # Force execute timer ngay
/solarcrate info <player>             # Xem thống kê player chi tiết
```

## **Hệ Thống Permissions Chi Tiết**

### **User Permissions** 
| Permission | Mô tả | Mặc định |
|------------|-------|----------|
| `solarcrate.user.time` | Xem thời gian còn lại timer | Default |
| `solarcrate.user.info` | Xem thông tin key bản thân | Default |
| `solarcrate.user.help` | Sử dụng lệnh help | Default |
| `solarcrate.user.version` | Xem phiên bản plugin | Default |

### **Admin Permissions**
| Permission | Mô tả | Chức năng |
|------------|-------|-----------|
| `solarcrate.admin.reload` | Reload plugin | Hot-reload configs |
| `solarcrate.admin.execute` | Force timer | Chạy timer ngay lập tức |
| `solarcrate.admin.crate` | **Quản lý crate đầy đủ** | Create, edit, move, delete |
| `solarcrate.admin.give` | Trao key | Individual key distribution |
| `solarcrate.admin.keyall` | Trao key hàng loạt | Mass key distribution |
| `solarcrate.admin.take` | Thu hồi key | Individual + bulk removal |
| `solarcrate.admin.info` | Xem thông tin players | Statistics access |
| `solarcrate.admin.notify` | Nhận thông báo admin | Staff notifications |

## ⚙️ Cấu Hình

### config.yml
```yaml
language: "vi_vn"

debug: false

use_prefix: false

# Giới hạn số key mỗi người chơi có thể giữ (-1 = không giới hạn)
max-keys-per-player: -1

auto-save-interval: 5
timer:
  # Thời gian giữa các lần phát key (-1 = tắt timer)
  # Hỗ trợ định dạng: giây (3600), hoặc HMS (1h, 30m, 1h30m, 2h30m15s)
  # Ví dụ: "1h" = 1 tiếng, "30m" = 30 phút, "1h30m" = 1 tiếng 30 phút
  interval: "1h"
  
  # Lệnh chạy khi timer kích hoạt (dùng {player} cho tên người chơi)
  commands:
    - "solarcrate give common {player} 1"

clickable:
  command: "/warp crates"
  text: "&b&l⚡ BẤM ĐỂ DỊCH CHUYỂN &7→ /warp crates"
```

## **PlaceholderAPI Integration**

### **Placeholders Có Sẵn**
- `%sc_time%` - Hiện Thời Gian (Định Dạng H:M:S)
- `%sc_key_<cratename>%` - Số key của crates
- `%sc_key_<tên_crate>%` - Hiển thị keys của crate theo định dạng K/M/B/T
- `%sc_key_raw_<tên_crate>%` - Hiển thị số gốc không định dạng
---

> **Plugin được phát triển bởi OmhVN - SolarCrate v1.2 - R09**
