# STMS — 技术拆解

## Optical model: thickness → absorption → refraction

厚度使用解析凸主体 proxy，让薄边与厚中心得到不同的光学响应。Beer–Lambert 用于 transmittance；screen-space refraction 只采样当前可见背景，因此不能重建画面外信息，也不能提供完整的透明主体互折射。

![Analytic thickness proxy debug: brighter centre, thinner rim](../media/thickness-proxy.png)

上图是厚度代理通道，不是测量得到的真实光程。

![Screen-space refraction against a procedurally generated checker](../media/refraction-debug.png)

棋盘背景用于观察采样偏移；这是项目自身的校准画面，不是外部照片。

## Motion & local interaction

弹簧运动描述整体 squash / lean；局部接触层在 contact point 附近产生 dent 与周围 bulge，再与整体 wobble 组合。参数化 Material / Motion Profile 与 Preset 用于比较不同外观和响应，不代表真实物理材料参数拟合。

## Damage / recovery

同一网格通过 Shader 位移与 seam 外观模拟 necking、two-lobe visual separation 与 closing / regeneration。damage / recovery lifecycle 是驱动来源，未生成独立物理碎片或新拓扑。

![Soft-tear debug: partition, seam and regeneration channels](../media/soft-tear-debug.png)

从左到右为 partition、seam、regeneration Debug。它们解释视觉机制，不是连续动态录像。

## M2-A generalization: explicit subject binding

M2-A 的研究问题不是“做一个水母 Shader”，而是验证现有 STMS 能否在 **不复制 Shader core** 的前提下支持第二种、结构差异明显的软半透明主体。

最新 canonical audit 中，subject binding 已从草稿进入实现：新的 subject declaration 显式声明 renderer 成员、角色与可选的 per-renderer body metrics；motion、local contact、fracture-role、breakage、bubble-field 与 internal-noise 的目标解析均可使用该 binding，同时保留旧 jelly 的 fallback path。

这一改动经过独立 headless 进程回归：

- compile/import：0 C# errors / 0 Shader errors / 0 Exceptions；
- M1-F preset live re-apply：failures = 0；
- M1-G fracture lifecycle：gate = PASS。

这证明的是 **generalization infrastructure**，不是 jellyfish 最终视觉。当前还没有通过完整验收的 jellyfish geometry/material/hero capture。

## Current generalization boundaries

- current thickness model is still a convex/analytic proxy;
- motion weighting is built around a floor-contact anchor model;
- internal structure volumes are spherical and origin-centred;
- the current preset look path is primarily single-renderer;
- thin/open-sheet tissue would need extra two-sided-normal / thickness handling;
- screen-space refraction does not solve inter-subject transparent refraction.

这些限制被记录为下一阶段研究边界，而不是被隐藏成“已泛化完成”。

## Evidence scope

公开仓库只保留少量已审计的运行捕获与说明。原研发记录中的校准对照、回归 CSV、日志、散帧、agent 输出和完整工程不会作为 showcase 发布。

本页面不宣称 GPU benchmark、physical SSS、topology fracture、FEM soft-body simulation，也不把未编译或未通过 capture gate 的 jellyfish 草稿当作公开成果。
