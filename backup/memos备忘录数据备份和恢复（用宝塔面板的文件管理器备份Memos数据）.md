```
memos备忘录，项目地址：[](https://github.com/usememos/memos)

memos部署了很久，看官方的文档，备份和恢复还是无法很好的实现；求助豆包，给了一些方式，验证后总结如下：
```

## 宝塔文件管理器备份 Memos 的正确步骤

### 1. 【必做前提】先停止 Memos 服务 / 容器

这是最关键的一步！

- 如果是 Docker 部署 ：进入宝塔面板 → 软件商店 → Docker → 找到 Memos 容器 → 点击「停止」。
- 如果是 直接部署 ：停止 Memos 对应的进程或服务（比如在终端执行 `sudo systemctl stop memos`）。

> 目的：防止数据库文件被程序占用，导致备份的文件损坏、不完整。

![](https://cdn.jsdelivr.net/gh/ashutouyabo/wangbinrun.github.io@main/images/20260611/1.jpg)

点击“停止”

![](https://cdn.jsdelivr.net/gh/shutouyabo/wangbinrun.github.io@main/images/20260611/2.jpg)

### 2. 找到 Memos 的数据目录

Memos 的所有数据都存在一个目录里，你要找到它：

- 默认路径 ：通常是 `/root/.memos` 或 `/home/你的用户/.memos`
- Docker 部署 ：你可以在容器的「设置」→「目录 / 端口」里，找到你映射的宿主机目录（比如 `/www/memos-data` 这类自定义路径）。

> 这个目录里必须包含 `memos_prod.db` 文件和 `assets` 文件夹，这两个是你的笔记和附件核心数据。

![](https://cdn.jsdelivr.net/gh/shutouyabo/wangbinrun.github.io@main/images/20260611/3.jpg)

### 3. 宝塔文件管理器操作

1. 进入宝塔「文件」面板，找到上面说的 Memos 数据目录。
2. 选中整个 `.memos` 文件夹（或你自定义的 data 目录）。
3. 点击顶部的「压缩」按钮，格式选 `tar.gz`（通用压缩格式，恢复时兼容性最好）。
4. 压缩完成后，你可以把这个压缩包下载到本地电脑，或者复制到服务器的其他目录（比如 `/www/backup`）做异地备份。

![](https://cdn.jsdelivr.net/gh/shutouyabo/wangbinrun.github.io@main/images/20260611/4.jpg)

### 4. 恢复操作（关键！）

1. 再次停止 Memos 服务 / 容器。
2. 把旧的 Memos 数据目录重命名（比如改成 `.memos-old`，防止恢复失败还能回退）。
3. 把你备份的 `.tar.gz` 压缩包上传到服务器，解压成新的 `.memos` 文件夹。
4. 确认解压后的目录里有 `memos_prod.db` 和 `assets` 文件夹。
5. 启动 Memos 服务 / 容器，登录检查笔记和附件是否完整。

### 注意事项 & 避坑指南

1. 必须先停止服务 不停止服务直接复制文件，大概率会导致备份的数据库文件损坏，恢复后笔记丢失或打不开。这是最常见的错误。
2. 必须备份整个目录，不要只复制单个文件 只复制 `memos_prod.db` 会丢失你上传的所有图片 / 附件；只复制 `assets` 文件夹会丢失笔记数据。整个目录打包是最稳妥的。
3. 一定要测试恢复 备份完成后，建议在测试环境里恢复一次，确认数据能正常打开。很多人备份了好几年，到恢复时才发现文件损坏，就白忙活了。
4. 定期做异地备份 只存在服务器上的备份，万一服务器硬盘坏了，数据还是会丢。建议定期把压缩包下载到本地，或者传到网盘 / 其他服务器。

<!-- ##{"timestamp":1781191020}## -->
