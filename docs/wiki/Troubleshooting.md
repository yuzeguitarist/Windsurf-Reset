# 🔧 Troubleshooting Guide

[English](#english) | [中文](#中文) | [Deutsch](#deutsch)

---

## English

### Common Issues and Solutions

---

### Installation Issues

#### Issue: Application won't install

**Symptoms:**
- Installer fails to complete
- Error messages during installation
- Installation freezes

**Solutions:**

1. **Check Disk Space**
   ```bash
   # Ensure you have at least 100 MB free
   ```

2. **Run with Admin/Sudo**
   - **Windows**: Right-click installer → "Run as Administrator"
   - **macOS**: Use sudo if needed
   - **Linux**: `sudo dpkg -i windsurf-reset_*.deb` (for .deb)

3. **Temporarily Disable Antivirus**
   - Some antivirus software blocks installation
   - Disable temporarily, install, then re-enable

4. **Check System Architecture**
   - Ensure you downloaded the correct version (x64/ARM64)

---

#### Issue: "Application is damaged" (macOS)

**Symptoms:**
- macOS says app is damaged or can't be opened
- Gatekeeper blocks the application

**Solutions:**

**Method 1: Remove Quarantine**
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

**Method 2: System Preferences**
1. Go to System Preferences → Security & Privacy
2. Click "Open Anyway" for Windsurf Reset
3. Confirm in the dialog

**Method 3: Disable Gatekeeper (temporary)**
```bash
sudo spctl --master-disable
# Install the app
sudo spctl --master-enable
```

---

#### Issue: Windows Defender SmartScreen blocks app

**Symptoms:**
- "Windows protected your PC" message
- Can't run the application

**Solutions:**

1. **Click "More info"**
2. **Click "Run anyway"**
3. **If it persists:**
   ```powershell
   # Run PowerShell as Administrator
   Unblock-File -Path "C:\path\to\Windsurf-Reset.exe"
   ```

---

#### Issue: Linux dependencies missing

**Symptoms:**
- Application won't start
- Error about missing libraries
- `ldd` shows missing dependencies

**Solutions:**

**Debian/Ubuntu:**
```bash
sudo apt-get update
sudo apt-get install libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 xdg-utils libatspi2.0-0 libappindicator3-1 libsecret-1-0
```

**Fedora/RHEL:**
```bash
sudo dnf install gtk3 libnotify nss libXScrnSaver libXtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

**Arch Linux:**
```bash
sudo pacman -S gtk3 libnotify nss libxss libxtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

---

### Detection Issues

#### Issue: Windsurf not detected

**Symptoms:**
- "Windsurf not found" message
- Application shows "No installation detected"

**Solutions:**

1. **Ensure Windsurf is Closed**
   ```bash
   # macOS/Linux
   ps aux | grep -i windsurf
   killall Windsurf

   # Windows PowerShell
   Get-Process | Where-Object {$_.Name -like "*windsurf*"} | Stop-Process
   ```

2. **Check Installation Path**

   **Default Paths:**
   - **macOS**: `/Applications/Windsurf.app`
   - **Windows**: `C:\Users\<username>\AppData\Local\Windsurf\`
   - **Linux**: `/opt/windsurf/` or `~/.local/share/windsurf/`

3. **Set Custom Path**
   - Open Settings in Windsurf Reset
   - Navigate to "Advanced" → "Custom Windsurf Path"
   - Browse to your Windsurf installation

4. **Check Permissions**
   ```bash
   # macOS/Linux: Ensure read permissions
   ls -la /path/to/windsurf

   # Fix if needed
   chmod +r /path/to/windsurf
   ```

---

#### Issue: Wrong Windsurf version detected

**Symptoms:**
- Version number is incorrect
- Compatibility warning appears

**Solutions:**

1. **Refresh Detection**
   - Click "Refresh" button
   - Restart Windsurf Reset

2. **Clear Cache**
   ```bash
   # macOS
   rm -rf ~/Library/Application\ Support/WindsurfReset/cache/

   # Windows
   rd /s %APPDATA%\WindsurfReset\cache

   # Linux
   rm -rf ~/.config/WindsurfReset/cache/
   ```

3. **Manual Version Check**
   - Open Windsurf
   - Go to Help → About
   - Note the exact version number
   - Report if mismatch persists

---

### Operation Issues

#### Issue: Reset fails/gets stuck

**Symptoms:**
- Progress bar stops moving
- Application freezes during reset
- Error message appears

**Solutions:**

1. **Don't Panic - Your Backup Exists!**
   - Backups are created BEFORE any changes
   - Your data is safe

2. **Force Quit Safely**
   ```bash
   # macOS
   killall "Windsurf Reset"

   # Windows
   taskkill /F /IM "Windsurf-Reset.exe"

   # Linux
   pkill -9 windsurf-reset
   ```

3. **Restore from Backup**
   - Restart Windsurf Reset
   - Click "Restore Backup"
   - Select most recent backup
   - Confirm restoration

4. **Check Logs**
   ```bash
   # macOS
   ~/Library/Logs/WindsurfReset/

   # Windows
   %APPDATA%\WindsurfReset\logs\

   # Linux
   ~/.config/WindsurfReset/logs/
   ```

5. **Report Issue**
   - Include log files
   - Describe what happened
   - [Open an issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)

---

#### Issue: Backup creation fails

**Symptoms:**
- "Failed to create backup" error
- Reset won't start

**Solutions:**

1. **Check Disk Space**
   ```bash
   # Need at least 10 MB free
   df -h  # macOS/Linux
   ```

2. **Check Permissions**
   ```bash
   # macOS/Linux
   ls -la ~/Library/Application\ Support/WindsurfReset/backups/

   # Fix permissions
   chmod -R u+w ~/Library/Application\ Support/WindsurfReset/
   ```

3. **Change Backup Location**
   - Settings → Backup Management
   - Click "Change Backup Location"
   - Select a directory with sufficient space

4. **Clear Old Backups**
   - Settings → Backup Management
   - Delete old unnecessary backups
   - Keep at least one recent backup

---

#### Issue: Restore fails

**Symptoms:**
- "Failed to restore backup" error
- Restoration doesn't complete

**Solutions:**

1. **Verify Backup Integrity**
   - Open backup folder
   - Check backup file size (should be ~2-3 MB)
   - Try a different backup

2. **Ensure Windsurf is Closed**
   ```bash
   # Kill all Windsurf processes
   # See "Ensure Windsurf is Closed" section above
   ```

3. **Manual Restoration**
   ```bash
   # macOS
   cd ~/Library/Application\ Support/WindsurfReset/backups/
   # Copy files manually to Windsurf config directory

   # Windows
   cd %APPDATA%\WindsurfReset\backups\
   # Copy to Windsurf config directory

   # Linux
   cd ~/.config/WindsurfReset/backups/
   # Copy to Windsurf config directory
   ```

---

### UI/Display Issues

#### Issue: Application window is blank/black

**Symptoms:**
- Window opens but shows nothing
- Black or white screen

**Solutions:**

1. **Graphics Acceleration Issue**
   ```bash
   # Launch with software rendering
   # macOS
   open /Applications/Windsurf\ Reset.app --args --disable-gpu

   # Linux
   ./Windsurf-Reset-*.AppImage --disable-gpu

   # Windows
   "Windsurf-Reset.exe" --disable-gpu
   ```

2. **Update Graphics Drivers**
   - Check for driver updates
   - Restart after updating

3. **Clear Application Data**
   ```bash
   # macOS
   rm -rf ~/Library/Application\ Support/WindsurfReset/

   # Windows
   rd /s %APPDATA%\WindsurfReset

   # Linux
   rm -rf ~/.config/WindsurfReset/
   ```
   ⚠️ **Warning**: This deletes backups! Export them first if important.

---

#### Issue: Text is unreadable/garbled

**Symptoms:**
- Characters display incorrectly
- Font issues

**Solutions:**

1. **Check System Fonts**
   - Ensure system fonts are installed correctly

2. **Change Language**
   - Try switching to a different language
   - Settings → Language

3. **Reinstall Application**

---

### Performance Issues

#### Issue: Application is slow/laggy

**Symptoms:**
- UI responds slowly
- Operations take too long
- High CPU usage

**Solutions:**

1. **Close Other Applications**
   - Free up system resources
   - Especially close resource-heavy apps

2. **Check System Resources**
   ```bash
   # macOS/Linux
   top

   # Windows
   taskmgr
   ```

3. **Clear Logs**
   ```bash
   # Delete old log files
   # See log locations in "Check Logs" section
   ```

4. **Reinstall with Clean Install**
   - Completely uninstall
   - Delete application data
   - Fresh installation

---

### Data/Backup Issues

#### Issue: Can't find backups

**Symptoms:**
- Backup list is empty
- "No backups found" message

**Solutions:**

1. **Check Backup Location**

   **Default locations:**
   ```bash
   # macOS
   ~/Library/Application Support/WindsurfReset/backups/

   # Windows
   %APPDATA%\WindsurfReset\backups\

   # Linux
   ~/.config/WindsurfReset/backups/
   ```

2. **Check Custom Location**
   - Settings → Backup Management
   - Verify the configured backup path

3. **Restore Custom Location**
   - If you changed it and forgot
   - Check your common directories
   - Use system search for `.wsr_backup` files

---

#### Issue: Backup file is corrupted

**Symptoms:**
- Can't restore a specific backup
- "Backup corrupted" error

**Solutions:**

1. **Try Another Backup**
   - Use a different backup if available

2. **Check File Size**
   ```bash
   # Backup should be around 2-3 MB
   ls -lh /path/to/backup/
   ```

3. **Extract Manually** (Advanced)
   ```bash
   # Backups are compressed archives
   # Extract and inspect contents
   unzip backup_file.wsr_backup
   ```

---

### Advanced Troubleshooting

#### Enable Debug Mode

For detailed logging:

1. **Settings** → **Advanced** → **Debug Mode**
2. **Enable Debug Logging**
3. **Reproduce the issue**
4. **Check logs:**
   ```bash
   # macOS
   tail -f ~/Library/Logs/WindsurfReset/debug.log

   # Windows
   type %APPDATA%\WindsurfReset\logs\debug.log

   # Linux
   tail -f ~/.config/WindsurfReset/logs/debug.log
   ```

---

#### Reset Application Settings

If nothing else works:

```bash
# Complete reset of Windsurf Reset (NOT Windsurf IDE)

# macOS
rm -rf ~/Library/Application\ Support/WindsurfReset/
rm -rf ~/Library/Preferences/com.yuzepan.windsurfreset.plist

# Windows
rd /s /q "%APPDATA%\WindsurfReset"
rd /s /q "%LOCALAPPDATA%\WindsurfReset"

# Linux
rm -rf ~/.config/WindsurfReset/
```

⚠️ **Warning**: This deletes all backups and settings!

---

### Getting Help

If none of these solutions work:

1. **Collect Information:**
   - Operating System and version
   - Windsurf version
   - Windsurf Reset version
   - Error messages (screenshots)
   - Log files

2. **Check Existing Issues:**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - Search for similar problems

3. **Open a New Issue:**
   - Provide all collected information
   - Describe steps to reproduce
   - Include relevant log files

4. **Community Resources:**
   - Check the [FAQ](FAQ.md)
   - Read the [User Guide](User-Guide.md)

---

## 中文

### 常见问题及解决方案

---

### 安装问题

#### 问题: 应用程序无法安装

**症状:**
- 安装程序无法完成
- 安装过程中出现错误消息
- 安装冻结

**解决方案:**

1. **检查磁盘空间**
   ```bash
   # 确保至少有 100 MB 可用空间
   ```

2. **以管理员身份运行**
   - **Windows**: 右键安装程序 → "以管理员身份运行"
   - **macOS**: 必要时使用 sudo
   - **Linux**: `sudo dpkg -i windsurf-reset_*.deb` (对于 .deb)

3. **临时禁用杀毒软件**
   - 某些杀毒软件会阻止安装
   - 临时禁用，安装，然后重新启用

4. **检查系统架构**
   - 确保下载了正确的版本 (x64/ARM64)

---

#### 问题: "应用程序已损坏" (macOS)

**症状:**
- macOS 提示应用已损坏或无法打开
- Gatekeeper 阻止应用程序

**解决方案:**

**方法 1: 移除隔离**
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

**方法 2: 系统偏好设置**
1. 进入系统偏好设置 → 安全性与隐私
2. 为 Windsurf Reset 点击"仍要打开"
3. 在对话框中确认

**方法 3: 禁用 Gatekeeper (临时)**
```bash
sudo spctl --master-disable
# 安装应用
sudo spctl --master-enable
```

---

#### 问题: Windows Defender SmartScreen 阻止应用

**症状:**
- "Windows 已保护你的电脑" 消息
- 无法运行应用程序

**解决方案:**

1. **点击"更多信息"**
2. **点击"仍要运行"**
3. **如果仍然存在:**
   ```powershell
   # 以管理员身份运行 PowerShell
   Unblock-File -Path "C:\path\to\Windsurf-Reset.exe"
   ```

---

#### 问题: Linux 缺少依赖

**症状:**
- 应用程序无法启动
- 关于缺少库的错误
- `ldd` 显示缺少依赖

**解决方案:**

**Debian/Ubuntu:**
```bash
sudo apt-get update
sudo apt-get install libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 xdg-utils libatspi2.0-0 libappindicator3-1 libsecret-1-0
```

**Fedora/RHEL:**
```bash
sudo dnf install gtk3 libnotify nss libXScrnSaver libXtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

**Arch Linux:**
```bash
sudo pacman -S gtk3 libnotify nss libxss libxtst xdg-utils at-spi2-core libappindicator-gtk3 libsecret
```

---

### 检测问题

#### 问题: 未检测到 Windsurf

**症状:**
- "未找到 Windsurf" 消息
- 应用显示"未检测到安装"

**解决方案:**

1. **确保 Windsurf 已关闭**
   ```bash
   # macOS/Linux
   ps aux | grep -i windsurf
   killall Windsurf

   # Windows PowerShell
   Get-Process | Where-Object {$_.Name -like "*windsurf*"} | Stop-Process
   ```

2. **检查安装路径**

   **默认路径:**
   - **macOS**: `/Applications/Windsurf.app`
   - **Windows**: `C:\Users\<username>\AppData\Local\Windsurf\`
   - **Linux**: `/opt/windsurf/` 或 `~/.local/share/windsurf/`

3. **设置自定义路径**
   - 在 Windsurf Reset 中打开设置
   - 导航到"高级" → "自定义 Windsurf 路径"
   - 浏览到您的 Windsurf 安装位置

4. **检查权限**
   ```bash
   # macOS/Linux: 确保读取权限
   ls -la /path/to/windsurf

   # 必要时修复
   chmod +r /path/to/windsurf
   ```

---

### 操作问题

#### 问题: 重置失败/卡住

**症状:**
- 进度条停止移动
- 应用在重置期间冻结
- 出现错误消息

**解决方案:**

1. **不要惊慌 - 您的备份存在！**
   - 备份在任何更改之前创建
   - 您的数据是安全的

2. **安全强制退出**
   ```bash
   # macOS
   killall "Windsurf Reset"

   # Windows
   taskkill /F /IM "Windsurf-Reset.exe"

   # Linux
   pkill -9 windsurf-reset
   ```

3. **从备份恢复**
   - 重启 Windsurf Reset
   - 点击"恢复备份"
   - 选择最近的备份
   - 确认恢复

4. **检查日志**
   ```bash
   # macOS
   ~/Library/Logs/WindsurfReset/

   # Windows
   %APPDATA%\WindsurfReset\logs\

   # Linux
   ~/.config/WindsurfReset/logs/
   ```

5. **报告问题**
   - 包含日志文件
   - 描述发生了什么
   - [提交 issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)

---

### 性能问题

#### 问题: 应用程序缓慢/卡顿

**症状:**
- UI 响应缓慢
- 操作耗时过长
- CPU 使用率高

**解决方案:**

1. **关闭其他应用程序**
   - 释放系统资源
   - 特别是关闭资源密集型应用

2. **检查系统资源**
   ```bash
   # macOS/Linux
   top

   # Windows
   taskmgr
   ```

3. **清除日志**
   ```bash
   # 删除旧日志文件
   # 参见"检查日志"部分的日志位置
   ```

4. **全新安装**
   - 完全卸载
   - 删除应用数据
   - 全新安装

---

### 获取帮助

如果这些解决方案都不起作用:

1. **收集信息:**
   - 操作系统和版本
   - Windsurf 版本
   - Windsurf Reset 版本
   - 错误消息 (截图)
   - 日志文件

2. **检查现有 Issues:**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - 搜索类似问题

3. **提交新 Issue:**
   - 提供所有收集的信息
   - 描述重现步骤
   - 包含相关日志文件

---

## Deutsch

### Häufige Probleme und Lösungen

---

### Installationsprobleme

#### Problem: Anwendung lässt sich nicht installieren

**Symptome:**
- Installer schließt nicht ab
- Fehlermeldungen während der Installation
- Installation friert ein

**Lösungen:**

1. **Festplattenspeicher prüfen**
   ```bash
   # Mindestens 100 MB frei benötigt
   ```

2. **Mit Admin/Sudo ausführen**
   - **Windows**: Rechtsklick Installer → "Als Administrator ausführen"
   - **macOS**: Bei Bedarf sudo verwenden
   - **Linux**: `sudo dpkg -i windsurf-reset_*.deb` (für .deb)

3. **Antivirus temporär deaktivieren**
   - Einige Antivirus-Software blockiert Installation
   - Temporär deaktivieren, installieren, dann wieder aktivieren

4. **Systemarchitektur prüfen**
   - Stellen Sie sicher, dass Sie die richtige Version heruntergeladen haben (x64/ARM64)

---

#### Problem: "Anwendung ist beschädigt" (macOS)

**Symptome:**
- macOS sagt, App ist beschädigt oder kann nicht geöffnet werden
- Gatekeeper blockiert die Anwendung

**Lösungen:**

**Methode 1: Quarantäne entfernen**
```bash
xattr -cr /Applications/Windsurf\ Reset.app
```

**Methode 2: Systemeinstellungen**
1. Gehen Sie zu Systemeinstellungen → Sicherheit & Datenschutz
2. Klicken Sie "Trotzdem öffnen" für Windsurf Reset
3. Bestätigen Sie im Dialog

**Methode 3: Gatekeeper deaktivieren (temporär)**
```bash
sudo spctl --master-disable
# App installieren
sudo spctl --master-enable
```

---

### Erkennungsprobleme

#### Problem: Windsurf nicht erkannt

**Symptome:**
- "Windsurf nicht gefunden" Nachricht
- Anwendung zeigt "Keine Installation erkannt"

**Lösungen:**

1. **Sicherstellen, dass Windsurf geschlossen ist**
   ```bash
   # macOS/Linux
   ps aux | grep -i windsurf
   killall Windsurf

   # Windows PowerShell
   Get-Process | Where-Object {$_.Name -like "*windsurf*"} | Stop-Process
   ```

2. **Installationspfad prüfen**

   **Standardpfade:**
   - **macOS**: `/Applications/Windsurf.app`
   - **Windows**: `C:\Users\<username>\AppData\Local\Windsurf\`
   - **Linux**: `/opt/windsurf/` oder `~/.local/share/windsurf/`

3. **Benutzerdefinierten Pfad festlegen**
   - Einstellungen in Windsurf Reset öffnen
   - Navigieren zu "Erweitert" → "Benutzerdefinierter Windsurf-Pfad"
   - Zu Ihrer Windsurf-Installation navigieren

---

### Operationsprobleme

#### Problem: Reset schlägt fehl/bleibt hängen

**Symptome:**
- Fortschrittsbalken stoppt
- Anwendung friert während Reset ein
- Fehlermeldung erscheint

**Lösungen:**

1. **Keine Panik - Ihr Backup existiert!**
   - Backups werden VOR allen Änderungen erstellt
   - Ihre Daten sind sicher

2. **Sicher beenden erzwingen**
   ```bash
   # macOS
   killall "Windsurf Reset"

   # Windows
   taskkill /F /IM "Windsurf-Reset.exe"

   # Linux
   pkill -9 windsurf-reset
   ```

3. **Aus Backup wiederherstellen**
   - Windsurf Reset neu starten
   - "Backup wiederherstellen" klicken
   - Neuestes Backup auswählen
   - Wiederherstellung bestätigen

---

### Hilfe erhalten

Wenn keine dieser Lösungen funktioniert:

1. **Informationen sammeln:**
   - Betriebssystem und Version
   - Windsurf-Version
   - Windsurf Reset-Version
   - Fehlermeldungen (Screenshots)
   - Log-Dateien

2. **Bestehende Issues prüfen:**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - Nach ähnlichen Problemen suchen

3. **Neues Issue öffnen:**
   - Alle gesammelten Informationen bereitstellen
   - Schritte zur Reproduktion beschreiben
   - Relevante Log-Dateien einschließen

---

<div align="center">

[← Back to Wiki Home](Home.md)

</div>
