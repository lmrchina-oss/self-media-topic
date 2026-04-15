# 自媒体选题 - 多平台安装包

本目录包含不同平台的安装包和配置文件。

## 📦 安装包列表

### 1. 扣子 (Coze)
- **文件**：`../self-media-topic.skill`
- **安装方式**：
  1. 下载 `self-media-topic.skill` 文件
  2. 打开扣子工作台
  3. 点击"导入Skill"
  4. 选择文件并导入
  5. 直接使用

### 2. Claude Desktop
- **文件**：`claude_desktop_config.json`
- **安装方式**：
  1. 下载 `claude_desktop_config.json`
  2. 将文件放到 Claude Desktop 的配置目录：
     - **macOS**: `~/Library/Application Support/Claude/`
     - **Windows**: `%APPDATA%\Claude\`
  3. 重启 Claude Desktop
  4. 在侧边栏选择"自媒体选题"即可使用

### 3. OpenAI GPTs
- **文件**：`openai_gpt_config.json`
- **安装方式**：
  1. 访问 https://chat.openai.com/gpts
  2. 点击 "Create a GPT"
  3. 在 "Configure" 标签页：
     - 将 `openai_gpt_config.json` 的内容复制到对应字段
     - 或直接使用 "Instructions" 文本框粘贴完整提示词
  4. 设置名称和描述
  5. 保存并发布

### 4. OpenAI Assistant API
- **文件**：`assistant_api_config.json`
- **安装方式**：
  1. 使用 OpenAI Python SDK：
     ```python
     import openai

     # 读取配置
     with open('assistant_api_config.json', 'r') as f:
         config = json.load(f)

     # 创建Assistant
     assistant = client.beta.assistants.create(
         name=config['name'],
         description=config['description'],
         instructions=config['instructions'],
         model=config['model']['name']
     )
     ```
  2. 或使用 OpenAI API 控制台手动创建

### 5. WorkBuddy
- **文件**：`workbuddy_agent_config.yaml`
- **安装方式**：
  1. 下载 `workbuddy_agent_config.yaml`
  2. 打开 WorkBuddy 平台
  3. 创建新 Agent
  4. 导入配置文件或手动粘贴内容
  5. 保存并启用

---

## 🚀 快速开始

### 选择你的平台

#### 使用 Claude
```bash
# 下载配置文件
curl -O https://github.com/your-username/self-media-topic/releases/latest/download/claude_desktop_config.json

# 放到配置目录
mv claude_desktop_config.json ~/Library/Application\ Support/Claude/

# 重启 Claude Desktop
```

#### 使用 OpenAI GPTs
```
1. 访问 https://chat.openai.com/gpts
2. 创建新GPT
3. 粘贴提示词（见 UNIVERSAL_USAGE.md）
4. 保存并使用
```

#### 使用 WorkBuddy
```
1. 创建新Agent
2. 导入 workbuddy_agent_config.yaml
3. 保存并启用
```

#### 使用扣子
```
1. 下载 self-media-topic.skill
2. 导入到扣子工作台
3. 直接使用
```

---

## 📋 平台特性对比

| 平台 | 安装方式 | 联网搜索 | 自定义能力 | 推荐场景 |
|------|---------|---------|-----------|---------|
| **扣子** | 导入.skill | ✅ 支持 | ✅ 强 | 完整功能使用 |
| **Claude Desktop** | JSON配置 | ⚠️ 部分 | ✅ 强 | 桌面集成使用 |
| **OpenAI GPTs** | Web界面 | ✅ 支持 | ✅ 强 | 在线快速使用 |
| **OpenAI API** | API调用 | ✅ 支持 | ✅ 强 | 开发集成使用 |
| **WorkBuddy** | YAML配置 | ✅ 支持 | ✅ 强 | 工作流集成使用 |

---

## 🔧 配置文件说明

### claude_desktop_config.json
- **适用平台**: Claude Desktop
- **包含内容**: 完整的instructions、categories、capabilities
- **特点**: 原生支持Claude的所有特性

### openai_gpt_config.json
- **适用平台**: OpenAI GPTs
- **包含内容**: Instructions、tools配置、model参数
- **特点**: 支持GPTs的所有功能

### assistant_api_config.json
- **适用平台**: OpenAI Assistant API
- **包含内容**: 完整的Assistant配置
- **特点**: 适合API集成和开发

### workbuddy_agent_config.yaml
- **适用平台**: WorkBuddy
- **包含内容**: system_prompt、tools、input_examples
- **特点**: 结构化配置，易于管理

---

## 💡 使用技巧

### 1. 自定义配置
所有配置文件都可以根据需求修改：
- 调整评分标准权重
- 修改标题优化公式
- 添加自定义输出格式

### 2. 集成到工作流
- OpenAI API：可以集成到你的应用中
- WorkBuddy：可以配置为工作流的一部分
- Claude Desktop：可以作为日常工具使用

### 3. 联网搜索增强
如果平台支持联网搜索，可以让AI先搜索热点：
```
请先搜索"AI工具 近一周 热点"，然后基于搜索结果分析选题
```

---

## 📚 相关文档

- [通用使用指南](../UNIVERSAL_USAGE.md)
- [项目说明](../README.md)
- [评分标准详解](../self-media-topic/references/scoring_criteria.md)
- [平台优化指南](../self-media-topic/references/platform_guidelines.md)

---

## 🆘 常见问题

**Q: 哪个平台最好用？**
A: 取决于你的需求：
- 扣子：功能最完整，适合深度使用
- Claude Desktop：集成度高，适合日常使用
- OpenAI GPTs：最便捷，适合快速使用
- WorkBuddy：适合工作流集成

**Q: 可以同时安装多个版本吗？**
A: 可以！不同平台的配置文件互不冲突。

**Q: 配置文件可以修改吗？**
A: 可以，所有配置文件都可以根据你的需求自定义修改。

**Q: 如何更新到最新版本？**
A: 重新下载最新的配置文件并替换即可。

---

## 🤝 贡献

欢迎提交Issue和Pull Request来改进各个平台的配置！

---

**开始使用**：选择适合你的平台，下载对应的配置文件即可！
