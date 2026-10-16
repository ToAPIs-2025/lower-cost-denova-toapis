# Denova 接入说明

这是我们原创的独立API素材示例与接入契约，不是原项目官方Provider，契约JSON也不是已验证可直接导入的上游设置文件。真实API出图/出片与产品内验收分开记录。

上游固定SHA：b7895383d01abb311ba4bf2690dd1249a9156d26

- [internal/image/generation](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/internal/image/generation)
- [config/image_api_profiles.go](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/config/image_api_profiles.go)
- [internal/app/image/generation.go](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/internal/app/image/generation.go)

图片：Bearer鉴权，提交一次并保存id，轮询对应图片generations/{id}，从result.data[0].url下载。不同模型的resolution在顶层或metadata内，不能只改Base URL。

没有核实原项目的视频模型入口；当前仅图片素材路线，不虚构视频Provider。

接入后检查：模型目录与选项 → 提交/防重复 → 重启恢复查询 → 保存原始图片或视频 → 原界面导入和展示 → 费用核对。现阶段完整原生界面未验收。
