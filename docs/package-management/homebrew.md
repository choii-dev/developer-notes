## Markdown Notes

### 一、 核心基础操作

| 命令 | 功能 |
| :--- | :--- |
| `brew update` | 更新 Homebrew 本身及软件仓库索引 |
| `brew search <name>` | 搜索软件包（CLI 工具或 App 均可） |
| `brew install <name>` | 安装指定的命令行工具（如 `brew install git`） |
| `brew uninstall <name>` | 卸载指定的软件包 |
| `brew list` | 列出已安装的所有软件包 |
| `brew info <name>` | 查看软件包的详细信息（版本、依赖、安装路径等） |

---

### 二、 升级与清理

| 命令 | 功能 |
| :--- | :--- |
| `brew outdated` | 列出所有有新版本可更新的软件包 |
| `brew upgrade` | 升级**所有**已安装的软件包 |
| `brew upgrade <name>` | 仅升级指定的软件包 |
| `brew cleanup` | 清理旧版本的下载缓存与残留旧文件（释放磁盘空间） |

---

### 三、 带 GUI 界面应用（Cask）

| 命令 | 功能 |
| :--- | :--- |
| `brew install --cask <app_name>` | 安装带 GUI 颜面的软件（如 `brew install --cask typora`） |
| `brew uninstall --cask <app_name>` | 卸载带 GUI 界面的软件 |
| `brew list --cask` | 列出已安装的所有 Cask 应用 |

---

### 四、 系统诊断与故障排查

| 命令 | 功能 |
| :--- | :--- |
| `brew doctor` | 检查 Homebrew 环境是否存在异常或冲突问题 |
| `brew deps <name>` | 查看指定软件包的底层依赖项 |
