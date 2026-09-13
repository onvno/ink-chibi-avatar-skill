# Ink Chibi Avatar Skill

`ink-chibi-avatar-skill` 将参考图转换为固定风格的 1:1 水墨 Q 版头像：放大而有神的眼睛、圆润的成人 Q 比例、明亮干净的手绘肤色，以及克制的宣纸背景点缀。

它追求的是“认得出、很可爱、像一幅画”，而不是写实肖像或泛化的日系动漫脸。

## 效果预览

以下是仓库内置的默认 `realism: 0.5` 验收结果。每列先放原始参考图，下一行放对应的 Q 版头像；参考图中的非主体人物、字幕、场景与水印不会带入成图。

| 眼镜笑脸 | 红衣编发 |
| --- | --- |
| **原图**<br>![眼镜笑脸原图](examples/0.jpg) | **原图**<br>![红衣编发原图](examples/02-red-braids.png) |
| **默认 `realism: 0.5`**<br>![眼镜笑脸 Q 版头像](examples/generated/smiling-scholar.png) | **默认 `realism: 0.5`**<br>![红衣编发 Q 版头像](examples/generated/red-braids.png) |

参考输入位于 [`examples/`](examples/)；对应的成图位于 [`examples/generated/`](examples/generated/)。

## 风格约束

- 1:1 头像构图，头部约占画面高度的 80–86%，脸部始终是视觉中心。
- 默认是成人 Q 版：头脸更圆、脸颊更饱满、下半脸更短；眼睛约比原图大 25%，保留人物独特的眼神与眼距。
- 通过发型、眉眼、表情、胡须、头饰、眼镜和主要服装来保留辨识度，而不复刻成人写实脸型。
- 肤色默认使用明亮的浅至中浅手绘色调，保留冷暖底色，但不把昏暗光线或重阴影当成肤色本身。脸部不应出现毛孔、颗粒、斑点或噪点。
- 以墨黑、暖灰和一到两种高饱和水墨色完成对比；高饱和色只服务于人物，背景仅保留极少的浅墨点与断续笔触。
- 手可以作为可爱的辅助动作出现。若出现，保持一只小手、完整掌心与五根圆润手指（含拇指），不遮挡五官、不抢脸部焦点，也不产生缺指、多指或并指。
- 不生成文字、字幕、水印、标志、边框、海报排版或无关场景。

## 使用方法

### 1. 安装

将整个目录放进 Codex 的 skills 目录，保持 `SKILL.md` 位于目录根部。例如：

```bash
mkdir -p ~/.codex/skills
cp -R ./ink-chibi-avatar-skill ~/.codex/skills/
```

目录名与 `SKILL.md` 中的 `name` 必须保持为 `ink-chibi-avatar-skill`。之后在支持图像生成的 Codex 会话中，可直接用自然语言触发，也可显式引用 `$ink-chibi-avatar-skill`。

### 2. 最小请求

附上一张清晰的人物参考图，然后说明：

```text
基于这张图生成水墨 Q 版头像，使用默认参数。
```

默认参数为 `realism: 0.5`，适合大多数头像场景：会保留人物神态与关键辨识点，但保持明显的 Q 版设计。

### 3. 指定参数

```text
使用 $ink-chibi-avatar-skill，基于这张参考图生成 1:1 水墨 Q 版头像。
realism: 0.5
expression: 眉头微挑、侧目、嘴角轻轻上扬
face-shape: subtle
```

| 参数 | 默认值 | 说明 |
| --- | --- | --- |
| `realism` | `0.5` | `0.0–1.0` 的写实保留度。值越低，Q 化越强；值越高，保留越多原图的五官结构与表情。 |
| `expression` | 参考图决定 | 用一句话补充眼神、眉毛、嘴角、视线与头部角度。必要时可以补充一个小手势。 |
| `face-shape` | `subtle` | 默认不额外拉宽或拉长脸部；仅在明确要求时使用 `wider`、`longer` 或自定义夸张方向。 |

### 4. `realism` 的选择

| 范围 | 适用效果 |
| --- | --- |
| `0.0–0.45` | 更强、更俏皮的 Q 化，脸部细节最少。 |
| `0.46–0.59` | 默认区间。神态清晰、脸型明显 Q 化，适合常规头像。 |
| `0.60–0.80` | 保留更多眉眼、脸型与表情，但仍然是水墨 Q 版。 |
| `0.81–1.0` | 更强调参考图结构；仍不会生成照片级皮肤纹理。 |

## 示例素材

| 输入参考 | 输出头像 |
| --- | --- |
| [`0.jpg`](examples/0.jpg)（仅右侧人物） | [`smiling-scholar.png`](examples/generated/smiling-scholar.png) |
| [`02-red-braids.png`](examples/02-red-braids.png) | [`red-braids.png`](examples/generated/red-braids.png) |

## 目录结构

```text
ink-chibi-avatar-skill/
├── SKILL.md               # Codex 执行时读取的完整规则
├── README.md              # 本说明与使用示例
├── examples/
    ├── *.jpg / *.png      # 输入参考图
    └── generated/         # 对应的默认 0.5 成图
└── link/                  # 公众号与小红书关注素材
```

`SKILL.md` 是唯一的生成规范来源；README 只说明如何调用、选择参数和查看验收样例。

## 关注

欢迎关注知之为知之知。

| 微信公众号 | 小红书 |
| --- | --- |
| 扫码关注公众号 | 扫码关注小红书 |
| ![知之为知之知微信公众号二维码](link/wechat.jpg) | ![知之为知之知小红书名片](link/xhs.jpg) |
