# 📦 Installation Guide

[English](#english) | [中文](#中文) | [Deutsch](#deutsch)

---

## English

### System Requirements

Before installing Windsurf Reset, ensure your system meets these requirements:

#### Minimum Requirements

| Component | Requirement |
|-----------|-------------|
| **RAM** | 512 MB minimum |
| **Disk Space** | 100 MB free space |
| **Display** | Any resolution supported |
| **Internet** | Not required for operation |

#### Windsurf Compatibility

- ✅ **Supported**: Windsurf version ≤ 1.12.28
- ⚠️ **Testing**: Windsurf version > 1.12.28
- 📋 **Platforms**: macOS, Windows, Linux

---

### 🍎 macOS Installation

#### Available Formats

- **`.dmg` installer** (Recommended) - Universal Binary for both ARM64 and Intel
- **`.zip` portable** - Extract and run without installation

#### Installation Steps (DMG)

1. **Download** the latest `.dmg` file from [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases)

2. **Open** the downloaded `.dmg` file

3. **Drag** the Windsurf Reset app to your Applications folder

4. **First Launch**:
   - Right-click the app and select "Open"
   - Click "Open" in the security dialog
   - This is required only for the first launch

#### Installation Steps (ZIP)

1. **Download** the `.zip` file

2. **Extract** the archive

3. **Move** the app to your preferred location

4. **Launch** the application

#### macOS Security Notes

If you see "App is damaged and can't be opened":
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

---

### 🪟 Windows Installation

#### Available Formats

- **`.exe` installer** (Recommended) - Full installation with shortcuts
- **Portable version** - Run without installation

#### Installation Steps (Installer)

1. **Download** the latest `.exe` installer from [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases)

2. **Run** the installer

3. **Follow** the installation wizard:
   - Choose installation directory
   - Select Start Menu folder
   - Choose desktop shortcut option

4. **Launch** from Start Menu or Desktop

#### Installation Steps (Portable)

1. **Download** the portable `.zip` file

2. **Extract** to your preferred location

3. **Run** `Windsurf-Reset.exe`

#### Windows Defender SmartScreen

If Windows Defender blocks the app:
1. Click "More info"
2. Click "Run anyway"
3. This is normal for new applications

---

### 🐧 Linux Installation

#### Available Formats

- **`.AppImage`** (Recommended) - Universal, works on all distributions
- **`.deb` package** - For Debian/Ubuntu-based systems

#### Installation Steps (AppImage)

1. **Download** the `.AppImage` file

2. **Make executable**:
```bash
chmod +x Windsurf-Reset-*.AppImage
```

3. **Run**:
```bash
./Windsurf-Reset-*.AppImage
```

4. **Optional**: Integrate with system:
```bash
# Install AppImageLauncher for system integration
# It will prompt to integrate on first launch
```

#### Installation Steps (DEB)

1. **Download** the `.deb` package

2. **Install** using dpkg:
```bash
sudo dpkg -i windsurf-reset_*.deb
```

3. **Fix dependencies** (if needed):
```bash
sudo apt-get install -f
```

4. **Launch** from applications menu

#### Linux Dependencies

Most distributions include required dependencies. If not:

**Debian/Ubuntu**:
```bash
sudo apt-get install libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 xdg-utils libatspi2.0-0 libappindicator3-1 libsecret-1-0
```

**Fedora/RHEL**:
```bash
sudo dnf install gtk3 libnotify nss libXScrnSaver libXtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

**Arch Linux**:
```bash
sudo pacman -S gtk3 libnotify nss libxss libxtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

---

### ✅ Post-Installation

#### Verify Installation

1. **Launch** Windsurf Reset

2. **Check** the welcome screen appears

3. **Verify** language settings (EN/中文/DE)

#### First Run Checklist

- [ ] Application launches successfully
- [ ] UI displays correctly
- [ ] Language can be changed
- [ ] Windsurf detection works

#### Updating Windsurf Reset

To update to a newer version:

1. **Download** the latest release
2. **Close** the current version
3. **Install** the new version (overwrites old)
4. **Launch** - your settings are preserved

---

### 🔧 Troubleshooting Installation

#### "Application won't open"

**macOS**: Remove quarantine attribute
```bash
xattr -cr /path/to/Windsurf\ Reset.app
```

**Windows**: Run as Administrator or disable SmartScreen temporarily

**Linux**: Ensure executable permissions and dependencies installed

#### "Installation failed"

- Check disk space (need 100 MB free)
- Ensure you have admin/sudo privileges
- Temporarily disable antivirus
- Check system architecture matches (x64/ARM64)

#### "Dependencies missing" (Linux)

Install required packages for your distribution (see Linux Dependencies above)

---

### 📞 Need More Help?

- Check the [Troubleshooting Guide](Troubleshooting.md)
- Visit the [FAQ](FAQ.md)
- [Open an issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)

---

## 中文

### 系统要求

在安装 Windsurf Reset 之前，请确保您的系统满足以下要求:

#### 最低要求

| 组件 | 要求 |
|------|------|
| **内存** | 最少 512 MB |
| **磁盘空间** | 100 MB 可用空间 |
| **显示** | 支持任意分辨率 |
| **网络** | 运行时无需联网 |

#### Windsurf 兼容性

- ✅ **已支持**: Windsurf 版本 ≤ 1.12.28
- ⚠️ **测试中**: Windsurf 版本 > 1.12.28
- 📋 **平台**: macOS、Windows、Linux

---

### 🍎 macOS 安装

#### 可用格式

- **`.dmg` 安装器** (推荐) - ARM64 和 Intel 通用二进制
- **`.zip` 便携版** - 解压即用，无需安装

#### 安装步骤 (DMG)

1. **下载** 最新的 `.dmg` 文件从 [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases)

2. **打开** 下载的 `.dmg` 文件

3. **拖动** Windsurf Reset 应用到应用程序文件夹

4. **首次启动**:
   - 右键点击应用并选择"打开"
   - 在安全对话框中点击"打开"
   - 仅首次启动需要此操作

#### 安装步骤 (ZIP)

1. **下载** `.zip` 文件

2. **解压** 压缩包

3. **移动** 应用到您喜欢的位置

4. **启动** 应用程序

#### macOS 安全提示

如果看到"应用已损坏无法打开":
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

---

### 🪟 Windows 安装

#### 可用格式

- **`.exe` 安装器** (推荐) - 完整安装并创建快捷方式
- **便携版** - 无需安装直接运行

#### 安装步骤 (安装器)

1. **下载** 最新的 `.exe` 安装器从 [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases)

2. **运行** 安装器

3. **按照** 安装向导操作:
   - 选择安装目录
   - 选择开始菜单文件夹
   - 选择桌面快捷方式选项

4. **启动** 从开始菜单或桌面

#### 安装步骤 (便携版)

1. **下载** 便携版 `.zip` 文件

2. **解压** 到您喜欢的位置

3. **运行** `Windsurf-Reset.exe`

#### Windows Defender SmartScreen

如果 Windows Defender 阻止应用:
1. 点击"更多信息"
2. 点击"仍要运行"
3. 这对新应用是正常的

---

### 🐧 Linux 安装

#### 可用格式

- **`.AppImage`** (推荐) - 通用格式，适用于所有发行版
- **`.deb` 包** - 适用于 Debian/Ubuntu 系统

#### 安装步骤 (AppImage)

1. **下载** `.AppImage` 文件

2. **设置可执行**:
```bash
chmod +x Windsurf-Reset-*.AppImage
```

3. **运行**:
```bash
./Windsurf-Reset-*.AppImage
```

4. **可选**: 集成到系统:
```bash
# 安装 AppImageLauncher 实现系统集成
# 首次启动时会提示集成
```

#### 安装步骤 (DEB)

1. **下载** `.deb` 包

2. **安装** 使用 dpkg:
```bash
sudo dpkg -i windsurf-reset_*.deb
```

3. **修复依赖** (如需要):
```bash
sudo apt-get install -f
```

4. **启动** 从应用程序菜单

#### Linux 依赖

大多数发行版包含所需依赖。如果没有:

**Debian/Ubuntu**:
```bash
sudo apt-get install libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 xdg-utils libatspi2.0-0 libappindicator3-1 libsecret-1-0
```

**Fedora/RHEL**:
```bash
sudo dnf install gtk3 libnotify nss libXScrnSaver libXtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

**Arch Linux**:
```bash
sudo pacman -S gtk3 libnotify nss libxss libxtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

---

### ✅ 安装后

#### 验证安装

1. **启动** Windsurf Reset

2. **检查** 欢迎屏幕是否出现

3. **验证** 语言设置 (中文/EN/DE)

#### 首次运行清单

- [ ] 应用成功启动
- [ ] UI 正确显示
- [ ] 可以切换语言
- [ ] Windsurf 检测功能正常

#### 更新 Windsurf Reset

要更新到新版本:

1. **下载** 最新版本
2. **关闭** 当前版本
3. **安装** 新版本 (覆盖旧版)
4. **启动** - 您的设置会保留

---

### 🔧 安装故障排除

#### "应用无法打开"

**macOS**: 移除隔离属性
```bash
xattr -cr /path/to/Windsurf\ Reset.app
```

**Windows**: 以管理员身份运行或临时禁用 SmartScreen

**Linux**: 确保可执行权限和依赖已安装

#### "安装失败"

- 检查磁盘空间 (需要 100 MB 可用)
- 确保有管理员/sudo 权限
- 临时禁用杀毒软件
- 检查系统架构匹配 (x64/ARM64)

#### "缺少依赖" (Linux)

为您的发行版安装所需包 (见上方 Linux 依赖)

---

### 📞 需要更多帮助？

- 查看 [故障排除指南](Troubleshooting.md)
- 访问 [常见问题](FAQ.md)
- [提交 Issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)

---

## Deutsch

### Systemanforderungen

Stellen Sie vor der Installation von Windsurf Reset sicher, dass Ihr System diese Anforderungen erfüllt:

#### Mindestanforderungen

| Komponente | Anforderung |
|------------|-------------|
| **RAM** | Mindestens 512 MB |
| **Festplattenspeicher** | 100 MB freier Speicher |
| **Display** | Beliebige Auflösung |
| **Internet** | Nicht erforderlich |

#### Windsurf-Kompatibilität

- ✅ **Unterstützt**: Windsurf Version ≤ 1.12.28
- ⚠️ **In Tests**: Windsurf Version > 1.12.28
- 📋 **Plattformen**: macOS, Windows, Linux

---

### 🍎 macOS Installation

#### Verfügbare Formate

- **`.dmg` Installer** (Empfohlen) - Universal Binary für ARM64 und Intel
- **`.zip` portabel** - Entpacken und ausführen ohne Installation

#### Installationsschritte (DMG)

1. **Laden Sie** die neueste `.dmg`-Datei von [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases) herunter

2. **Öffnen Sie** die heruntergeladene `.dmg`-Datei

3. **Ziehen Sie** die Windsurf Reset App in Ihren Programme-Ordner

4. **Erster Start**:
   - Rechtsklick auf die App und "Öffnen" wählen
   - Klicken Sie "Öffnen" im Sicherheitsdialog
   - Dies ist nur beim ersten Start erforderlich

#### Installationsschritte (ZIP)

1. **Laden Sie** die `.zip`-Datei herunter

2. **Entpacken Sie** das Archiv

3. **Verschieben Sie** die App an Ihren bevorzugten Ort

4. **Starten Sie** die Anwendung

#### macOS Sicherheitshinweise

Wenn Sie "App ist beschädigt und kann nicht geöffnet werden" sehen:
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

---

### 🪟 Windows Installation

#### Verfügbare Formate

- **`.exe` Installer** (Empfohlen) - Vollständige Installation mit Verknüpfungen
- **Portable Version** - Ausführen ohne Installation

#### Installationsschritte (Installer)

1. **Laden Sie** den neuesten `.exe`-Installer von [Releases](https://github.com/yuzeguitarist/Windsurf-Reset/releases) herunter

2. **Führen Sie** den Installer aus

3. **Folgen Sie** dem Installationsassistenten:
   - Wählen Sie Installationsverzeichnis
   - Wählen Sie Startmenü-Ordner
   - Wählen Sie Desktop-Verknüpfungsoption

4. **Starten Sie** aus Startmenü oder Desktop

#### Installationsschritte (Portabel)

1. **Laden Sie** die portable `.zip`-Datei herunter

2. **Entpacken Sie** an Ihren bevorzugten Ort

3. **Führen Sie** `Windsurf-Reset.exe` aus

#### Windows Defender SmartScreen

Wenn Windows Defender die App blockiert:
1. Klicken Sie "Weitere Informationen"
2. Klicken Sie "Trotzdem ausführen"
3. Dies ist normal für neue Anwendungen

---

### 🐧 Linux Installation

#### Verfügbare Formate

- **`.AppImage`** (Empfohlen) - Universal, funktioniert auf allen Distributionen
- **`.deb` Paket** - Für Debian/Ubuntu-basierte Systeme

#### Installationsschritte (AppImage)

1. **Laden Sie** die `.AppImage`-Datei herunter

2. **Machen Sie ausführbar**:
```bash
chmod +x Windsurf-Reset-*.AppImage
```

3. **Ausführen**:
```bash
./Windsurf-Reset-*.AppImage
```

4. **Optional**: In System integrieren:
```bash
# Installieren Sie AppImageLauncher für Systemintegration
# Es wird beim ersten Start zur Integration aufgefordert
```

#### Installationsschritte (DEB)

1. **Laden Sie** das `.deb`-Paket herunter

2. **Installieren Sie** mit dpkg:
```bash
sudo dpkg -i windsurf-reset_*.deb
```

3. **Abhängigkeiten beheben** (falls nötig):
```bash
sudo apt-get install -f
```

4. **Starten Sie** aus dem Anwendungsmenü

#### Linux Abhängigkeiten

Die meisten Distributionen enthalten erforderliche Abhängigkeiten. Falls nicht:

**Debian/Ubuntu**:
```bash
sudo apt-get install libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 xdg-utils libatspi2.0-0 libappindicator3-1 libsecret-1-0
```

**Fedora/RHEL**:
```bash
sudo dnf install gtk3 libnotify nss libXScrnSaver libXtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

**Arch Linux**:
```bash
sudo pacman -S gtk3 libnotify nss libxss libxtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

---

### ✅ Nach der Installation

#### Installation überprüfen

1. **Starten Sie** Windsurf Reset

2. **Prüfen Sie**, ob der Begrüßungsbildschirm erscheint

3. **Überprüfen Sie** Spracheinstellungen (DE/EN/中文)

#### Checkliste für ersten Start

- [ ] Anwendung startet erfolgreich
- [ ] UI wird korrekt angezeigt
- [ ] Sprache kann geändert werden
- [ ] Windsurf-Erkennung funktioniert

#### Windsurf Reset aktualisieren

Um auf eine neuere Version zu aktualisieren:

1. **Laden Sie** die neueste Version herunter
2. **Schließen Sie** die aktuelle Version
3. **Installieren Sie** die neue Version (überschreibt alte)
4. **Starten Sie** - Ihre Einstellungen bleiben erhalten

---

### 🔧 Installationsfehlerbehebung

#### "Anwendung öffnet sich nicht"

**macOS**: Quarantäne-Attribut entfernen
```bash
xattr -cr /path/to/Windsurf\ Reset.app
```

**Windows**: Als Administrator ausführen oder SmartScreen temporär deaktivieren

**Linux**: Stellen Sie ausführbare Berechtigungen und installierte Abhängigkeiten sicher

#### "Installation fehlgeschlagen"

- Prüfen Sie Festplattenspeicher (100 MB frei benötigt)
- Stellen Sie sicher, dass Sie Admin/Sudo-Rechte haben
- Deaktivieren Sie vorübergehend Antivirus
- Prüfen Sie System-Architektur-Übereinstimmung (x64/ARM64)

#### "Abhängigkeiten fehlen" (Linux)

Installieren Sie erforderliche Pakete für Ihre Distribution (siehe Linux Abhängigkeiten oben)

---

### 📞 Benötigen Sie weitere Hilfe?

- Siehe [Fehlerbehebungsanleitung](Troubleshooting.md)
- Besuchen Sie die [FAQ](FAQ.md)
- [Öffnen Sie ein Issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)

---

<div align="center">

[← Back to Wiki Home](Home.md)

</div>
