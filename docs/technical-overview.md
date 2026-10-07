# STMS — 技术拆解

## 光学：厚度代理 → 吸收 → 折射

厚度使用解析凸主体 proxy，薄边与厚中心得到不同光学参数。Beer–Lambert 用于 transmittance；screen-space refraction 从当前可见背景采样，因此不能重建画面外信息或透明主体之间的完整互折射。

![Analytic thickness proxy debug: brighter centre, thinner rim](../media/thickness-proxy.png)

上图是厚度代理通道，不是测量得到的真实光程。

![Screen-space refraction against a procedurally generated checker](../media/refraction-debug.png)

棋盘背景用于观察采样偏移；这是本项目的校准画面，不是外部照片。

## 运动与局部接触

弹簧运动描述整体 squash / lean；局部接触层在 contact point 附近产生 dent 和周围 bulge，然后与整体 wobble 组合。参数化 Profile / Preset 用于比较不同外观与响应，不代表物理材料参数拟合。

## 视觉软撕裂与再生

同一网格通过 Shader 位移与 seam 外观模拟 necking、two-lobe separation 与 closing/regeneration。damage / recovery lifecycle 是驱动来源，未生成独立物理碎片或新拓扑。

![Soft-tear debug: partition, seam and regeneration channels](../media/soft-tear-debug.png)

从左到右为 partition、seam、regeneration Debug；它们解释视觉机制，不是连续动态验证。首页 GIF 是另一个 spring-motion 实验，不能替代这一生命周期的完整录像。

## Evidence scope

这些是既有运行捕获的精选副本。原研发记录包含校准对照、局部接触和生命周期记录；本公开入口只重述方法、机制与限制，不发布内部报告或主机日志。未在此宣称 GPU benchmark、真实 SSS、拓扑断裂或 FEM。
