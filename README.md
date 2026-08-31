# 学员案例访谈 Skill

把真实学员分享稿、访谈记录或案例素材整理成可直接发布的微信公众号学员访谈，并可生成直播采访提纲。

这个 Skill 强调：

- 以学员原始素材为事实权威，不虚构身份、数据、结果或课程效果；
- 拆清营业额、利润、成本、退款、投流等数据口径；
- 保留失败、转折、具体动作和证据链，不把故事压成空泛总结；
- 让课程价值从真实执行过程里自然呈现；
- 缺失的关键事实使用 `【待核实】` 或 `【真实素材待补】` 标记。

## 安装

将仓库中的 `student-case-interview` 文件夹复制到 Codex Skills 目录：

```text
~/.codex/skills/student-case-interview
```

重新启动 Codex，或开始一个新任务后即可使用。

## 使用方式

可以直接提出需求，例如：

```text
使用 $student-case-interview，把这份学员分享稿整理成可发布的公众号访谈文章。
```

```text
使用 $student-case-interview，为这位学员生成一份直播采访提纲和证据准备清单。
```

Skill 会根据任务自动读取对应参考文件：

- `references/article-framework.md`：公众号访谈成稿框架；
- `references/interview-guide.md`：直播采访问题、追问与证据准备方法。

## 目录结构

```text
student-case-interview/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── article-framework.md
    └── interview-guide.md
```

## 隐私边界

仓库不包含任何真实学员素材、联系方式、后台截图或课程内部案例。使用时请只处理已获授权的内容，并在公开发布前再次核对事实与隐私。
