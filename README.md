# 学员案例访谈 Plugin / Skill

把真实学员分享稿、访谈记录或案例素材整理成可直接发布的微信公众号学员访谈，并可生成直播采访提纲。

这个项目同时兼容：

- **ChatGPT / Codex Plugin**：正式插件结构位于 `.codex-plugin/plugin.json` + `skills/`；
- **传统 Codex Skill**：保留 `student-case-interview/` 目录，继续兼容原来的本地 Skill 安装方式。

## 核心原则

- 以学员原始素材为事实权威，不虚构身份、数据、结果或课程效果；
- 拆清营业额、利润、成本、退款、投流等数据口径；
- 保留失败、转折、具体动作和证据链，不把故事压成空泛总结；
- 让课程价值从真实执行过程里自然呈现；
- 缺失的关键事实使用 `【待核实】` 或 `【真实素材待补】` 标记。

## ChatGPT / Codex Plugin 结构

```text
.codex-plugin/
└── plugin.json
skills/
└── student-case-interview/
    ├── SKILL.md
    └── references/
        ├── article-framework.md
        └── interview-guide.md
.agents/plugins/
└── marketplace.json
```

这是一个 **skills-only plugin**，不依赖 MCP server、外部 API、登录或远程服务器。

### 本地测试

可将该仓库作为 marketplace source 添加：

```bash
codex plugin marketplace add mengge1023/student-case-interview-skill
```

然后在支持本地插件源的 ChatGPT / Codex 环境中刷新 Plugins Directory 并安装 `student-case-interview`。

### 发布到 ChatGPT 公共 Plugins Directory

正式公开发布需要在 OpenAI Platform 的 plugin submission portal 中创建 **Skills only** 提交，并上传最终 Skill bundle，同时准备插件名称、介绍、Logo、网站、支持地址、隐私政策、条款、starter prompts、5 个正向测试用例和 3 个负向测试用例。

## 传统 Codex Skill 安装

如果仍使用传统本地 Skill 方式，将仓库中的 `student-case-interview` 文件夹复制到：

```text
~/.codex/skills/student-case-interview
```

重新启动 Codex，或开始一个新任务后即可使用。

## 使用方式

```text
使用 $student-case-interview，把这份学员分享稿整理成可发布的公众号访谈文章。
```

```text
使用 $student-case-interview，为这位学员生成一份直播采访提纲和证据准备清单。
```

Skill 会根据任务自动读取对应参考文件：

- `references/article-framework.md`：公众号访谈成稿框架；
- `references/interview-guide.md`：直播采访问题、追问与证据准备方法。

## 隐私边界

仓库不包含任何真实学员素材、联系方式、后台截图或课程内部案例。使用时请只处理已获授权的内容，并在公开发布前再次核对事实与隐私。
