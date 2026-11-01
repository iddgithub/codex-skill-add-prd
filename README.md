# add-prd

`add-prd` 是一个 Codex Skill，用于把结构化 PRD 直接加入已有原型：左侧保留真实可交互页面，右侧展示页面级 PRD，并用编号把界面模块与需求条目一一对应。

## 能力

- 识别“添加prd”“在原型上加 PRD”等自然语言触发方式
- 支持已有原型的初始化标注和增量更新
- PRD 固定覆盖页面目的、交互说明、业务规则和异常情况
- 支持一级页面与二级页面分别维护页面级 PRD
- 保留搜索、筛选、新增、编辑、上传、下载、分页和路由跳转等原有交互
- 支持“查看需求说明”开关和 `?prd=1` 直开模式
- 默认不发布外网、不改变站点访问权限

## 安装

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo iddgithub/codex-skill-add-prd \
  --path skills/add-prd
```

如果本机 Python 下载时出现 SSL 证书错误，可改用 Git 稀疏检出：

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo iddgithub/codex-skill-add-prd \
  --path skills/add-prd \
  --method git
```

安装完成后，在下一轮对话中即可使用。

也可以将以下 GitHub 目录链接交给支持 Skill 安装的 Codex：

```text
https://github.com/iddgithub/codex-skill-add-prd/tree/main/skills/add-prd
```

## 使用

自然语言触发：

```text
给当前原型添加prd
```

指定页面范围：

```text
给订单列表和订单详情页面添加prd
```

显式调用：

```text
使用 $add-prd 给当前原型添加左页面、右 PRD 的同屏需求说明模式
```

## 目录结构

```text
skills/add-prd/
├── SKILL.md
└── agents/
    └── openai.yaml
```

## License

MIT
