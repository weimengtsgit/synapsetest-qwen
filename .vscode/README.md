# VSCode/Cursor 配置说明

本目录包含 VSCode/Cursor IDE 的配置文件，用于优化开发体验。

## 📁 配置文件

### `settings.json`
项目级别的 IDE 设置：
- ✅ 启用 pytest 测试框架
- ✅ 配置测试自动发现
- ✅ 设置 Python 路径和环境
- ✅ 配置代码分析路径

### `launch.json`
调试配置：
- Python: Current File - 调试当前文件
- Python: pytest - Current File - 调试当前测试文件
- Python: pytest - All Tests - 调试所有测试
- Python: FastAPI App - 调试 FastAPI 应用

### `tasks.json`
预定义任务（Cmd/Ctrl + Shift + P -> "Tasks: Run Task"）：
- pytest: Run All Tests - 运行所有测试
- pytest: Run Current File - 运行当前文件测试
- pytest: Run with Coverage - 生成覆盖率报告
- pytest: Run Failed Tests Only - 只运行失败的测试
- pytest: Collect Tests Only - 收集测试（不运行）
- pytest: Run API Tests - 运行 API 测试
- pytest: Run Model Tests - 运行模型测试

### `extensions.json`
推荐的 VSCode 扩展：
- ms-python.python - Python 语言支持
- ms-python.vscode-pylance - Python 语言服务器
- ms-python.debugpy - Python 调试器
- littlefoxteam.vscode-python-test-adapter - 测试适配器

## 🚀 快速开始

### 运行测试

1. **使用运行按钮**（最简单）
   - 打开任意测试文件
   - 在测试方法左侧点击 ▶️ 按钮

2. **使用测试资源管理器**
   - 点击侧边栏 🧪 图标
   - 浏览并运行测试

3. **使用命令行**
   ```bash
   cd ai-service
   python3 -m pytest
   ```

### 调试测试

1. 在测试代码中设置断点
2. 右键点击测试方法旁的 ▶️
3. 选择 "Debug Test"

### 运行任务

1. 按 `Cmd/Ctrl + Shift + P`
2. 输入 "Tasks: Run Task"
3. 选择一个预定义任务

## 📚 详细文档

- **测试快速启动**：`ai-service/tests/QUICK_START.md`
- **测试配置详解**：`ai-service/tests/TEST_SETUP.md`
- **配置完成总结**：`ai-service/TEST_RUNNER_SETUP_SUMMARY.md`

## 🔧 自定义配置

你可以根据需要修改这些配置文件：

### 修改 Python 解释器
在 `settings.json` 中：
```json
"python.defaultInterpreterPath": "/path/to/your/python"
```

### 添加更多测试参数
在 `settings.json` 中：
```json
"python.testing.pytestArgs": [
  "ai-service/tests",
  "-v",
  "-s",
  "--tb=short"
]
```

### 添加新任务
在 `tasks.json` 中添加新的任务配置。

### 添加新调试配置
在 `launch.json` 中添加新的配置项。

## ⚠️ 注意事项

1. **不要提交个人配置**：如果有个人特定的配置，请添加到 `.git/info/exclude` 中
2. **团队共享配置**：当前配置文件是团队共享的，修改时请考虑其他团队成员
3. **备份配置**：修改前建议备份原配置

## 🆘 故障排查

### 测试按钮不显示
```bash
# 重新加载窗口
Cmd/Ctrl + Shift + P -> "Developer: Reload Window"

# 配置测试
Cmd/Ctrl + Shift + P -> "Python: Configure Tests"
```

### Python 解释器错误
```bash
# 检查解释器
点击左下角 Python 版本
选择正确的解释器
```

### 测试发现失败
```bash
# 查看测试日志
打开 "输出" 面板 -> 选择 "Python Test Log"
```

---

**最后更新：** 2025-11-26
**维护者：** SynapseTest Team

