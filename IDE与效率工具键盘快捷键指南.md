## IntelliJ IDEA 快捷键

### 导航与搜索
| 功能 | Windows | macOS | 说明 |
|------|----------|--------|------|
| 全局搜索 | `Shift + Shift` | `Shift + Shift` | 搜索所有内容 |
| 查找类 | `Ctrl + N` | `Cmd + O` | 按名称查找类 |
| 查找文件 | `Ctrl + Shift + N` | `Cmd + Shift + O` | 按名称查找文件 |
| 查找符号 | `Ctrl + Alt + Shift + N` | `Cmd + Option + O` | 查找符号（方法/字段）|
| 查找使用 | `Alt + F7` | `Option + F7` | 查找使用位置 |
| 查找定义 | `Ctrl + B` | `Cmd + B` | 转到定义处 |
| 最近文件 | `Ctrl + E` | `Cmd + E` | 显示最近打开的文件 |

### 编辑与重构
| 功能 | Windows | macOS | 说明 |
|------|----------|--------|------|
| 生成代码 | `Alt + Insert` | `Cmd + N` | 生成构造器/Getter/Setter等 |
| 重命名 | `Shift + F6` | `Shift + F6` | 重命名变量/方法/类 |
| 提取变量 | `Ctrl + Alt + V` | `Cmd + Option + V` | 提取为变量 |
| 提取方法 | `Ctrl + Alt + M` | `Cmd + Option + M` | 提取为方法 |
| 移动代码 | `Shift + Alt + ↑/↓` | `Shift + Option + ↑/↓` | 上下移动代码行 |
| 优化导入 | `Ctrl + Alt + O` | `Ctrl + Option + O` | 优化导入语句 |
| 格式化代码 | `Ctrl + Alt + L` | `Cmd + Option + L` | 格式化代码 |

### 调试与运行
| 功能 | Windows | macOS | 说明 |
|------|----------|--------|------|
| 运行当前 | `Shift + F10` | `Ctrl + R` | 运行当前配置 |
| 调试当前 | `Shift + F9` | `Ctrl + D` | 调试当前配置 |
| 设置断点 | `Ctrl + F8` | `Cmd + F8` | 切换断点 |
| 单步调试 | `F8` | `F8` | 单步执行 |
| 单步进入 | `F7` | `F7` | 步入方法 |
| 恢复程序 | `F9` | `Cmd + Option + R` | 继续执行 |
| 计算表达式 | `Alt + F8` | `Option + F8` | 评估表达式 |

## 生产力工具快捷键

### Alfred/Raycast (macOS)
| 功能 | 快捷键 | 说明 |
|------|--------|------|
| 唤醒 | `Option + Space` | 打开搜索框 |
| 文件搜索 | `'` | 搜索文件 |
| 网页搜索 | `g` | Google搜索 |
| 计算器 | `=` | 快速计算 |
| 剪贴板历史 | `Option + Cmd + C` | 查看剪贴板历史 |
| 系统命令 | `>` | 执行系统命令 |
| Workflow触发 | `自定义` | 触发自定义工作流 |

### PowerToys (Windows)
| 功能 | 快捷键 | 说明 |
|------|--------|------|
| PowerToys Run | `Alt + Space` | 快速启动器 |
| 窗口管理 | `Win + ↑/↓/←/→` | FancyZones窗口布局 |
| 键盘管理器 | `自定义` | 自定义键盘映射 |
| 颜色选择器 | `Win + Shift + C` | 屏幕取色器 |
| 文件预览 | `Alt + P` | 快速预览文件 |

### 笔记工具 (Notion/Evernote)
| 功能 | Windows | macOS | 说明 |
|------|----------|--------|------|
| 快速笔记 | `Win + Shift + N` | `Cmd + Shift + N` | 新建笔记 |
| 搜索笔记 | `Ctrl + P` | `Cmd + P` | 搜索内容 |
| 格式化文本 | `Ctrl + B/I/U` | `Cmd + B/I/U` | 加粗/斜体/下划线 |
| 代码块 | `Ctrl + Shift + C` | `Cmd + Shift + C` | 插入代码块 |
| 任务列表 | `Ctrl + Shift + T` | `Cmd + Shift + T` | 创建任务列表 |

## 跨平台快捷键统一方案

### 键位映射建议
1. **Caps Lock改键**
   - 映射为 `Ctrl` (Windows) / `Cmd` (macOS)
   - 双击触发原有Caps Lock功能

2. **空格键扩展**
   - 按住作为修饰键
   - 单击保持原有功能

3. **常用修饰键统一**
   ```
   Windows: Ctrl -> Command
           Alt  -> Option
           Win  -> Control
   
   macOS:   Cmd -> Control
           Option -> Alt
           Control -> Win
   ```

### 自定义工作流配置

1. **开发环境启动**
```ahk
; AutoHotkey示例 (Windows)
!d::  ; Alt + D
Run, "C:\Program Files\DEV.bat"
return

; DEV.bat内容
start "" "C:\Program Files\Microsoft VS Code\Code.exe"
start "" "C:\Program Files\Git\git-bash.exe"
start "" "http://localhost:3000"
```

2. **项目快速切换**
```json
// VS Code keybindings.json
{
    "key": "ctrl+alt+1",
    "command": "workbench.action.openWorkspace",
    "args": {"uri": "path/to/project1.code-workspace"}
},
{
    "key": "ctrl+alt+2",
    "command": "workbench.action.openWorkspace",
    "args": {"uri": "path/to/project2.code-workspace"}
}
```

3. **文档处理流程**
```applescript
-- macOS自动化示例
on alfred_script(q)
    tell application "Finder"
        set current_path to POSIX path of (target of front window as text)
    end tell
    
    set cmd to "pandoc \"" & current_path & "\" -o output.pdf"
    do shell script cmd
end alfred_script
```

### 快捷键管理工具推荐

1. **跨平台工具**
   - Autokey (Linux)
   - AutoHotkey (Windows)
   - Hammerspoon (macOS)

2. **专业化工具**
   - BetterTouchTool (macOS)
   - PowerToys (Windows)
   - XMouse Button Control (Windows)

3. **键盘固件**
   - QMK固件
   - VIA配置工具
   - Karabiner-Elements (macOS)

## 工作流优化建议

1. **建立任务模板**
   ```
   开发任务模板:
   1. 打开IDE和相关工具 (Alt + D)
   2. 拉取最新代码 (Alt + G P)
   3. 启动开发服务器 (Alt + R)
   4. 打开文档 (Alt + D)
   ```

2. **创建常用命令别名**
   ```bash
   # .bashrc or .zshrc
   alias gs='git status'
   alias gp='git pull'
   alias dc='docker-compose'
   alias k='kubectl'
   ```

3. **自动化测试流程**
   ```bash
   #!/bin/bash
   # test-workflow.sh
   npm test
   npm run lint
   npm run build
   ```

4. **文档生成工作流**
   ```json
   // VS Code tasks.json
   {
       "version": "2.0.0",
       "tasks": [
           {
               "label": "Generate Docs",
               "type": "shell",
               "command": "jsdoc -c jsdoc.json",
               "group": {
                   "kind": "build",
                   "isDefault": true
               }
           }
       ]
   }
   ```

## 注意事项与最佳实践

1. **快捷键原则**
   - 保持一致性
   - 避免复杂组合
   - 考虑人体工程学
   - 定期回顾和调整

2. **工具选择**
   - 优先选择跨平台工具
   - 注重可配置性
   - 关注社区活跃度
   - 重视文档完整性

3. **配置管理**
   - 使用版本控制
   - 定期备份
   - 模块化组织
   - 注释完善

4. **习惯养成**
   - 循序渐进
   - 专注高频操作
   - 持续优化
   - 分享经验
