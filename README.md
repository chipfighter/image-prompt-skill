# image-prompt：生图摄影转译 skill

把聊出的画面想法转成具体的摄影设计和生图提示词；用户要求出图时，调用可用的生图工具并交付图片。适合原创静帧、角色或场景参考图，以及按需制作的视频关键帧。

## 它会做什么

- 明确主体、动作、表情、视线、数量和空间关系，逐份说明参考图的用途。
- 使用准确的摄影术语交代机位、景别、构图、焦段、光圈、景深、对焦与布光，并补充可见效果。参数作为提示词中的摄影设定，不冒充工具的独立控制项。
- 明确风格、滤镜和后期处理，说明光线来源、材质、色彩与明暗层次，不默认添加颗粒、柔光或重度磨皮。
- 局部编辑时明确保留原图的构图、透视及其他不变内容；视频关键帧按指定阶段设计，不把所有参考图都当成关键帧。
- 用户只要提示词时交付全文，要图片时实际生成。具体画面要求可配合 [image-spec-check](https://github.com/chipfighter/image-spec-check-skill) 检查。

视频中的动作过程和运镜提示词由 [video-prompt](https://github.com/chipfighter/video-prompt-skill) 处理；整套分镜预演由 [storyboard-preview](https://github.com/chipfighter/storyboard-preview-skill) 处理。

## 安装

把下面这句话发给你的 Claude Code 或 Codex：

```text
帮我安装这个 skill：https://github.com/chipfighter/image-prompt-skill
```

将仓库中的 `image-prompt/` 整个文件夹复制到相应目录，保留内部文件结构：

- Claude Code，包括桌面端本地 Code 会话：`~/.claude/skills/image-prompt/`
- Codex：`~/.agents/skills/image-prompt/`
- 其他 agent：读取 `SKILL.md`，支持文件按需读取。

更新后在新会话中使用最新版。Claude 的聊天或 Cowork 技能库使用应用内的独立安装方式，本地 Code 目录不等于账户技能库。生成图片需要相应 agent 已接入可用的生图工具。

## 文件

- `image-prompt/SKILL.md`：画面理解、摄影设计、调用与交付规则。
- `image-prompt/references/prompt-detail.md`：摄影描述示例。
- `image-prompt/agents/openai.yaml`：Codex 的技能界面配置。

## 许可

MIT
