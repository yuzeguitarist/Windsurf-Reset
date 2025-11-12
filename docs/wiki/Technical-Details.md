# 🛠️ Technical Details

[English](#english) | [中文](#中文) | [Deutsch](#deutsch)

---

## English

### System Architecture

#### Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Framework** | Electron 28.0 | Cross-platform desktop application |
| **Frontend** | HTML5, CSS3, JavaScript | User interface |
| **Design** | Neo-Brutalism | Visual aesthetics |
| **Packaging** | electron-builder | Multi-platform builds |

---

### How It Works

#### Reset Process Flow

```
┌─────────────────────────────────────────────┐
│  1. USER INITIATES RESET                    │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  2. DETECT WINDSURF INSTALLATION            │
│     - Scan standard paths                   │
│     - Verify installation                   │
│     - Check version compatibility           │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  3. CREATE BACKUP                           │
│     - Copy current configuration            │
│     - Compress files                        │
│     - Store with timestamp                  │
│     - Verify backup integrity               │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  4. GENERATE NEW IDENTIFIERS                │
│     - Create machine ID                     │
│     - Generate session tokens               │
│     - Update configuration values           │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  5. APPLY CHANGES                           │
│     - Write new configuration               │
│     - Update relevant files                 │
│     - Clear caches                          │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  6. VERIFY & COMPLETE                       │
│     - Verify file integrity                 │
│     - Log operation                         │
│     - Show success message                  │
└─────────────────────────────────────────────┘
```

---

### File Locations

#### Windsurf Configuration Paths

**macOS:**
```
~/Library/Application Support/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

**Windows:**
```
%APPDATA%\Windsurf\
├── machineId
├── globalStorage\
│   └── storage.json
└── User\
    └── settings.json
```

**Linux:**
```
~/.config/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

#### Windsurf Reset Data Paths

**macOS:**
```
~/Library/Application Support/WindsurfReset/
├── backups/
│   ├── backup_2025-11-12_103045.wsr
│   └── backup_2025-11-10_142210.wsr
├── config.json
└── logs/
    └── app.log
```

**Windows:**
```
%APPDATA%\WindsurfReset\
├── backups\
│   ├── backup_2025-11-12_103045.wsr
│   └── backup_2025-11-10_142210.wsr
├── config.json
└── logs\
    └── app.log
```

**Linux:**
```
~/.config/WindsurfReset/
├── backups/
│   ├── backup_2025-11-12_103045.wsr
│   └── backup_2025-11-10_142210.wsr
├── config.json
└── logs/
    └── app.log
```

---

### Modified Files

#### What Gets Changed

| File/Directory | Modification | Reversible |
|----------------|--------------|------------|
| `machineId` | Regenerated | ✅ Yes (via backup) |
| `globalStorage/storage.json` | Session data cleared | ✅ Yes (via backup) |
| Cache directories | Cleared | ⚠️ Rebuilt by Windsurf |

#### What Stays Unchanged

✅ **User Projects** - All your code and files
✅ **Extensions** - Installed extensions remain
✅ **User Settings** - Most preferences preserved
✅ **Workspaces** - Workspace configurations
✅ **Keybindings** - Custom keyboard shortcuts

---

### Backup Format

#### Backup File Structure

```
backup_YYYY-MM-DD_HHMMSS.wsr (ZIP archive)
│
├── metadata.json          # Backup information
│   ├── timestamp
│   ├── windsurf_version
│   ├── app_version
│   └── checksum
│
├── machineId              # Original machine ID
├── globalStorage/         # Global storage data
└── User/                  # User configuration
```

#### Metadata Schema

```json
{
  "timestamp": "2025-11-12T10:30:45Z",
  "windsurf_version": "1.12.28",
  "app_version": "1.0.0",
  "platform": "darwin",
  "checksum": "sha256:abc123...",
  "files_backed_up": [
    "machineId",
    "globalStorage/storage.json"
  ]
}
```

---

### Security Considerations

#### Data Safety

✅ **Local Only** - All operations are local, no network calls
✅ **No Telemetry** - No data sent to external servers
✅ **Encrypted Storage** - Backups use standard zip compression
✅ **Read-Only Source** - Original files only read during backup

#### What Data is Handled

**Modified:**
- Machine identifiers (randomized strings)
- Session tokens (temporary authentication data)
- Cache files (rebuildable by Windsurf)

**Never Touched:**
- User credentials
- API keys
- Source code
- Project files
- Extension data

---

### Platform-Specific Details

#### macOS

**Requirements:**
- macOS 10.13 (High Sierra) or later
- Both ARM64 (M1/M2/M3) and Intel supported

**Code Signing:**
- Application is signed (developer ID)
- Notarized for Gatekeeper compatibility

**Permissions:**
- File system access for Windsurf directory
- No additional permissions required

---

#### Windows

**Requirements:**
- Windows 10 version 1809 or later
- x64 architecture

**Installation:**
- MSI installer or portable executable
- No administrator rights required for portable version

**Compatibility:**
- Windows Defender exclusion may be needed
- SmartScreen compatible

---

#### Linux

**Requirements:**
- Kernel 4.x or later
- GTK+ 3.0 libraries

**Formats:**
- AppImage: Universal binary
- DEB: For Debian/Ubuntu systems

**Dependencies:**
```
libgtk-3-0
libnotify4
libnss3
libxss1
libxtst6
xdg-utils
libatspi2.0-0
libappindicator3-1
libsecret-1-0
```

---

### Performance

#### Resource Usage

| Operation | CPU | Memory | Disk I/O | Duration |
|-----------|-----|--------|----------|----------|
| **Idle** | < 1% | ~80 MB | Minimal | - |
| **Detection** | 5-10% | ~90 MB | Low | < 1s |
| **Backup** | 10-20% | ~100 MB | Medium | 1-2s |
| **Reset** | 20-30% | ~120 MB | Medium | 2-3s |
| **Restore** | 15-25% | ~110 MB | Medium | 1-2s |

#### Storage Requirements

| Component | Size |
|-----------|------|
| **Application** | ~80 MB |
| **Per Backup** | ~2-3 MB |
| **Logs** | ~1-5 MB |
| **Cache** | ~5 MB |
| **Total (with 5 backups)** | ~95-100 MB |

---

### Compatibility Matrix

#### Supported Windsurf Versions

| Windsurf Version | Status | Notes |
|------------------|--------|-------|
| ≤ 1.12.28 | ✅ Fully Supported | Tested and verified |
| 1.12.29 - 1.13.x | ⚠️ Testing | May work, use caution |
| > 1.13.x | ❌ Unknown | Wait for tool update |

#### Operating System Compatibility

| OS | Version | Architecture | Status |
|----|---------|--------------|--------|
| **macOS** | 10.13+ | ARM64, x64 | ✅ Full |
| **Windows** | 10 (1809+) | x64 | ✅ Full |
| **Linux** | Kernel 4.x+ | x64 | ✅ Full |

---

### API & Integration

#### Command Line Interface

**Launch with options:**
```bash
# macOS
open /Applications/Windsurf\ Reset.app --args --reset

# Windows
Windsurf-Reset.exe --reset

# Linux
./Windsurf-Reset-*.AppImage --reset
```

**Available flags:**
```bash
--reset              # Auto-start reset on launch
--restore-latest     # Restore latest backup
--backup-only        # Create backup and exit
--windsurf-path=PATH # Custom Windsurf location
--backup-path=PATH   # Custom backup location
--debug              # Enable debug logging
--no-gpu             # Disable GPU acceleration
--help               # Show help
```

---

### Logging

#### Log Levels

| Level | Purpose | Example |
|-------|---------|---------|
| **ERROR** | Critical failures | "Failed to create backup" |
| **WARN** | Warnings | "Windsurf version not tested" |
| **INFO** | General information | "Reset completed successfully" |
| **DEBUG** | Detailed debugging | "Reading file: machineId" |

#### Log File Format

```
[2025-11-12 10:30:45.123] [INFO] Application started
[2025-11-12 10:30:45.456] [INFO] Detecting Windsurf installation
[2025-11-12 10:30:45.789] [INFO] Found Windsurf at: /Applications/Windsurf.app
[2025-11-12 10:30:46.012] [INFO] Creating backup...
[2025-11-12 10:30:47.345] [INFO] Backup created: backup_2025-11-12_103045.wsr
[2025-11-12 10:30:47.678] [INFO] Generating new identifiers...
[2025-11-12 10:30:48.901] [INFO] Reset completed successfully
```

---

### Development

#### Building from Source

**Prerequisites:**
```bash
Node.js >= 18.x
npm >= 9.x
```

**Build commands:**
```bash
# Install dependencies
npm install

# Development mode
npm run dev

# Build for current platform
npm run build

# Build for all platforms
npm run build:all

# Run tests
npm test
```

#### Project Structure

```
windsurf-reset/
├── src/
│   ├── main/           # Main process
│   ├── renderer/       # Renderer process
│   ├── shared/         # Shared utilities
│   └── resources/      # Images, icons
├── build/              # Build configuration
├── dist/               # Built applications
├── package.json
└── README.md
```

---

### Troubleshooting for Developers

#### Enable Developer Tools

**macOS/Linux:**
```bash
export WINDSURF_RESET_DEV=1
```

**Windows:**
```cmd
set WINDSURF_RESET_DEV=1
```

Then launch the application to access DevTools (F12).

#### Debug Mode

Enable in `config.json`:
```json
{
  "debug": true,
  "log_level": "DEBUG"
}
```

---

## 中文

### 系统架构

#### 技术栈

| 组件 | 技术 | 用途 |
|------|------|------|
| **框架** | Electron 28.0 | 跨平台桌面应用 |
| **前端** | HTML5, CSS3, JavaScript | 用户界面 |
| **设计** | 新粗野主义 | 视觉美学 |
| **打包** | electron-builder | 多平台构建 |

---

### 工作原理

#### 重置流程

```
┌─────────────────────────────────────────────┐
│  1. 用户发起重置                             │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  2. 检测 WINDSURF 安装                      │
│     - 扫描标准路径                           │
│     - 验证安装                               │
│     - 检查版本兼容性                         │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  3. 创建备份                                 │
│     - 复制当前配置                           │
│     - 压缩文件                               │
│     - 带时间戳存储                           │
│     - 验证备份完整性                         │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  4. 生成新标识符                             │
│     - 创建机器 ID                            │
│     - 生成会话令牌                           │
│     - 更新配置值                             │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  5. 应用更改                                 │
│     - 写入新配置                             │
│     - 更新相关文件                           │
│     - 清除缓存                               │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  6. 验证并完成                               │
│     - 验证文件完整性                         │
│     - 记录操作                               │
│     - 显示成功消息                           │
└─────────────────────────────────────────────┘
```

---

### 文件位置

#### Windsurf 配置路径

**macOS:**
```
~/Library/Application Support/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

**Windows:**
```
%APPDATA%\Windsurf\
├── machineId
├── globalStorage\
│   └── storage.json
└── User\
    └── settings.json
```

**Linux:**
```
~/.config/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

---

### 修改的文件

#### 被更改的内容

| 文件/目录 | 修改 | 可逆 |
|-----------|------|------|
| `machineId` | 重新生成 | ✅ 是 (通过备份) |
| `globalStorage/storage.json` | 会话数据清除 | ✅ 是 (通过备份) |
| 缓存目录 | 清除 | ⚠️ Windsurf 重建 |

#### 保持不变的内容

✅ **用户项目** - 所有代码和文件
✅ **扩展** - 已安装扩展保留
✅ **用户设置** - 大多数偏好设置保留
✅ **工作区** - 工作区配置
✅ **键绑定** - 自定义键盘快捷键

---

### 安全考虑

#### 数据安全

✅ **仅本地** - 所有操作都是本地的，无网络调用
✅ **无遥测** - 不向外部服务器发送数据
✅ **加密存储** - 备份使用标准 zip 压缩
✅ **只读源** - 备份期间仅读取原始文件

#### 处理的数据

**修改:**
- 机器标识符 (随机字符串)
- 会话令牌 (临时认证数据)
- 缓存文件 (Windsurf 可重建)

**从不触及:**
- 用户凭据
- API 密钥
- 源代码
- 项目文件
- 扩展数据

---

## Deutsch

### Systemarchitektur

#### Technologie-Stack

| Komponente | Technologie | Zweck |
|------------|-------------|-------|
| **Framework** | Electron 28.0 | Plattformübergreifende Desktop-Anwendung |
| **Frontend** | HTML5, CSS3, JavaScript | Benutzeroberfläche |
| **Design** | Neo-Brutalismus | Visuelle Ästhetik |
| **Packaging** | electron-builder | Multi-Plattform-Builds |

---

### Funktionsweise

#### Reset-Prozessablauf

```
┌─────────────────────────────────────────────┐
│  1. BENUTZER INITIIERT RESET                │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  2. WINDSURF-INSTALLATION ERKENNEN          │
│     - Standardpfade scannen                 │
│     - Installation überprüfen               │
│     - Versionskompatibilität prüfen         │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  3. BACKUP ERSTELLEN                        │
│     - Aktuelle Konfiguration kopieren       │
│     - Dateien komprimieren                  │
│     - Mit Zeitstempel speichern             │
│     - Backup-Integrität überprüfen          │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  4. NEUE KENNUNGEN GENERIEREN               │
│     - Maschinen-ID erstellen                │
│     - Sitzungs-Token generieren             │
│     - Konfigurationswerte aktualisieren     │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  5. ÄNDERUNGEN ANWENDEN                     │
│     - Neue Konfiguration schreiben          │
│     - Relevante Dateien aktualisieren       │
│     - Caches löschen                        │
└─────────────────┬───────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────┐
│  6. ÜBERPRÜFEN & ABSCHLIESSEN               │
│     - Dateiintegrität überprüfen            │
│     - Operation protokollieren              │
│     - Erfolgsmeldung anzeigen               │
└─────────────────────────────────────────────┘
```

---

### Dateistandorte

#### Windsurf-Konfigurationspfade

**macOS:**
```
~/Library/Application Support/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

**Windows:**
```
%APPDATA%\Windsurf\
├── machineId
├── globalStorage\
│   └── storage.json
└── User\
    └── settings.json
```

**Linux:**
```
~/.config/Windsurf/
├── machineId
├── globalStorage/
│   └── storage.json
└── User/
    └── settings.json
```

---

### Modifizierte Dateien

#### Was geändert wird

| Datei/Verzeichnis | Änderung | Umkehrbar |
|-------------------|----------|-----------|
| `machineId` | Regeneriert | ✅ Ja (via Backup) |
| `globalStorage/storage.json` | Sitzungsdaten gelöscht | ✅ Ja (via Backup) |
| Cache-Verzeichnisse | Gelöscht | ⚠️ Von Windsurf neu gebaut |

#### Was unverändert bleibt

✅ **Benutzerprojekte** - Alle Codes und Dateien
✅ **Erweiterungen** - Installierte Erweiterungen bleiben
✅ **Benutzereinstellungen** - Meiste Präferenzen erhalten
✅ **Arbeitsbereiche** - Workspace-Konfigurationen
✅ **Tastenbelegungen** - Benutzerdefinierte Tastaturkürzel

---

### Sicherheitsüberlegungen

#### Datensicherheit

✅ **Nur Lokal** - Alle Operationen sind lokal, keine Netzwerk-Aufrufe
✅ **Keine Telemetrie** - Keine Daten an externe Server gesendet
✅ **Verschlüsselte Speicherung** - Backups verwenden Standard-Zip-Komprimierung
✅ **Nur-Lese-Quelle** - Originaldateien nur während Backup gelesen

#### Verarbeitete Daten

**Modifiziert:**
- Maschinenkennungen (zufällige Strings)
- Sitzungs-Token (temporäre Authentifizierungsdaten)
- Cache-Dateien (von Windsurf neu baubar)

**Nie berührt:**
- Benutzer-Anmeldedaten
- API-Schlüssel
- Quellcode
- Projektdateien
- Erweiterungs-Daten

---

<div align="center">

[← Back to Wiki Home](Home.md)

</div>
