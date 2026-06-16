<div align="center">

<img src="https://github.com/user-attachments/assets/a252453c-bed2-4044-aa24-edd13f4ca431" width="120" height="120" alt="易下载 EasyDownload" />

# 易下载 EasyDownload

**把微信公众号文章「搬」到本地的小工具**

支持单篇、批量、监控、公众号平台四种下载方式，导出 HTML / Markdown / PDF，图片音频评论一并带走，还能顺手存进 MySQL。

[![GitHub stars](https://img.shields.io/github/stars/yangbuyiya/easyDownload?style=flat&color=gold)](https://github.com/yangbuyiya/easyDownload)
[![GitHub downloads](https://img.shields.io/badge/downloads-2231-blue?style=flat)](https://github.com/yangbuyiya/easyDownload/releases)
[![GitHub issues](https://img.shields.io/github/issues/yangbuyiya/easyDownload)](https://github.com/yangbuyiya/easyDownload/issues)
[![Website](https://img.shields.io/badge/官网-easydownload-blue?style=flat)](https://easy-wechat-download.vercel.app/)

</div>

---


## 软件预览

<img width="1536" height="1024" alt="主界面" src="https://github.com/user-attachments/assets/f97fa490-d29c-4596-88ff-157704ab1d2d" />

## 下载

到 [Releases](https://github.com/yangbuyiya/easyDownload/releases) 拿最新版。

- Windows：下载 `.exe` 双击安装
- macOS：下载 `.dmg` 拖进「应用程序」。提示「无法验证开发者」时，到访达里右键选「打开」即可

## 四种下载方式，挑顺手的用

| 方式 | 适合场景 | 稳定性 |
|------|---------|--------|
| **公众号平台模式** | 想稳定拉取某个公众号的历史文章 | ⭐⭐⭐⭐⭐ 推荐 |
| **单篇下载** | 只存一两篇 | ⭐⭐⭐⭐⭐ 最稳 |
| **监控下载** | 手动挑几篇，不要整号 | ⭐⭐⭐⭐ |
| **批量下载（代理）** | 想代理抓包，但不保证稳 | ⭐⭐ 看运气 |

> **代理批量下载老是抓不到文章？直接换「公众号平台模式」，扫码登录就能用，不用代理、不用装证书。**

---

## 公众号平台模式（推荐）

不依赖本地代理，不走抓包，直接通过微信公众平台接口拉取历史文章列表。**代理模式不稳定的，用这个。**

### 第一次用：先登录

1. 进「系统设置」→「公众平台登录」
2. 点「扫码登录」，弹出二维码
3. 用**公众号管理员**微信扫码，手机上确认登录
4. 状态变成「已登录」就行，凭证保留 4 天，过期重新扫

### 然后下载

1. 进侧边栏「公众号下载」
2. 先选下载范围（今天 / 近 7 天 / 近 1 个月 / 自定义）
3. 搜索框输入公众号名称，回车
4. 点搜索结果里的目标公众号
5. 软件自动翻页拉取该公众号的历史文章列表
6. 勾选你想要的，或者一键全选
7. 点下载，任务中心实时看进度

> 碰到「历史列表接口被限制」是微信频控（ret=200013），已获取的文章会保留。先把已有的下了，缩小范围、调大间隔再试。

---

## 单篇下载

最简单，适合只存一两篇。

1. 复制微信文章链接
2. 粘贴到首页输入框
3. 点「下载文章」

## 监控下载

适合手动挑几篇，不想要整个公众号的历史。

1. 点「开始监控」，按钮变色说明在盯着了
2. 在电脑版微信里一篇篇打开你要的文章
3. 每抓到一篇，日志区会打印文章 `mid`
4. 都打开完了，再点一次按钮停止
5. 软件自动下载这些文章

## 批量下载（代理模式）

> ⚠️ 这个模式依赖代理抓包，稳定性看微信脸色。**抓不到就换公众号平台模式。**

1. 「系统设置」里装好代理证书并信任（第一次才需要）
2. 确认电脑版微信已登录
3. 回首页点「批量下载」，软件启动代理并开始 60 秒倒计时
4. 在电脑版微信里打开目标公众号主页，**强制刷新一下**（Ctrl+R / Cmd+R）
5. 随便点开该公众号的一篇文章，让微信重新发起请求
6. 回到软件，弹出确认框点「确定」
7. 等它自己跑完

> 60 秒内没监听到请求，代理会自动关闭。抓不到的话，优先回公众号主页刷新再点文章；macOS 上尤其容易因为缓存不重新请求。

---

## EPUB 电子书

1. 侧边栏进「创建电子书」
2. 填书名，选已下载文章的文件夹（HTML 或 Markdown 都行）
3. 想要封面图就加一张
4. 点「开始生成」

## 系统设置

| 配置 | 说明 |
|------|------|
| 保存路径 | 文章存到哪 |
| 缓存路径 | 临时文件的家 |
| 导出格式 | HTML / Markdown / PDF，可多选 |
| 资源选项 | 图片、音频、评论、元数据、原文链接，按需勾选 |
| 下载间隔 | 每篇之间的等待毫秒数，建议 1000 起 |
| 单批数量 | 一批并发处理几篇，网络不稳就调小 |
| 下载范围 | 今天 / 近 7 天 / 近 1 个月 / 自定义 |
| 公众平台登录 | 扫码登录，用于公众号平台模式 |
| MySQL | 数据库连接配置，建表 SQL 在 [doc/mysql.sql](doc/mysql.sql) |

### 线程模式

- **单线程**：一篇下完再下一篇，稳但慢
- **多线程**：按间隔并发起跑，快但容易触发风控

新手建议单线程 + 1000ms 间隔起步。

## 任务中心

下载过程中，任务中心实时展示：

- **进度面板** — 总数、下载中、成功、失败、跳过，一目了然
- **失败重试** — 有失败项？一键重试，不用整个重来
- **导出报告** — 下载完可以导出任务报告，方便对账

## 过滤规则

不想全收？用 JSON 写个规则，按标题或作者筛。

只要标题带「好人」、作者是「张三」的：

```json
{
  "title": { "include": ["好人"] },
  "auth": { "include": ["张三"] }
}
```

标题里带「广告」或「推广」的统统不要：

```json
{
  "title": { "exclude": ["广告", "推广"] }
}
```

---

## 常见问题

<details>
<summary>批量下载（代理）一直抓不到文章</summary>

**直接换「公众号平台模式」，扫码登录就能用，不折腾代理。**

如果还想用代理模式，依次检查：
1. 证书装了而且信任了
2. 用的是电脑版微信，不是浏览器或手机
3. 点了批量下载之后，强制刷新公众号主页（Ctrl+R / Cmd+R），再点开文章
4. 没有 VPN、安全软件抢了系统代理
5. 还不行就退出微信和软件重开
</details>

<details>
<summary>公众号平台模式提示「接口被限制」</summary>

这是微信频控（ret=200013）。已获取的文章会保留，先把已有的下了。后续缩小下载范围、调大下载间隔、降低单批数量，等一段时间再试。
</details>

<details>
<summary>下载时跳出验证页 / 正文提取失败</summary>

典型的风控表现。停一会儿再试，把下载频率降下来。代理模式遇到这种情况建议直接切公众号平台模式。
</details>

<details>
<summary>PDF 导出特别慢</summary>

PDF 要开隐藏窗口渲染 HTML 再打印，天生比 HTML / Markdown 慢。批量的时候建议先关掉 PDF，等内容确认没问题再单独导。
</details>

<details>
<summary>下载完电脑上不了网</summary>

代理没恢复。先点「恢复网络」。还不行就关掉软件，手动检查系统代理设置，或者重启电脑。

公众号平台模式不走代理，不会有这个问题。
</details>

<details>
<summary>macOS 提示「无法验证开发者」或「应用已损坏，无法打开」</summary>

由于 macOS 的安全机制，非 App Store 下载的应用会触发此提示。当前开源发布流程尚未接入 Apple Developer ID 签名和公证，因此部分系统版本会显示更严格的 Gatekeeper 提示。

**方法一：命令行修复（推荐）**

打开终端，执行以下命令：

```bash
sudo xattr -rd com.apple.quarantine "/Applications/EasyWechatDownload.app"
```

> 如果你修改了应用名称，请在命令中相应调整路径。

**方法二：系统设置**

在「系统设置」→「隐私与安全性」中点击「仍要打开」。

**方法三：访达右键**

<img width="520" height="496" alt="macOS 提示" src="https://github.com/user-attachments/assets/f2fcf3b1-4864-45f2-9373-c5cf482cde69" />

到访达里右键选「打开」就行。

<img width="1840" height="872" alt="访达右键打开" src="https://github.com/user-attachments/assets/921f93fa-ba64-4786-9e03-a4a01c44c798" />
</details>

---

## 关注 & 加群

备注「易下载」加群交流。

<div style="display: flex; justify-content: space-between; margin-bottom: 20px;">
  <img src="https://foruda.gitee.com/images/1779462265406893356/45d8567c_5151444.jpg" width="30%" alt="加群"/>
  <img src="https://github.com/user-attachments/assets/d35dd840-b16e-47e1-a26e-39643a3eb86d" width="30%" alt="公众号二维码"/>
</div>

> 公众号「程序员不易」，欢迎来聊技术。

## 问题反馈

- 用着有问题 → 提 [GitHub Issues](https://github.com/yangbuyiya/easyDownload/issues)
- 想唠嗑交流 → 微信找我
- 想深度合作 → 微信私信

## 📢 免责声明
1. 本软件仅供学习交流，严禁用于商业用途
2. 使用本软件请遵守相关法律法规，由违规使用导致的任何问题与作者无关
3. 下载的内容请勿传播,下载的内容仅供个人学习归档，仅供个人学习使用
4. 如有侵权请联系作者删除

