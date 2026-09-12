# Changelog

## v0.1.3

- feat: DataTable 展开行支持——@expand 事件与 headerCell 插槽透传、expandRowByClick 整行热区、展开图标列 40px 定宽并计入强制表宽（ant-design-vue 注入列无宽度，fixed 布局下原会被挤为 0）
- feat: fillWidth 双向自适应——容器宽于列总和拉伸（原行为），窄于列总和时弹性列收缩至 minWidth 内消除横向滚动，最小宽度仍放不下才允许滚动
- fix: 消除两类恒定横向溢出——rowSelection 注入列 32px 计入强制表宽；容器窄于列总和时改由全部非 fixed 可收缩列按 minWidth 迭代分摊，取整误差从最宽列逐列修正保证表宽精确等于容器
- fix: 表头居中规则加 !important——antd cssinjs 对 th 注入 text-align:start 的特异性高于 scoped 编译产物，常规覆盖无效
- perf: package.json 声明 sideEffects 仅样式文件，组件模块可被 bundler tree-shake（同步 monorepo 2bcaecd）

## v0.1.2

- ci: 发布流水线合并——npm 发布成功后统一推送企微通知（内容含 GitHub + npm 双渠道），通知不再早于发布

## v0.1.1

- feat: npm registry 正式上架（@angineer/table-ui）

## v0.1.0

- 首次发布：通用表格组件 DataTable（自 AnGIneer ui-kit 拆分独立）
- 配置驱动筛选栏：input / select（多选）/ radio / switch，`v-model:query` 输出查询条件
- 列宽拖拽 + localStorage 持久化（storageKey）；容器宽度自适应填满（fillWidth / flex 弹性列）
- 卡片容器模式（内置 SectionCard，`card` 可关闭）
- 主题零配置：颜色经 `var(--table-*, var(--语义变量, 默认值))` 双回退，宿主可在 `:root` 覆盖 `--table-*` 单独定制
