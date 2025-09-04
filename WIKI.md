# SolarCrate Plugin - Hướng Dẫn Sử Dụng

## Tổng Quan
**SolarCrate** là plugin Minecraft hoàn chỉnh và chuyên nghiệp được phát triển bởi **Omh** với hệ thống crate và key tự động hoàn toàn có thể tùy chỉnh. Plugin hỗ trợ đầy đủ database, âm thanh, PlaceholderAPI và tương thích với **Spigot/Paper/Folia**.

**Thông Tin Plugin:**
- **Phiên bản**: 1.0.1-last-2 (Fixed)  
- **Tác giả**: Omh  
- **Tương thích**: Paper/Spigot/Folia 1.21.1+
- **Build tool**: Maven
- **Java**: 17+
- **Ngôn ngữ**: Tiếng Việt (100%)
- **🆕 CẢI THIỆN**: Placeholder ngắn gọn, Error handling tốt hơn

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
- **🆕 Drag & Drop**: Kéo thả items trực tiếp trong GUI
- **Auto-save**: Tự động lưu khi di chuyển items
- **Interactive GUI**: Click để chọn item từ crate
- **Move system**: Di chuyển crate linh hoạt với tọa độ chính xác

### **Hệ Thống Key Đa Dạng**
- **Database storage**: Lưu key trong SQLite/MySQL
- **Multi-key support**: Hỗ trợ nhiều loại key khác nhau
- **Statistics tracking**: Theo dõi thống kê chi tiết
- **Bulk operations**: Trao/thu hồi key hàng loạt
- **Permission system**: Phân quyền chi tiết

### **🆕 GUI Systems - Tiếng Việt 100%**
- **Edit Menu**: Giao diện chỉnh sửa 54-slot bằng tiếng Việt
- **Drag & Drop**: Kéo thả items trực tiếp từ inventory
- **Item Selection**: GUI chọn item từ crate (tiếng Việt)
- **Confirmation**: Xác nhận trước khi nhận item (tiếng Việt)
- **Auto-transfer**: Shift-click để chuyển items nhanh
- **Real-time saving**: Lưu tự động khi thay đổi

### **Admin Tools**
- **Comprehensive commands**: Hơn 15 lệnh admin
- **Debug system**: Hệ thống debug tích hợp
- **Statistics**: Thống kê chi tiết player và system
- **Hot-reload**: Reload config không cần restart

---

## Danh Sách Lệnh

### 🆕 Lệnh User - Commands Ngắn Gọn
```bash
# Lệnh rút gọn (khuyến khích sử dụng)
/sc help                           # Hiển thị trợ giúp đầy đủ
/sc time                           # Xem thời gian đến lần trao key tiếp theo
/sc info                           # Xem thông tin về key của bạn
/sc info <player>                  # Xem thông tin key của player khác (Admin)
/sc version                        # Xem phiên bản plugin

# Lệnh đầy đủ (vẫn hoạt động)
/solarcrate help                   # Tương tự /sc help
/crate help                        # Alias khác
/solar help                        # Alias khác
```

### **🆕 Lệnh Admin - Commands Ngắn Gọn & Drag-Drop**
```bash
# Tạo và quản lý crate
/sc create <tên>                      # Tạo crate mới tại vị trí chính xác
/sc delete <tên>                      # Xóa crate hoàn toàn
/sc edit <tên>                        # Mở GUI DRAG & DROP 54-slot!

# 🆕 KHÔNG CẦN ADD/REMOVE ITEMS NỮA!
# Chỉ cần dùng: /sc edit <tên>
# Rồi kéo thả items trực tiếp!

# Di chuyển crate
/sc movehere <tên>                    # Di chuyển crate đến vị trí player
/sc move <tên>                        # Di chuyển crate đến nơi player nhìn
```

### **🆕 Hướng Dẫn Drag & Drop (Tiếng Việt)**
```
✨ Cách sử dụng tính năng kéo thả mới:

1️⃣ Mở GUI: /sc edit <tên_crate>
2️⃣ GUI sẽ hiển thị:
   ▫️ 27 slot đầu: Items của crate
   ▫️ 27 slot giữa: Inventory của bạn
   ▫️ 9 slot cuối: Nút điều khiển

3️⃣ Cách thực hiện:
   ✅ Kéo items từ inventory vào crate
   ✅ Di chuyển items giữa các slot crate
   ✅ Shift-click để chuyển nhanh
   ✅ Right-click để đặt 1 item
   ✅ Tự động lưu khi thay đổi!
   
4️⃣ Remove Mode (khi cần xóa):
   - Click nút "Chế độ xóa" để bật/tắt
   - Click vào items cần xóa
```

### **Lệnh Admin - Quản Lý Key (Commands Ngắn)**
```bash
# Trao key
/sc give <key> <số>                    # Trao key cho bản thân
/sc give <key> <player> <số>           # Trao key cho player cụ thể
/sc keyall <crate> <số>                # Trao key cho tất cả online

# Thu hồi key  
/sc take <key> <player> <số>           # Thu hồi từ 1 player
/sc takeall <key> <số>                 # Thu hồi từ tất cả players
```

### **Lệnh Admin - Hệ Thống (Commands Ngắn)**
```bash
/sc reload                    # Reload toàn bộ cấu hình
/sc execute                   # Force execute timer ngay
/sc info <player>             # Xem thống kê player chi tiết
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
**Interface Layout:**
```
┌─────────────────────────────────────────────────────┐
│ [Items Area] - 45 slots (5 rows)                   │
│ Slot 0-44: Kéo thả items trực tiếp                 │
├─────────────────────────────────────────────────────┤
│ [Control Panel] - Bottom row                       │
│ [Add] [Remove] [---] [---] [---] [Cancel] [Save]   │
└─────────────────────────────────────────────────────┘
```

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

## **🆕 PlaceholderAPI Integration - NGẮN GỌN HỚN!**

### **🔥 Placeholders MỚI - Ngắn gọn dễ dùng**
| Placeholder Ngắn | Placeholder Đầy đủ | Mô tả |
|------------------|-------------------|-------|
| `%solarcrate_time%` | `%solarcrate_keyalltime%` | Thời gian còn lại (định dạng HMS) |
| `%solarcrate_timer%` | `%solarcrate_keyalltime%` | Tương tự time (định dạng HMS) |
| `%solarcrate_sec%` | `%solarcrate_keyallsec%` | Giây còn lại (số) |
| `%sckey_default%` | `%SCKey_default%` | Số key default (ngắn hơn) |
| `%sckey_epic%` | `%SCKey_epic%` | Số key epic (ngắn hơn) |

### **🎯 Ví Dụ Sử Dụng - NGẮN GỌN**
```
⏰ Timer: %solarcrate_time%          → "1h 30m 45s"
🔑 Default Keys: %sckey_default%     → "5"
💎 Epic Keys: %sckey_epic%           → "2" 
⏱️ Giây còn lại: %solarcrate_sec%    → "5445"

-- HOẶC dùng placeholders đầy đủ --
Bạn có: %solarcratekey_default% default keys
Timer còn: %solarcrate_keyalltime%   → "1h 30m 45s"
```

### **📝 Migration Guide - Chuyển đổi**
```yaml
# CŨ (vẫn hoạt động)
%solarcrate_keyalltime% → %solarcrate_time%
%SCKey_default% → %sckey_default%

# MỚI (khuyến khích) - Định dạng HMS
%solarcrate_time% - ngắn hơn 50% + định dạng HMS!
%sckey_default% - ngắn hơn 40%!

# VÍ DỤ OUTPUT
Timer cũ: "01:30:45" → Timer mới: "1h 30m 45s"
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

## 🚨 **Lỗi Thường Gặp & Giải Pháp - CẢI THIỆN 2024**

### ❌ **Crate không hoạt động**
```bash
NGUYÊN NHÂN: 
- Không có items trong crate
- Player không có keys
- Permissions không đúng
- Plugin compatibility issue

🔧 GIẢI PHÁP:
1. /sc edit <crate> → Thêm items (dùng lệnh ngắn)
2. /sc give <key> <player> 1 → Trao key
3. Kiểm tra permissions: solarcrate.user.*
4. /sc reload → Hot reload để fix
5. Kiểm tra console logs để thấy chi tiết
```

### ⏰ **Timer không chạy - CẢI THIỆN**
```bash
NGUYÊN NHÂN:
- Config timer bị sai
- Commands không hợp lệ
- Plugin startup error

🔧 GIẢI PHÁP NÂNG CAO:
1. Kiểm tra config.yml → timer.interval: 3600
2. Kiểm tra timer.commands có đúng format
3. /sc reload (dùng lệnh ngắn)
4. /sc execute để test ngay
5. Xem console logs - plugin hiện tại có error handling tốt hơn!
6. Dùng placeholder %solarcrate_status% để kiểm tra realtime
```

### 🗄️ **Database errors - ĐÃ FIX**
```bash
NGUYÊN NHÂN:
- MySQL connection failed
- File permissions
- Version compatibility

🔧 GIẢI PHÁP CẢI THIỆN:
1. Plugin hiện tại có auto-fallback từ MySQL → SQLite
2. Improved error recovery trong startup
3. Restart server
4. Kiểm tra logs - error messages chi tiết hơn
5. Plugin version hiện tại tương thích Paper 1.21.1+
```

### 🎨 **GUI không mở - CẢI THIỆN**
```bash
NGUYÊN NHÂN:
- Inventory đầy
- Plugin conflict
- Null pointer exceptions (đã fix)

🔧 GIẢI PHÁP:
1. Clear inventory space
2. /sc reload (lệnh ngắn)
3. Plugin có better error handling - check console
4. Thử /sc info để test plugin hoạt động
5. Version hiện tại có null-safety improvements
```

### 🆕 **Placeholder Issues - MỚI**
```bash
NGUYÊN NHÂN:
- PlaceholderAPI chưa register
- Sử dụng placeholder cũ

🔧 GIẢI PHÁP:
1. Kiểm tra PlaceholderAPI đã cài
2. Dùng placeholders MỚI ngắn hơn:
   - %solarcrate_time% thay vì %solarcrate_keyalltime%
   - %sckey_default% thay vì %SCKey_default%
3. /papi reload để refresh
4. Console sẽ log "PlaceholderAPI integration enabled!"
```

### 🔧 **Version Compatibility - ĐÃ FIX**
```bash
⚠️ LỖI CŨ: Server Paper 1.21.1 nhưng plugin build cho 1.21.8
✅ ĐÃ FIX: Plugin hiện tại tương thích Paper/Spigot 1.21.1+

🔧 NẾU VẪN GẶP LỖI:
1. Đảm bảo server dùng Java 17+
2. Plugin hiện tại build với Java 17 (không phải 21)
3. Check console startup logs
4. Plugin có improved error handling
```

---

## 🏆 **Best Practices**

### 🎯 **Setup Production**
1. **Database**: Dùng MySQL cho server lớn (>50 players)
2. **Backup**: Auto-backup keys.yml hàng ngày
3. **Permissions**: Set up groups rõ ràng
4. **Monitor**: Theo dõi console logs định kỳ

### ⚡ **Performance Tips**
1. **Timer interval**: Không set <300 seconds
2. **Max keys**: Giới hạn 100 keys/player
3. **Crate size**: Không quá 45 items/crate
4. **Database**: Regular cleanup old data

### 🔒 **Security**
1. **Backup**: Định kỳ backup config files
2. **Permissions**: Chỉ admin có full permissions
3. **Commands**: Limit access cho sensitive commands
4. **Monitor**: Log all admin actions

---

## 📞 **Support & Resources**

### 📋 **Version Info**
- **Plugin**: SolarCrate v1.0.0
- **Author**: Omh  
- **Build**: Maven
- **Java**: 17+
- **MC Version**: 1.20.4+

### 🔗 **Dependencies**
- ✅ **FoliaLib 0.3.1** - Cross-platform support
- ✅ **PlaceholderAPI 2.11.5** - Placeholder integration  
- ✅ **HikariCP 5.0.1** - Database connection pooling
- ✅ **MySQL/SQLite** - Data storage

### 🆘 **Getting Help**
1. **Logs**: Check console for detailed error messages
2. **Config**: Validate YAML syntax in config files  
3. **Permissions**: Double-check permission nodes
4. **Commands**: Use `/solarcrate help` for command list

---

> **🎊 Plugin được phát triển bởi Omh - SolarCrate v1.0.0**  
> **⚡ Professional Minecraft Crate System with Timer Auto-distribution**