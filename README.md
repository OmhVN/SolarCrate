# SolarCrate Plugin - Hướng Dẫn Sử Dụng

## Tổng Quan
**SolarCrate** là plugin Minecraft hoàn chỉnh được phát triển bởi **Omh** với hệ thống crate và key tự động hoàn toàn có thể tùy chỉnh. Plugin hỗ trợ đầy đủ database, âm thanh, PlaceholderAPI và tương thích với **Spigot/Paper/Folia**.

**Thông Tin Plugin:**
- **Phiên bản**: 1.0.0  
- **Tác giả**: Omh
- **Mã Nguồn**: Donutkeyall và Vnceocrates
- **Tương thích**: Spigot/Paper/Folia 1.21.4+
- **Build tool**: Maven
- **Java**: 17+

---

## Tính Năng Chính

### **Hệ Thống Timer Tự Động**
- **Auto-distribution**: Tự động trao key theo chu kỳ 1 giờ
- **Thông báo tùy chỉnh**: Before/After messages với màu sắc
- **Clickable teleport**: Link teleport đến khu vực crates
- **Sound effects**: Âm thanh khi trao key (mặc định tắt)
- **Real-time countdown**: Hiển thị thời gian còn lại

### **Hệ Thống Crate Nâng Cao**
- **Tạo crate không giới hạn**: Tại bất kỳ vị trí nào
- **GUI Edit Menu**: Giao diện 54-slot trực quan
- **Slot management**: Quản lý từng slot riêng biệt
- **Interactive GUI**: Click để chọn item từ crate
- **Move system**: Di chuyển crate linh hoạt với tọa độ chính xác

### **Hệ Thống Key Đa Dạng**
- **Database storage**: Lưu key trong SQLite/MySQL
- **Multi-key support**: Hỗ trợ nhiều loại key khác nhau
- **Statistics tracking**: Theo dõi thống kê chi tiết
- **Bulk operations**: Trao/thu hồi key hàng loạt
- **Permission system**: Phân quyền chi tiết

### **GUI Systems**
- **Edit Menu**: 54-slot editing interface
- **Item Selection**: GUI chọn item từ crate
- **Confirmation**: Xác nhận trước khi nhận item
- **Visual effects**: Animation và particle effects

### **Admin Tools**
- **Comprehensive commands**: Hơn 15 lệnh admin
- **Debug system**: Hệ thống debug tích hợp
- **Statistics**: Thống kê chi tiết player và system
- **Hot-reload**: Reload config không cần restart

---

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
/solarcrate edit <tên>                # Mở GUI chỉnh sửa 54-slot

# Thêm/xóa items
/solarcrate additem <tên> <slot>      # Thêm item từ tay vào slot cụ thể
/solarcrate removeitem <tên> <slot>   # Xóa item tại slot cụ thể

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
/solarcrate takeall <key> <số>                 # Thu hồi từ tất cả players
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

### **Permission Groups Suggested**
```yaml
# VIP Group
permissions:
  - solarcrate.user.*
  
# Moderator Group  
permissions:
  - solarcrate.user.*
  - solarcrate.admin.info
  - solarcrate.admin.give
  
# Admin Group
permissions:
  - solarcrate.admin.*
```

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

## **Hướng Dẫn Sử Dụng Chi Tiết**

### **Setup Crate Đầu Tiên**
```bash
# Bước 1: Tạo crate với tọa độ chính xác
1. Đứng tại vị trí muốn đặt crate hoặc nhìn vào block
2. Gõ: /solarcrate create default
3. Crate được tạo tại vị trí chính xác

# Bước 2: Thêm items
/solarcrate edit default
# Mở GUI 54-slot để quản lý items
```

### **Sử Dụng Edit Menu (54-Slot GUI)**

**Các thao tác:**
1. **Add Item**: Cầm item → Click nút xanh "Add Item"
2. **Remove Mode**: Click nút đỏ → Click item muốn xóa
3. **Drag & Drop**: Kéo thả items giữa các slots
4. **Save & Close**: Lưu thay đổi và đóng GUI
5. **Cancel**: Thoát không lưu

### **Di Chuyển Crate (Tọa độ cải thiện)**
```bash
# Đến vị trí player chính xác (không trừ Y-coordinate)
/solarcrate movehere mycrate

# Đến block player đang nhìn (trong vòng 5 blocks)
/solarcrate move mycrate
```

### **Quản Lý Key System**
```bash
# Trao key individual
/solarcrate give default PlayerName 5

# Trao key mass distribution  
/solarcrate keyall default 2
# Tất cả online players nhận 2 default keys

# Thu hồi key từ 1 player
/solarcrate take default PlayerName 3

# Thu hồi key từ ALL players
/solarcrate takeall default 2
# Lấy tối đa 2 keys từ mỗi player online
```

### **Player Experience**
```
Cách sử dụng crate:
1. Tìm crate block trong world
2. Right-click vào crate
3. GUI mở → Chọn 1 item bất kỳ  
4. Click "Confirm" để nhận item
5. Item vào inventory, -1 key
```

### **Timer System**
**Tự động trao key mỗi 1 giờ (âm thanh mặc định tắt):**
```bash
# Xem thời gian còn lại
/solarcrate time
# Output: "Time until next crate: 23:45:12"

# Force chạy timer ngay (Admin only)
/solarcrate execute
# Tất cả online players nhận key ngay lập tức
```

## **Khắc phục sự cố và cải thiện**

### **Crate Không Hoạt Động**
**Nguyên nhân và giải pháp:**
- **Permissions**: Kiểm tra player có quyền `solarcrate.user.*`
- **Items trống**: Đảm bảo crate đã có items bên trong
- **Tọa độ sai**: Kiểm tra crate tồn tại tại vị trí chính xác
- **Plugin conflict**: Thử `/solarcrate reload`

### **Timer Không Chạy**
**Cải thiện error handling:**
- **Config validation**: Kiểm tra `timer.interval > 0` trong config.yml
- **Commands validation**: Đảm bảo lệnh trong `timer.commands` đúng format
- **Sound settings**: Âm thanh timer mặc định đã tắt
- **Recovery**: Plugin tự động khôi phục timer khi restart

### **Move/Create Commands - Tọa độ chính xác**
**Cải thiện:**
- `movehere`: Sử dụng `getLocation().getBlock()` thay vì `subtract(0,1,0)`
- `create`: Ưu tiên target block, fallback về player location chính xác
- **Error messages**: Hoàn toàn customizable trong message.yml
- **Coordinate display**: Hiển thị tọa độ chính xác trong thông báo

### **Database và Performance**
**Cải thiện:**
- **Auto-reconnection**: Tự động kết nối lại khi mất kết nối
- **Error recovery**: Graceful fallback từ MySQL về SQLite
- **Validation**: Kiểm tra database integrity khi khởi động
- **Logs**: Chi tiết hơn trong console để debug

## **PlaceholderAPI Integration**

### **Placeholders Có Sẵn**
- `%solarcrate_keys_received%` - Số key đã nhận (Fixed "Never" issue)
- `%solarcrate_last_key_time%` - Lần cuối nhận key (Proper timestamp)
- `%solarcrate_time_remaining%` - Thời gian còn lại đến timer tiếp theo
- `%solarcratekey_<cratename>%` - Số key của crate cụ thể

### **Ví Dụ Sử Dụng**
```
Bạn có: %solarcratekey_default% default keys
Số key epic: %solarcratekey_epic%
Lần cuối nhận: %solarcrate_last_key_time%
Timer còn: %solarcrate_time_remaining%
```

## **Tùy Chỉnh và Configuration**

### **Message System (Hoàn toàn tùy chỉnh)**
File `message.yml` hỗ trợ:
- **Prefix system**: `{prefix}` placeholder
- **Dynamic placeholders**: `{player}`, `{amount}`, `{name}`, `{x},{y},{z}`
- **All commands**: Mọi tin nhắn đều customizable
- **Error handling**: Professional error messages

### **Âm Thanh (Cải thiện)**
Trong `config.yml`, section `sounds`:
- `timer-execute` - **MẶCH ĐỊNH TẮT** (enabled: false)
- `key-receive` - Âm thanh khi nhận key
- `command` - Âm thanh lệnh thành công
- `error` - Âm thanh lỗi

### **Màu Sắc và Formatting**
Hỗ trợ đầy đủ:
- Legacy codes: `&a`, `&c`, `&e`
- Hex colors: `#00A4FC`, `#FF0000`
- Gradient support
- Format codes: `&l`, `&n`, `&o`

## 📝 Changelog

### Version 1.0.0
- ✅ Hệ thống Timer tự động
- ✅ Quản lý Crate và Key
- ✅ GUI Edit Menu
- ✅ Move Commands  
- ✅ PlaceholderAPI integration
- ✅ MySQL và SQLite support
- ✅ Sound effects
- ✅ Permissions system

## 🆘 Hỗ Trợ

Nếu gặp vấn đề:
1. Kiểm tra console logs
2. Thử `/solarcrate reload`
3. Kiểm tra permissions
4. Đảm bảo cấu hình đúng format

## 🔧 **Lệnh Nâng Cao**

### 🎯 **Item Management**
```bash
# Xóa item tại slot cụ thể
/solarcrate removeitem <crate> <slot>
# Ví dụ: /solarcrate removeitem default 5
# → Xóa item tại slot 5 của crate default

# Thêm item vào slot cụ thể
/solarcrate additem <crate> <slot>
# → Cầm item trong tay rồi chạy lệnh
```

### 📊 **Statistics & Debug**
```bash
# Xem thông tin chi tiết player
/solarcrate info PlayerName
# → Keys received, last key time, playtime

# Reload hot-config
/solarcrate reload
# → Reload không cần restart server

# Force timer execution
/solarcrate execute
# → Chạy distribution cycle ngay lập tức
```

---

## 🚨 **Lỗi Thường Gặp & Giải Pháp**

### ❌ **Crate không hoạt động**
```bash
Nguyên nhân: 
- Không có items trong crate
- Player không có keys
- Permissions không đúng

Giải pháp:
1. /solarcrate edit <crate> → Thêm items
2. /solarcrate give <key> <player> 1 → Trao key
3. Kiểm tra permissions: solarcrate.user.*
```

### ⏰ **Timer không chạy**
```bash
Nguyên nhân:
- Config timer bị sai
- Commands không hợp lệ

Giải pháp:
1. Kiểm tra config.yml → timer.interval: 3600
2. Kiểm tra timer.commands có đúng format
3. /solarcrate reload
4. /solarcrate execute để test
```

### 🗄️ **Database errors**
```bash
Nguyên nhân:
- MySQL connection failed
- File permissions

Giải pháp:
1. Set mysql.enabled: false → Dùng SQLite
2. Restart server
3. Kiểm tra logs trong console
```

### 🎨 **GUI không mở**
```bash
Nguyên nhân:
- Inventory đầy
- Plugin conflict

Giải pháp:
1. Clear inventory space
2. /solarcrate reload
3. Kiểm tra console errors
```

---

## 📞 **Support & Resources**

### **Dependencies**
- **PlaceholderAPI** - Placeholder integration  

### 🆘 **Getting Help**
1. **Logs**: Check console for detailed error messages
2. **Config**: Validate YAML syntax in config files  
3. **Permissions**: Double-check permission nodes
4. **Commands**: Use `/solarcrate help` for command list

---

> **🎊 Plugin được phát triển bởi Omh - SolarCrate v1.0.0**  
> **⚡ Professional Minecraft Crate System with Timer Auto-distribution**
