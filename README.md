# 真人随手拍口播

**适合什么输入：** 想法、口喷草稿，或已经拍好的自拍、走路、固定机位等真人口播。

**得到什么：** 可直接念的完整稿，或保留真实原声与人物现场的精剪成片、双语字幕、封面和四平台发布包；按本次需要交付。

**什么时候选：** 观众主要看本人表情、现场和观点。即使坐在电脑前，也不因此改成录屏教程；不为放文字把全屏真人缩成资料小窗。

**从哪里开始：** 打开 [SKILL.md](SKILL.md)。只有想法先写稿；已有正式视频直接精剪；只改字幕、封面或某一段时保留其他已选内容。三秒真实钩子、V24及当前封面方向继续执行。

原key `edit-talking-head-social-video` 继续有效。电脑界面、引用原片或资料承担主要解释时，在制作开始前一次分流至 `edit-screen-tutorial-video`；混合片按主任务选负责人，分段构图共用原声时轴。白板和访谈保留专项，不互相递归调用整套流程。

## 包内资源

- [布局](references/person-layout.md)、[动作](references/person-motion.md)、[分流](references/video-routing.md)。
- [声音与剪辑](references/editing-and-audio.md)、[字幕](references/subtitles-and-motion.md)、[封面](references/covers-and-release.md)、[四平台交付](references/four-platform-delivery.md)。
- [39方法与8配方](references/editing-methods/index.md)，含来源、授权、V24原子组件和校验脚本；原证据14文件仅作本地可选输入，不随公共包分发。来源/许可分别见方法模块、节奏MIT许可和源剪辑ORIGIN；不把来源媒体或无LICENSE上游代码统称MIT。
- [源素材处理](references/source-editing.md)：四个模板自带common模块，默认当前工程或显式 `--workdir`。FFmpeg/FFprobe/Python、实际ASR所需Whisper及实际编辑器是显式工具条件，不携带原媒体、凭据或机器环境。

## 维护共同规范

本包是共同规范的唯一维护源。明确白名单见 `distribution/shared-video-manifest.json`；录屏包及其他消费者使用构建时生成的包内副本，运行时不读取兄弟Skill。维护后用 `scripts/sync_shared_video.py --target <目标> --profile <profile>` 生成；已有无lock的旧分发源须显式 `--adopt-existing`，已有副本被手改则拒绝覆盖。

派发给其他消费者时用 `--bundle-dir shared-video`；它们只读取所需参考，不继承真人或屏幕的完整流程。`--check --target <目标> --bundle-dir shared-video` 仅校验该目标自有文件，无需安装本包；构建维护时可加 `--compare-source <本包>` 比较源哈希。代码检查不表示视频视听通过或用户接受，实际成片按[质量标准](references/quality-standards.md)另查。
