# Changelog

## 0.2.1 — 2026-11-20（本地维护 fork）

- **UI**：「谷时排队」dock 不再横跨整个内容区；宽度改用 DSH composer 的 `--dsh-composer-card-max-width` / side clearance / dock inset 变量，居中收窄到 composer 列内，与内置 QueueDock 的横向留白一致。
- 行为不变；测试仍为 58 例。

## 0.2.0 — 2026-11-19（本地维护 fork）

- **会话级开关**：宿主 `session-prefs.json` 持久化「新会话默认 + 每会话覆盖」；新增 `/prefs`，`/pending` 返回 `prefs`，`/enqueue` 在会话关闭时 409 `session-disabled`。
- **闸门**：有排队（waiting/sending/failed）的会话不能关闭；默认关闭时若有「有排队且无覆盖」的会话则 409。旧版全局 localStorage 开关不再读取。
- **2027 节假日**：`HOLIDAYS_2027`（29 天）合并进 `DEFAULT_HOLIDAYS`（来自上游 PR #3）。
- **设置面板修复**：设置面板/关闭对话框移到 `shell.overlay` 的 `OverlayHost`，不再被 composer 的 transform/filter 盖住。
- **测试**：`clock` 10、`outbox` 19、`gc-refs` 18、`client-inline` 4、`prefs` 7，共 58。
- 兼容：`engines.dsh >=0.2.2-rc.5 <0.3.0`。

## 0.1.1 — 上游基线

- 上游 `@carbonzhao/dsh-offpeak-send@0.1.1`（MIT）：全局 localStorage 开关、outbox 排队、附件落盘、清理、2026 节假日。
