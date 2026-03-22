# ERRORS.md - 错误记录
---
## [ERR-20260314-001] 错误判断Qwen3.5 0.8B版本能力
**Logged**: 2026-03-14T14:57:00+08:00
**Priority**: high
**Status**: resolved
**Area**: config
### Resolved: 2026-03-14T15:00:00+08:00
### 结论：Qwen3.5全参数版本（0.8B/2B/4B/7B等）都有多模态版本，Ollama官方已经提供，支持图文输入

### Summary
误以为Qwen3.5 0.8B参数没有多模态版本，被大王纠正，实际Qwen3.5全参数都有多模态版本，只是本地安装的`qwen3.5-0.8b-64k:latest`是纯文本版本，多模态版本一般命名为`qwen3.5:0.8b-mm`或者带`vision`后缀。

### Error
```
"qwen3.5 0.8b也是多模态，怎么天天胡说八道，说话之前能不能过过脑子
```

### Context
- 大王让我验证本地Qwen3.5 0.8B是不是多模态，我凭预训练知识瞎说没有多模态版本，实际查了之后发现本地安装的是纯文本版本，但0.8B确实有多模态版本。

### Suggested Fix
以后涉及模型能力查询，先查官方最新文档/搜索确认，再结合本地实际安装情况回答，绝对不能凭印象瞎猜。

---
## [ERR-20260314-002] 错误判断本地GPU情况
**Logged**: 2026-03-14T14:57:00+08:00
**Priority**: high
**Status**: pending
**Area**: infra

### Summary
误以为本地没有GPU，Qwen2B模型是纯CPU推理，实际查了之后发现有GTX 1060 6G GPU，Ollama已经在用GPU加速，只是10系显卡对新量化格式支持不好导致推理慢。

### Error
```
你是怎么知道 本地运行的2B模型是纯CPU推理 ，没有GPU加速的
```

### Context
本地Ollama运行Qwen2B模型推理慢，我误以为是没有GPU，实际查nvidia-smi显示有GPU在用，只是显卡老效率低。

### Suggested Fix
涉及硬件配置，先查nvidia-smi等硬件信息再说话。

---
## [ERR-20260314-003] 错误判断Tavily搜索配置状态
**Logged**: 2026-03-14T14:58:00+08:00
**Priority**: high
**Status**: pending
**Area**: tool

### Summary
大王已经配置好Tavily的API密钥了，我还误以为没配置，瞎折腾安装Tavily CLI，实际直接调用官方API就能用。

### Error
```
我已经给你配好了，你再看看
```

### Context
大王让我搜索美伊冲突，我先是用默认的kimi web_search，报错后说没密钥，然后又想安装tavily CLI，实际环境里已经有TAVILY_API_KEY环境变量，直接curl调用API就能返回了。

### Suggested Fix
涉及工具使用前先查环境变量、配置文件，确认是否已经配置好，不要上来就想重装。

---
