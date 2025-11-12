# 💬 Frequently Asked Questions (FAQ)

[English](#english) | [中文](#中文) | [Deutsch](#deutsch)

---

## English

### General Questions

<details>
<summary><b>What is Windsurf Reset?</b></summary>
<br>

Windsurf Reset is a utility tool that allows you to refresh your Windsurf IDE machine identifiers with a single click. It creates automatic backups and allows you to restore previous configurations if needed.

**Key Features:**
- One-click reset operation
- Automatic backup system
- Cross-platform support (Windows, macOS, Linux)
- Multi-language interface (EN/中文/DE)

</details>

<details>
<summary><b>Is Windsurf Reset safe to use?</b></summary>
<br>

Yes! Windsurf Reset is designed with safety in mind:

✅ **Automatic Backups**: Creates backups before every operation
✅ **Reversible Operations**: All changes can be undone
✅ **No Data Loss**: Your project files remain untouched
✅ **Tested**: Thoroughly tested on multiple platforms

The tool only modifies Windsurf configuration files, not your actual project data.

</details>

<details>
<summary><b>What does the reset actually do?</b></summary>
<br>

The reset operation:

1. **Creates a backup** of your current Windsurf configuration
2. **Regenerates machine identifiers** used by Windsurf
3. **Updates configuration files** with new identifiers
4. **Verifies** the changes were applied correctly

Your project files, extensions, and most settings remain unchanged.

</details>

<details>
<summary><b>Will I lose my projects or files?</b></summary>
<br>

**No!** Windsurf Reset only modifies IDE configuration files. Your projects, code files, and workspaces are completely safe and will not be affected.

</details>

---

### Compatibility

<details>
<summary><b>Which Windsurf versions are supported?</b></summary>
<br>

**Fully Supported:**
- Windsurf version ≤ 1.12.28

**Under Testing:**
- Windsurf version > 1.12.28

**Recommendation:** Always check the [releases page](https://github.com/yuzeguitarist/Windsurf-Reset/releases) for the latest compatibility information.

</details>

<details>
<summary><b>Does it work on my operating system?</b></summary>
<br>

Windsurf Reset supports all major platforms:

| Platform | Support | Formats |
|----------|---------|---------|
| **macOS** | ✅ Full | .dmg, .zip |
| **Windows** | ✅ Full | .exe, portable |
| **Linux** | ✅ Full | .AppImage, .deb |

**Architectures:**
- macOS: ARM64 (M1/M2/M3) and Intel (x64)
- Windows: x64
- Linux: x64

</details>

<details>
<summary><b>Can I use it with the latest Windsurf version?</b></summary>
<br>

Tested and confirmed working with Windsurf version 1.12.28 and below. For newer versions:

1. Check the [releases page](https://github.com/yuzeguitarist/Windsurf-Reset/releases) for updates
2. Look for compatibility notes
3. Consider waiting for an updated version if uncertain
4. Always create a backup first

</details>

---

### Usage Questions

<details>
<summary><b>How often should I use the reset tool?</b></summary>
<br>

**Recommended Usage:**

- ⚠️ **As needed only** - Don't reset unnecessarily
- ✅ **Before starting new major projects**
- ✅ **When experiencing IDE issues**
- ✅ **After major Windsurf updates**

**Not Recommended:**
- ❌ Daily resets
- ❌ Multiple resets in a short period
- ❌ During active project development

</details>

<details>
<summary><b>What should I do before resetting?</b></summary>
<br>

**Pre-Reset Checklist:**

```
□ Save all open files
□ Close all Windsurf windows
□ Note down custom settings
□ Ensure no Windsurf processes running
□ Verify sufficient disk space (100 MB)
```

**Optional but Recommended:**
- Export workspace settings
- List installed extensions
- Document custom configurations

</details>

<details>
<summary><b>How long does a reset take?</b></summary>
<br>

**Typical Timeline:**

| Operation | Duration |
|-----------|----------|
| Detection | < 1 second |
| Backup Creation | 1-2 seconds |
| Identifier Generation | 2-3 seconds |
| Configuration Update | 1-2 seconds |
| Verification | < 1 second |
| **Total** | **5-10 seconds** |

Actual time may vary based on system performance.

</details>

<details>
<summary><b>Can I undo a reset?</b></summary>
<br>

**Yes!** You can restore any previous backup:

1. Close Windsurf
2. Open Windsurf Reset
3. Click "Restore Backup"
4. Select the backup you want to restore
5. Confirm restoration
6. Restart Windsurf

All backups include timestamp and version information to help you choose the right one.

</details>

---

### Licensing

<details>
<summary><b>Can I use Windsurf Reset for free?</b></summary>
<br>

**Yes!** Windsurf Reset is free for personal use.

**Permitted:**
- ✅ Personal use
- ✅ Educational use
- ✅ Non-profit use
- ✅ Closed-source projects

**Prohibited:**
- ❌ Commercial use
- ❌ Selling the software
- ❌ Removing attribution

See the [License](License-Details.md) for complete terms.

</details>

<details>
<summary><b>Can I use it in my company?</b></summary>
<br>

**Commercial use is prohibited** under the current license.

For commercial licensing:
1. [Open an issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
2. Describe your use case
3. We'll discuss licensing options

</details>

<details>
<summary><b>Can I modify the source code?</b></summary>
<br>

**Modifications are allowed** but must be open-sourced:

**Requirements:**
- ✅ Must release modifications as open-source
- ✅ Must use the same license
- ✅ Must maintain attribution
- ✅ Must include clear documentation

**Note:** The distributed version is obfuscated for security reasons.

</details>

---

### Technical Questions

<details>
<summary><b>Where are backups stored?</b></summary>
<br>

**Default Backup Locations:**

**macOS:**
```
~/Library/Application Support/WindsurfReset/backups/
```

**Windows:**
```
%APPDATA%\WindsurfReset\backups\
```

**Linux:**
```
~/.config/WindsurfReset/backups/
```

You can change this location in Settings → Backup Management.

</details>

<details>
<summary><b>How much disk space do I need?</b></summary>
<br>

**Space Requirements:**

| Component | Size |
|-----------|------|
| Application | ~80 MB |
| Per Backup | ~2-3 MB |
| Recommended Free | 100+ MB |

**Example:** With 5 backups, you need ~100 MB total.

</details>

<details>
<summary><b>Does it require internet connection?</b></summary>
<br>

**No!** Windsurf Reset works completely offline.

**Internet only needed for:**
- Downloading the initial installation
- Checking for updates (optional)
- Accessing online documentation

All core functionality works without internet.

</details>

<details>
<summary><b>What files does it modify?</b></summary>
<br>

Windsurf Reset only modifies Windsurf IDE configuration files:

**Modified:**
- Machine identifier files
- Configuration cache
- Session storage

**NOT Modified:**
- Your project files
- Code repositories
- User data
- Installed extensions (structure)

</details>

---

### Troubleshooting

<details>
<summary><b>The application won't open. What should I do?</b></summary>
<br>

**Try these solutions:**

**macOS:**
```bash
# Remove quarantine attribute
xattr -cr /Applications/Windsurf\ Reset.app
```

**Windows:**
- Right-click → Run as Administrator
- Check Windows Defender/Antivirus
- Temporarily disable SmartScreen

**Linux:**
```bash
# Ensure executable permissions
chmod +x Windsurf-Reset-*.AppImage

# Check dependencies
ldd Windsurf-Reset-*.AppImage
```

See [Troubleshooting Guide](Troubleshooting.md) for more solutions.

</details>

<details>
<summary><b>Windsurf isn't detected. What's wrong?</b></summary>
<br>

**Common causes and solutions:**

1. **Non-standard installation location**
   - Solution: Set custom path in Settings

2. **Windsurf is running**
   - Solution: Close all Windsurf windows and processes

3. **Permissions issue**
   - Solution: Run with appropriate permissions

4. **Unsupported version**
   - Solution: Check compatibility, update tool or Windsurf

See detailed solutions in [Troubleshooting](Troubleshooting.md).

</details>

<details>
<summary><b>Reset failed halfway. What now?</b></summary>
<br>

**Don't panic!** Your backup is safe.

**Recovery steps:**

1. **Close Windsurf Reset**
2. **Reopen the application**
3. **Click "Restore Backup"**
4. **Select the most recent backup**
5. **Confirm restoration**

Your Windsurf will be back to its previous state.

If problems persist, see [Troubleshooting](Troubleshooting.md) or [open an issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues).

</details>

<details>
<summary><b>Where can I get help?</b></summary>
<br>

**Support Resources:**

1. **Documentation**
   - [User Guide](User-Guide.md)
   - [Troubleshooting](Troubleshooting.md)
   - [Technical Details](Technical-Details.md)

2. **Community Support**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - Check existing issues first
   - Provide detailed information when creating new issues

3. **This FAQ**
   - Browse all questions above
   - Use Ctrl+F to search

</details>

---

## 中文

### 常规问题

<details>
<summary><b>什么是 Windsurf Reset？</b></summary>
<br>

Windsurf Reset 是一个实用工具，允许您一键刷新 Windsurf IDE 的机器标识符。它会创建自动备份，并允许您在需要时恢复之前的配置。

**主要功能:**
- 一键重置操作
- 自动备份系统
- 跨平台支持 (Windows, macOS, Linux)
- 多语言界面 (中文/EN/DE)

</details>

<details>
<summary><b>使用 Windsurf Reset 安全吗？</b></summary>
<br>

安全！Windsurf Reset 在设计时考虑了安全性:

✅ **自动备份**: 每次操作前创建备份
✅ **可逆操作**: 所有更改都可以撤销
✅ **无数据丢失**: 您的项目文件保持不变
✅ **经过测试**: 在多个平台上经过充分测试

该工具只修改 Windsurf 配置文件，不触及您的实际项目数据。

</details>

<details>
<summary><b>重置实际上做了什么？</b></summary>
<br>

重置操作:

1. **创建备份** 您当前的 Windsurf 配置
2. **重新生成机器标识符** Windsurf 使用的标识符
3. **更新配置文件** 使用新标识符
4. **验证** 更改已正确应用

您的项目文件、扩展和大多数设置保持不变。

</details>

<details>
<summary><b>我会丢失项目或文件吗？</b></summary>
<br>

**不会！** Windsurf Reset 只修改 IDE 配置文件。您的项目、代码文件和工作区完全安全，不会受到影响。

</details>

---

### 兼容性

<details>
<summary><b>支持哪些 Windsurf 版本？</b></summary>
<br>

**完全支持:**
- Windsurf 版本 ≤ 1.12.28

**测试中:**
- Windsurf 版本 > 1.12.28

**建议:** 始终查看 [releases 页面](https://github.com/yuzeguitarist/Windsurf-Reset/releases) 获取最新兼容性信息。

</details>

<details>
<summary><b>它在我的操作系统上工作吗？</b></summary>
<br>

Windsurf Reset 支持所有主流平台:

| 平台 | 支持 | 格式 |
|------|------|------|
| **macOS** | ✅ 完全 | .dmg, .zip |
| **Windows** | ✅ 完全 | .exe, 便携版 |
| **Linux** | ✅ 完全 | .AppImage, .deb |

**架构:**
- macOS: ARM64 (M1/M2/M3) 和 Intel (x64)
- Windows: x64
- Linux: x64

</details>

<details>
<summary><b>可以与最新版本的 Windsurf 一起使用吗？</b></summary>
<br>

已测试并确认支持 Windsurf 版本 1.12.28 及以下。对于更新版本:

1. 查看 [releases 页面](https://github.com/yuzeguitarist/Windsurf-Reset/releases) 获取更新
2. 查找兼容性说明
3. 如果不确定，考虑等待更新版本
4. 始终先创建备份

</details>

---

### 使用问题

<details>
<summary><b>我应该多久使用一次重置工具？</b></summary>
<br>

**推荐使用:**

- ⚠️ **仅在需要时** - 不要不必要地重置
- ✅ **开始新的主要项目前**
- ✅ **遇到 IDE 问题时**
- ✅ **Windsurf 重大更新后**

**不推荐:**
- ❌ 每天重置
- ❌ 短时间内多次重置
- ❌ 在活跃项目开发期间

</details>

<details>
<summary><b>重置前应该做什么？</b></summary>
<br>

**重置前检查清单:**

```
□ 保存所有打开的文件
□ 关闭所有 Windsurf 窗口
□ 记录自定义设置
□ 确保没有 Windsurf 进程在运行
□ 验证足够的磁盘空间 (100 MB)
```

**可选但推荐:**
- 导出工作区设置
- 列出已安装扩展
- 记录自定义配置

</details>

<details>
<summary><b>重置需要多长时间？</b></summary>
<br>

**典型时间线:**

| 操作 | 持续时间 |
|------|---------|
| 检测 | < 1秒 |
| 创建备份 | 1-2秒 |
| 生成标识符 | 2-3秒 |
| 更新配置 | 1-2秒 |
| 验证 | < 1秒 |
| **总计** | **5-10秒** |

实际时间可能因系统性能而异。

</details>

<details>
<summary><b>我可以撤销重置吗？</b></summary>
<br>

**可以！** 您可以恢复任何之前的备份:

1. 关闭 Windsurf
2. 打开 Windsurf Reset
3. 点击"恢复备份"
4. 选择要恢复的备份
5. 确认恢复
6. 重启 Windsurf

所有备份都包含时间戳和版本信息，帮助您选择正确的备份。

</details>

---

### 许可

<details>
<summary><b>我可以免费使用 Windsurf Reset 吗？</b></summary>
<br>

**可以！** Windsurf Reset 个人使用免费。

**允许:**
- ✅ 个人使用
- ✅ 教育使用
- ✅ 非营利使用
- ✅ 闭源项目

**禁止:**
- ❌ 商业使用
- ❌ 销售软件
- ❌ 删除署名

查看 [许可证](License-Details.md) 了解完整条款。

</details>

<details>
<summary><b>我可以在公司使用吗？</b></summary>
<br>

**当前许可禁止商业使用**。

获取商业许可:
1. [提交 issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
2. 描述您的使用场景
3. 我们将讨论许可选项

</details>

<details>
<summary><b>我可以修改源代码吗？</b></summary>
<br>

**允许修改** 但必须开源:

**要求:**
- ✅ 必须以开源方式发布修改
- ✅ 必须使用相同许可
- ✅ 必须保留署名
- ✅ 必须包含清晰文档

**注意:** 分发版本出于安全原因已混淆。

</details>

---

### 技术问题

<details>
<summary><b>备份存储在哪里？</b></summary>
<br>

**默认备份位置:**

**macOS:**
```
~/Library/Application Support/WindsurfReset/backups/
```

**Windows:**
```
%APPDATA%\WindsurfReset\backups\
```

**Linux:**
```
~/.config/WindsurfReset/backups/
```

您可以在 设置 → 备份管理 中更改此位置。

</details>

<details>
<summary><b>我需要多少磁盘空间？</b></summary>
<br>

**空间要求:**

| 组件 | 大小 |
|------|------|
| 应用程序 | ~80 MB |
| 每个备份 | ~2-3 MB |
| 推荐可用空间 | 100+ MB |

**示例:** 包含 5 个备份，您总共需要 ~100 MB。

</details>

<details>
<summary><b>需要互联网连接吗？</b></summary>
<br>

**不需要！** Windsurf Reset 完全离线工作。

**仅需要互联网:**
- 下载初始安装
- 检查更新 (可选)
- 访问在线文档

所有核心功能无需互联网即可工作。

</details>

<details>
<summary><b>它修改哪些文件？</b></summary>
<br>

Windsurf Reset 只修改 Windsurf IDE 配置文件:

**修改:**
- 机器标识符文件
- 配置缓存
- 会话存储

**不修改:**
- 您的项目文件
- 代码仓库
- 用户数据
- 已安装扩展 (结构)

</details>

---

### 故障排除

<details>
<summary><b>应用程序无法打开。我该怎么办？</b></summary>
<br>

**尝试这些解决方案:**

**macOS:**
```bash
# 移除隔离属性
xattr -cr /Applications/Windsurf\ Reset.app
```

**Windows:**
- 右键 → 以管理员身份运行
- 检查 Windows Defender/杀毒软件
- 临时禁用 SmartScreen

**Linux:**
```bash
# 确保可执行权限
chmod +x Windsurf-Reset-*.AppImage

# 检查依赖
ldd Windsurf-Reset-*.AppImage
```

查看 [故障排除指南](Troubleshooting.md) 获取更多解决方案。

</details>

<details>
<summary><b>未检测到 Windsurf。怎么回事？</b></summary>
<br>

**常见原因和解决方案:**

1. **非标准安装位置**
   - 解决方案: 在设置中设置自定义路径

2. **Windsurf 正在运行**
   - 解决方案: 关闭所有 Windsurf 窗口和进程

3. **权限问题**
   - 解决方案: 以适当权限运行

4. **不支持的版本**
   - 解决方案: 检查兼容性，更新工具或 Windsurf

查看 [故障排除](Troubleshooting.md) 中的详细解决方案。

</details>

<details>
<summary><b>重置中途失败。现在怎么办？</b></summary>
<br>

**不要惊慌！** 您的备份是安全的。

**恢复步骤:**

1. **关闭 Windsurf Reset**
2. **重新打开应用程序**
3. **点击"恢复备份"**
4. **选择最近的备份**
5. **确认恢复**

您的 Windsurf 将恢复到之前的状态。

如果问题持续，查看 [故障排除](Troubleshooting.md) 或 [提交 issue](https://github.com/yuzeguitarist/Windsurf-Reset/issues)。

</details>

<details>
<summary><b>我在哪里可以获得帮助？</b></summary>
<br>

**支持资源:**

1. **文档**
   - [用户指南](User-Guide.md)
   - [故障排除](Troubleshooting.md)
   - [技术细节](Technical-Details.md)

2. **社区支持**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - 首先检查现有 issues
   - 创建新 issue 时提供详细信息

3. **本 FAQ**
   - 浏览上面所有问题
   - 使用 Ctrl+F 搜索

</details>

---

## Deutsch

### Allgemeine Fragen

<details>
<summary><b>Was ist Windsurf Reset?</b></summary>
<br>

Windsurf Reset ist ein Dienstprogramm, mit dem Sie die Maschinenkennungen Ihrer Windsurf IDE mit einem Klick aktualisieren können. Es erstellt automatische Backups und ermöglicht es Ihnen, bei Bedarf frühere Konfigurationen wiederherzustellen.

**Hauptfunktionen:**
- Ein-Klick-Reset-Operation
- Automatisches Backup-System
- Plattformübergreifende Unterstützung (Windows, macOS, Linux)
- Mehrsprachige Oberfläche (DE/EN/中文)

</details>

<details>
<summary><b>Ist Windsurf Reset sicher zu verwenden?</b></summary>
<br>

Ja! Windsurf Reset wurde mit Blick auf Sicherheit entwickelt:

✅ **Automatische Backups**: Erstellt Backups vor jeder Operation
✅ **Umkehrbare Operationen**: Alle Änderungen können rückgängig gemacht werden
✅ **Kein Datenverlust**: Ihre Projektdateien bleiben unberührt
✅ **Getestet**: Gründlich auf mehreren Plattformen getestet

Das Tool modifiziert nur Windsurf-Konfigurationsdateien, nicht Ihre tatsächlichen Projektdaten.

</details>

<details>
<summary><b>Was macht der Reset eigentlich?</b></summary>
<br>

Die Reset-Operation:

1. **Erstellt ein Backup** Ihrer aktuellen Windsurf-Konfiguration
2. **Regeneriert Maschinenkennungen**, die von Windsurf verwendet werden
3. **Aktualisiert Konfigurationsdateien** mit neuen Kennungen
4. **Überprüft**, ob die Änderungen korrekt angewendet wurden

Ihre Projektdateien, Erweiterungen und die meisten Einstellungen bleiben unverändert.

</details>

<details>
<summary><b>Verliere ich meine Projekte oder Dateien?</b></summary>
<br>

**Nein!** Windsurf Reset modifiziert nur IDE-Konfigurationsdateien. Ihre Projekte, Code-Dateien und Workspaces sind völlig sicher und werden nicht beeinträchtigt.

</details>

---

### Kompatibilität

<details>
<summary><b>Welche Windsurf-Versionen werden unterstützt?</b></summary>
<br>

**Vollständig unterstützt:**
- Windsurf Version ≤ 1.12.28

**In Tests:**
- Windsurf Version > 1.12.28

**Empfehlung:** Überprüfen Sie immer die [Releases-Seite](https://github.com/yuzeguitarist/Windsurf-Reset/releases) für die neuesten Kompatibilitätsinformationen.

</details>

<details>
<summary><b>Funktioniert es auf meinem Betriebssystem?</b></summary>
<br>

Windsurf Reset unterstützt alle wichtigen Plattformen:

| Plattform | Unterstützung | Formate |
|-----------|---------------|---------|
| **macOS** | ✅ Voll | .dmg, .zip |
| **Windows** | ✅ Voll | .exe, portabel |
| **Linux** | ✅ Voll | .AppImage, .deb |

**Architekturen:**
- macOS: ARM64 (M1/M2/M3) und Intel (x64)
- Windows: x64
- Linux: x64

</details>

<details>
<summary><b>Kann ich es mit der neuesten Windsurf-Version verwenden?</b></summary>
<br>

Getestet und bestätigt mit Windsurf Version 1.12.28 und darunter. Für neuere Versionen:

1. Überprüfen Sie die [Releases-Seite](https://github.com/yuzeguitarist/Windsurf-Reset/releases) auf Updates
2. Suchen Sie nach Kompatibilitätshinweisen
3. Erwägen Sie, auf eine aktualisierte Version zu warten, wenn unsicher
4. Erstellen Sie immer zuerst ein Backup

</details>

---

### Nutzungsfragen

<details>
<summary><b>Wie oft sollte ich das Reset-Tool verwenden?</b></summary>
<br>

**Empfohlene Verwendung:**

- ⚠️ **Nur bei Bedarf** - Nicht unnötig zurücksetzen
- ✅ **Vor Beginn neuer Hauptprojekte**
- ✅ **Bei IDE-Problemen**
- ✅ **Nach größeren Windsurf-Updates**

**Nicht empfohlen:**
- ❌ Tägliche Resets
- ❌ Mehrere Resets in kurzer Zeit
- ❌ Während aktiver Projektentwicklung

</details>

<details>
<summary><b>Was sollte ich vor dem Reset tun?</b></summary>
<br>

**Pre-Reset-Checkliste:**

```
□ Alle offenen Dateien speichern
□ Alle Windsurf-Fenster schließen
□ Benutzerdefinierte Einstellungen notieren
□ Sicherstellen, dass keine Windsurf-Prozesse laufen
□ Ausreichend Festplattenspeicher überprüfen (100 MB)
```

**Optional aber empfohlen:**
- Workspace-Einstellungen exportieren
- Installierte Erweiterungen auflisten
- Benutzerdefinierte Konfigurationen dokumentieren

</details>

<details>
<summary><b>Wie lange dauert ein Reset?</b></summary>
<br>

**Typischer Zeitplan:**

| Operation | Dauer |
|-----------|-------|
| Erkennung | < 1 Sekunde |
| Backup-Erstellung | 1-2 Sekunden |
| Kennung-Generierung | 2-3 Sekunden |
| Konfigurations-Update | 1-2 Sekunden |
| Überprüfung | < 1 Sekunde |
| **Gesamt** | **5-10 Sekunden** |

Die tatsächliche Zeit kann je nach Systemleistung variieren.

</details>

<details>
<summary><b>Kann ich einen Reset rückgängig machen?</b></summary>
<br>

**Ja!** Sie können jedes frühere Backup wiederherstellen:

1. Windsurf schließen
2. Windsurf Reset öffnen
3. "Backup wiederherstellen" klicken
4. Backup auswählen, das Sie wiederherstellen möchten
5. Wiederherstellung bestätigen
6. Windsurf neu starten

Alle Backups enthalten Zeitstempel und Versionsinformationen, um Ihnen bei der Auswahl des richtigen zu helfen.

</details>

---

### Lizenzierung

<details>
<summary><b>Kann ich Windsurf Reset kostenlos verwenden?</b></summary>
<br>

**Ja!** Windsurf Reset ist für den persönlichen Gebrauch kostenlos.

**Erlaubt:**
- ✅ Persönliche Nutzung
- ✅ Bildungsnutzung
- ✅ Gemeinnützige Nutzung
- ✅ Closed-Source-Projekte

**Verboten:**
- ❌ Kommerzielle Nutzung
- ❌ Software verkaufen
- ❌ Attribution entfernen

Siehe [Lizenz](License-Details.md) für vollständige Bedingungen.

</details>

<details>
<summary><b>Kann ich es in meinem Unternehmen verwenden?</b></summary>
<br>

**Kommerzielle Nutzung ist unter der aktuellen Lizenz verboten**.

Für kommerzielle Lizenzierung:
1. [Issue öffnen](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
2. Anwendungsfall beschreiben
3. Wir besprechen Lizenzierungsoptionen

</details>

<details>
<summary><b>Kann ich den Quellcode modifizieren?</b></summary>
<br>

**Modifikationen sind erlaubt**, müssen aber Open-Source sein:

**Anforderungen:**
- ✅ Modifikationen müssen als Open-Source veröffentlicht werden
- ✅ Muss dieselbe Lizenz verwenden
- ✅ Muss Attribution beibehalten
- ✅ Muss klare Dokumentation enthalten

**Hinweis:** Die verteilte Version ist aus Sicherheitsgründen verschleiert.

</details>

---

### Technische Fragen

<details>
<summary><b>Wo werden Backups gespeichert?</b></summary>
<br>

**Standard-Backup-Speicherorte:**

**macOS:**
```
~/Library/Application Support/WindsurfReset/backups/
```

**Windows:**
```
%APPDATA%\WindsurfReset\backups\
```

**Linux:**
```
~/.config/WindsurfReset/backups/
```

Sie können diesen Speicherort in Einstellungen → Backup-Verwaltung ändern.

</details>

<details>
<summary><b>Wie viel Festplattenspeicher benötige ich?</b></summary>
<br>

**Speicheranforderungen:**

| Komponente | Größe |
|------------|-------|
| Anwendung | ~80 MB |
| Pro Backup | ~2-3 MB |
| Empfohlener freier Speicher | 100+ MB |

**Beispiel:** Mit 5 Backups benötigen Sie insgesamt ~100 MB.

</details>

<details>
<summary><b>Benötigt es eine Internetverbindung?</b></summary>
<br>

**Nein!** Windsurf Reset funktioniert vollständig offline.

**Internet nur benötigt für:**
- Herunterladen der Erstinstallation
- Nach Updates suchen (optional)
- Zugriff auf Online-Dokumentation

Alle Kernfunktionen funktionieren ohne Internet.

</details>

<details>
<summary><b>Welche Dateien werden modifiziert?</b></summary>
<br>

Windsurf Reset modifiziert nur Windsurf IDE-Konfigurationsdateien:

**Modifiziert:**
- Maschinenkennungsdateien
- Konfigurations-Cache
- Sitzungsspeicher

**NICHT modifiziert:**
- Ihre Projektdateien
- Code-Repositories
- Benutzerdaten
- Installierte Erweiterungen (Struktur)

</details>

---

### Fehlerbehebung

<details>
<summary><b>Die Anwendung öffnet sich nicht. Was soll ich tun?</b></summary>
<br>

**Versuchen Sie diese Lösungen:**

**macOS:**
```bash
# Quarantäne-Attribut entfernen
xattr -cr /Applications/Windsurf\ Reset.app
```

**Windows:**
- Rechtsklick → Als Administrator ausführen
- Windows Defender/Antivirus überprüfen
- SmartScreen temporär deaktivieren

**Linux:**
```bash
# Ausführbare Berechtigungen sicherstellen
chmod +x Windsurf-Reset-*.AppImage

# Abhängigkeiten überprüfen
ldd Windsurf-Reset-*.AppImage
```

Siehe [Fehlerbehebungsanleitung](Troubleshooting.md) für weitere Lösungen.

</details>

<details>
<summary><b>Windsurf wird nicht erkannt. Was ist falsch?</b></summary>
<br>

**Häufige Ursachen und Lösungen:**

1. **Nicht-standardmäßiger Installationsort**
   - Lösung: Benutzerdefinierten Pfad in Einstellungen festlegen

2. **Windsurf läuft**
   - Lösung: Alle Windsurf-Fenster und -Prozesse schließen

3. **Berechtigungsproblem**
   - Lösung: Mit entsprechenden Berechtigungen ausführen

4. **Nicht unterstützte Version**
   - Lösung: Kompatibilität prüfen, Tool oder Windsurf aktualisieren

Siehe detaillierte Lösungen in [Fehlerbehebung](Troubleshooting.md).

</details>

<details>
<summary><b>Reset ist auf halbem Weg fehlgeschlagen. Was jetzt?</b></summary>
<br>

**Keine Panik!** Ihr Backup ist sicher.

**Wiederherstellungsschritte:**

1. **Windsurf Reset schließen**
2. **Anwendung erneut öffnen**
3. **"Backup wiederherstellen" klicken**
4. **Neuestes Backup auswählen**
5. **Wiederherstellung bestätigen**

Ihr Windsurf wird in den vorherigen Zustand zurückversetzt.

Wenn Probleme bestehen bleiben, siehe [Fehlerbehebung](Troubleshooting.md) oder [Issue öffnen](https://github.com/yuzeguitarist/Windsurf-Reset/issues).

</details>

<details>
<summary><b>Wo kann ich Hilfe bekommen?</b></summary>
<br>

**Support-Ressourcen:**

1. **Dokumentation**
   - [Benutzerhandbuch](User-Guide.md)
   - [Fehlerbehebung](Troubleshooting.md)
   - [Technische Details](Technical-Details.md)

2. **Community-Support**
   - [GitHub Issues](https://github.com/yuzeguitarist/Windsurf-Reset/issues)
   - Überprüfen Sie zuerst bestehende Issues
   - Geben Sie detaillierte Informationen beim Erstellen neuer Issues

3. **Diese FAQ**
   - Durchsuchen Sie alle obigen Fragen
   - Verwenden Sie Strg+F zum Suchen

</details>

---

<div align="center">

[← Back to Wiki Home](Home.md)

</div>
