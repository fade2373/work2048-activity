# 数字实验室 2048

一个纯单文件 HTML 的 2048 小游戏，零依赖、零构建，双击即可运行。

## 功能

- 4×4 棋盘，方向键与触摸滑动双向操作
- 相同数字合并、翻倍计分，实时显示得分与历史最佳
- 无法移动时自动判定结束，合成 2048 触发通关提示
- 进度自动保存到 localStorage，刷新后继续上一局
- 响应式布局，适配 PC 与移动端

## 技术要点

单文件 `index.html`，CSS/JS 全部内联；无 npm、无打包、无外部依赖。
核心逻辑集中在 `mergeLine`（单行合并）与 `calculateMove`（四方向变换），
状态收敛在 `cells` 数组里，渲染走一次 `render()`，便于推理和测试。

## 运行

直接用浏览器打开 `index.html`，或起一个静态服务：

```bash
python3 -m http.server 20480
```

## 部署

已部署于华为云 ECS（Huawei Cloud EulerOS 3.0 + Nginx 1.24），
公网地址 http://116.205.127.248/hc-activity/index.html
