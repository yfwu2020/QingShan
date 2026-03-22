# LEARNINGS.md - 经验教训记录
---
## [LRN-20260314-001] 本地内容查询规则
**Logged**: 2026-03-14T14:55:00+08:00
**Priority**: critical
**Status**: pending
**Area**: config

### Summary
大王明确规定：本地相关问题必须先实际查询验证，再结合预训练知识回答，两者矛盾时100%以本地结果为准；实时/迭代快的内容优先上网搜最新消息，绝对不能凭印象瞎猜。

### Details
之前多次犯错误：
1. 误以为本地Qwen3.5 0.8B没有多模态版本，实际是有，只是本地安装的是纯文本版本
2. 误以为本地没有GPU，实际有GTX 1060 6G并且Ollama已经在用GPU加速
3. 不知道Tavily密钥已经配置好，瞎折腾安装CLI，实际直接调用API就可以用

### Suggested Action
每次回答涉及本地内容前，必须先执行查询命令拿到实锤结果再回答；涉及实时内容先搜最新消息再回答。

### Metadata
- Source: user_feedback
- Related Files: MEMORY.md
- Tags: 规则, 本地查询, 实时搜索

---
