# SolarCrate Plugin

## Tổng Quan
**SolarCrate** là plugin Minecraft hoàn chỉnh được phát triển bởi **Omh** với hệ thống crate và key tự động hoàn toàn có thể tùy chỉnh. Plugin hỗ trợ đầy đủ database, âm thanh, PlaceholderAPI và tương thích với **Spigot/Paper/Folia**.

**Thông Tin Plugin:**
- **Phiên bản**: 1.1 (Bản Cũ 1.0)
- **Tác giả**: Omh
- **Mã Nguồn**: Donutkeyall và Vnceocrates
- **Tương thích**: Spigot/Paper/Folia 1.21.4+

---
## Lưu Ý
### Ngưng Support Database
Đã ngưng hỗ trợ Database từ 1.0 và không có bất kì bản phát hành mới nào hỗ trợ nữa.

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
# Timer Configuration
timer:
  interval: 3600                    # Khoảng thời gian giữa các lần trao key (giây)
  commands:
    - "solarcrate give default {player} 1"  # Lệnh thực hiện khi timer kích hoạt

# Messages
messages:
  before:                           # Tin nhắn trước khi trao key
    - "&a&l⚡ &eSolarCrate Distribution Starting..."
  after:                            # Tin nhắn sau khi trao key
    - "&a&l✓ &eCrate keys have been distributed!"

# Clickable message
clickable:
  command: "/warp crates"           # Lệnh khi click message
  text: "#00A4FB[CLICK TO TELEPORT] &fOr type /warp crates"

# Database configuration
database:
  mysql:
    enabled: false                  # Sử dụng MySQL (false = SQLite)
    host: "localhost"
    port: 3306
    database: "solarcrate"
    username: "root"
    password: ""

# Sound effects
sounds:
  timer-execute:
    enabled: false                  # Mặc định tắt âm thanh timer
    sound: "BLOCK_NOTE_BLOCK_PLING"
    volume: 1.0
    pitch: 1.0
```

## **PlaceholderAPI Integration**

### **Placeholders Có Sẵn**
- `%sc_time%` - Hiện Thời Gian (Định Dạng H:M:S)
- `%sc_key_<cratename>%` - Số key của crates
---

> **Plugin được phát triển bởi Omh - SolarCrate v1.1**  
