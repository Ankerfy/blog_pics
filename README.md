# 📷 GitHub 自用图床使用说明

> 本仓库作为个人图床使用，通过 [PicGo](https://github.com/Molunerfinn/PicGo) 工具实现一键上传图片到 GitHub 仓库，方便快捷地管理图片资源。

---

## 📌 用途说明

本仓库用于存储用户上传的图片资源，适用于博客、笔记、文档、聊天等场景中的图片外链需求。通过 GitHub + PicGo 搭建个人图床，可以：

- ✅ 免费使用
- ✅ 稳定可靠
- ✅ 支持 Markdown 图片语法
- ✅ 快捷上传（支持拖拽、剪贴板等）

---

## 🛠️ 配置步骤

### 1. 准备工作

- ✅ GitHub 账号（如果没有，请先注册）
- ✅ 创建一个空的 GitHub 仓库（例如：`image-bed`）
- ✅ 安装 [PicGo](https://github.com/Molunerfinn/PicGo/releases)（推荐使用最新版本）

---

### 2. 获取 GitHub Token

GitHub 从 2021 年起不再支持使用用户名密码进行 API 操作，因此你需要创建一个 Personal Access Token。

#### 创建 Token 步骤

1. 打开 GitHub → 右上角头像 → `Settings`
2. 左侧菜单选择 `Developer settings` → `Personal access tokens` → `Generate new token`
3. 勾选权限：
   - `repo`（用于访问私有/公开仓库）
   - `public_repo`（如果你的图床仓库是公开的）
4. 设置 Token 的过期时间（建议选择合适的有效期）
5. 点击 `Generate token`
6. **复制生成的 Token**（只显示一次，务必保存好）

---

### 3. 配置 PicGo

1. 打开 PicGo 软件
2. 点击左侧 `图床设置` → 选择 `GitHub图床`
3. 填写以下信息：

| 字段 | 示例 | 说明 |
|------|------|------|
| `token` | `ghp_xxxxxxxxxxxxxxxxxxxxxx` | 刚刚生成的 GitHub Token |
| `仓库名` | `username/image-bed` | 替换为你的 GitHub 用户名和仓库名 |
| `分支名` | `main` 或 `master` | 通常为 `main` 或 `master` |
| `路径` | `img/`（可选） | 图片上传到仓库中的哪个文件夹下 |
| `自定义域名` | `https://cdn.jsdelivr.net/gh/username/image-bed@main/`（可选） | 可通过 jsDelivr 加速访问 |

4. 点击 `测试上传`，成功则说明配置无误。

---

### 4. 设置快捷上传方式（可选）

- **截图上传**：可在 PicGo 设置中开启截图上传快捷键（默认 `Ctrl + Shift + P`）
- **拖拽上传**：直接将图片拖入 PicGo 窗口即可上传
- **剪贴板上传**：按下快捷键即可上传剪贴板中的图片

---

## 📎 使用说明

上传成功后，PicGo 会自动将图片链接复制到剪贴板，格式如下：

```
![图片名称](https://cdn.jsdelivr.net/gh/username/image-bed@main/img/图片名称.png)
```

你可以直接粘贴到 Markdown、博客、文档中使用。

---

## ⚠️ 注意事项

- GitHub 免费账户的图床访问速度取决于 CDN（如使用 jsDelivr），请合理使用。
- 图片命名请避免重复，PicGo 默认使用时间戳命名，建议保留默认设置。
- 不建议上传敏感或隐私图片。
- GitHub 仓库建议设为 `public`（公开仓库），否则需要 Token 有对应权限。

---

## ❓ 常见问题

### Q：上传失败提示 `403` 或 `404` 怎么办？

- A：检查 Token 是否正确、仓库名是否填写完整（格式为 `username/repo`）、分支是否正确。

### Q：图片无法访问？

- A：检查仓库是否为公开仓库；若使用 jsDelivr，请确认路径是否正确（如 `img/xxx.png`）。

### Q：如何更换图床？

- A：PicGo 支持多种图床（如 SM.MS、腾讯云、阿里云、七牛云等），可在设置中切换。

---

## 📚 参考链接

- [PicGo 官方文档](https://picgo.github.io/PicGo-Doc/)
- [GitHub Personal Access Token 教程](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [jsDelivr CDN 加速 GitHub 图片](https://www.jsdelivr.com/github)
