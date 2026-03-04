# Claude Code 最佳实践：50 条 Claude Code 技巧

> 原文链接: https://mp.weixin.qq.com/s/cN9eqbrHo6LlfuJz7xAqxQ
> 图片状态: 已本地化 (assets/)

---

# Claude Code 最佳实践：50 条 Claude Code 技巧

### 基础技巧

  1. 1\. 明确任务框架 - 在做任何事之前，确切说明你希望 Claude 做什么。
  2. 2\. 指令前置 - 始终将最重要的指令放在提示词的最顶端。
  3. 3\. 让 Claude 能够验证其工作 - 包含测试、截图或预期输出，以便 Claude 自查。这是你能做的杠杆率最高的一件事。
  4. 4\. 提示词结构技巧 - 为了让最后几条技巧更具实操性，我喜欢这种提示词结构：[角色] + [任务] + [上下文]
  5. 5\. Chrome 插件技巧 - UI 变更可以使用 Claude Chrome 插件进行验证。它会打开浏览器，测试 UI，并不断迭代直到代码正常工作。
  6. 6\. 先探索，再计划，后编码 - 先调研（此过程可包含其他 LLM），然后进入 Plan Mode，最后切换回普通模式执行代码。
  7. 7\. 在提示词中提供具体上下文 - 指令越精确越好。Claude 只能推断上下文。
  8. 8\. 假设零上下文 - 假设 Claude 对你的项目一无所知。告诉它需要知道的一切。
  9. 9\. 丰富上下文 - 使用 @ 链接文件、数据和图像。
  10. 10\. CLAUDE.md 技巧 - 运行 /init 为当前项目生成一个初始 CLAUDE.md 文件。



### 项目与 Skill 使用

  1. 11\. 项目指令 - 使用项目级指令定义长期行为，而不是重复提示。
  2. 12\. 项目记忆 - 编辑 “Memory” 标签页，精确控制 Claude 随时间推移应保留或忽略的内容（这也适用于项目）。
  3. 13\. Claude Skills - 利用它们将可重复的工作流转化为 Skill，而不是重新提示。
  4. 14\. 从示例生成 Skill - 粘贴一个优秀的输出，要求 Claude 将其转化为可复用的 Skill。你甚至可以上传截图，要求 Claude 复制它；将其转化为 Skill（这是创建高级 Skill 的简便方法）。
  5. 15\. Skill 版本控制 - 在优化工作流时复制并对 Skill 进行版本管理，而不是直接编辑正在使用的 Skill。
  6. 16\. 项目卫生 - 定期清理记忆、文件和指令，以避免漂移。
  7. 17\. 项目上下文串扰 - 为不相关的工作流建立独立项目，以防止上下文串扰。
  8. 18\. Claude Skills 仓库 - 一个包含 80,000+ Claude Skills 的库。https://skillsmp.com/
  9. 19\. Claude Skills 库 - 一个很酷的网站，提供即插即用的 Skills 等内容。https://mcpservers.org/claude-skills
  10. 20\. 项目记忆 - 项目记忆可以存储在 ./CLAUDE.md 或 ./.claude/CLAUDE.md 中。



### 被低估的迷你技巧（大多数人不知道这些）

  1. 21\. 模型堆叠 - 在打开 Claude Code 之前，使用其他 LLM 规划项目并生成高级 mega prompts——这一策略还能节省 Plan Mode 的 token。
  2. 22\. 创建自定义 Subagent - 在 .claude/agents/ 中定义专门的助手，Claude 可以将独立任务委托给它们。
  3. 23\. 输出打分 - 要求 Claude 根据预定义的成功标准对其回答进行打分。
  4. 24\. 安装插件 - 运行 /plugin 浏览市场。插件无需配置即可添加 Skill、工具和集成。
  5. 25\. 在 Claude Code 中教授 Claude Code - 一个直接在 Claude Code 内部教授 Claude Code 的课程。https://ccforeveryone.com/
  6. 26\. Claude 访谈 - 对于大型项目，让 Claude 先采访你。从一个极简提示词开始，要求 Claude 使用 AskUserQuestion 工具采访你。
  7. 27\. 频繁纠正 - 经常纠正 Claude。一旦它开始偏离轨道，立即停止（按 ESC 停止 Claude 的中途操作）。
  8. 28\. 清除 - 运行 /clear 开始一个干净的会话。
  9. 29\. 倒带 - 双击 ESC 或运行 /rewind 打开检查点菜单。
  10. 30\. 运行多个会话 - 运行并行会话主要有两种方式：


  * • Claude Desktop: 可视化管理多个本地会话。每个会话都有自己独立的工作树。
  * • Claude Web: 在 Anthropic 的安全云基础设施上的隔离虚拟机 (VM) 中运行。



### 调试、错误处理与常见失败模式

  1. 31\. 步骤隔离 - 仅重新运行出错的步骤，而不是重新生成所有内容。
  2. 32\. 错误复现 - 要求 Claude 故意复现失败以理解问题。
  3. 33\. 回滚提示词 - 回退到上一个已知良好的提示词，并一次应用一个更改。
  4. 34\. 过度具体的 CLAUDE.md - 如果你的 CLAUDE.md 太长，Claude 会忽略其中一半，因为重要规则会淹没在噪音中。 修复：无情删减。如果 Claude 在没有指令的情况下已经能正确执行某事，删除该指令或将其转换为钩子 (hook)。
  5. 35\. 别犯这个错 - 你从一个任务开始，然后问 Claude 一些不相关的事，再回到第一个任务。上下文充满了不相关的信息。 修复：在不相关任务之间运行 /clear。
  6. 36\. 过度纠正 - Claude 做错了，你纠正它，它还是错的，你再次纠正。上下文被失败的方法污染了。 修复：在两次纠正失败后，运行 /clear 并结合你学到的内容写一个更好的初始提示词。
  7. 37\. 逐步回放 - 让 Claude 逐行演示它是如何生成答案的。
  8. 38\. 无限探索 - 你要求 Claude “调查” 某事却没有限定范围。Claude 读取数百个文件，填满上下文。 修复：缩小调查范围或使用 Subagent，以免探索过程消耗你的主上下文。
  9. 39\. 调试项目 - 创建一个专门用于调试代码的 AI 项目（Grok 4 Heavy 擅长调试）。
  10. 40\. Context Window 管理 - Claude 的 Context Window 很快就会填满。发生这种情况时，Claude 可能会开始忘记之前的指令。此页面将帮助你消除该问题：https://code.claude.com/docs/en/costs#reduce-token-usage



### 最终技巧

  1. 41\. Notion 数据库 - 将你的 Notion 数据库连接到 Claude，以存储你最好和最常用的提示词。
  2. 42\. 实战学习 Claude Code - Anthropic 的学习资源：https://www.anthropic.com/learn
  3. 43\. Claude 课程 - Coursera 上的课程：https://www.anthropic.com/learn
  4. 44\. Boris 的设置 - Claude Code 的创建者如何最大化利用 Claude Code (Boris’ Claude Code Setup Cheatsheet)。
  5. 45\. Claude Code 最佳实践 (DOC) - 最新文档链接：https://code.claude.com/docs/en/best-practices
  6. 46\. 安全自主模式 - 使用 claude --dangerously-skip-permissions 绕过所有权限检查，让 Claude 不受干扰地工作。这非常适合修复 lint 错误或生成样板代码等工作流。
  7. 47\. 稳扎稳打 - 慢慢来。特别是在构建严肃的工作流时。计划。计划。再计划。然后，执行。
  8. 48\. Claude 超能力 - 一个 Claude Code 超能力的 GitHub 仓库。https://github.com/obra/superpowers
  9. 49\. Hooks - 最适合那些必须每次都发生、零例外的操作。
  10. 50\. 如何扩展 Claude Code - Anthropic 指南：https://code.claude.com/docs/en/features-overview

  

