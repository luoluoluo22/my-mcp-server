# remote-mcp-github-oauth

这个仓库用于学习使用，仓库看教程
[开发一款支持OAuth认证的Cloudflare MCP服务器 - MCP商业化的关键一步](https://www.bilibili.com/video/BV11RZMYnECi/?vd_source=0eaa8407ec8edd1e9f2a0abf6e126bf6)
因为觉得配置麻烦，不想要其它人再重复配置一边，所以仓库供大家参考使用


## Develop locally

```bash
# clone the repository
git clone https://github.com/luoluoluo22/my-mcp-server.git

cd my-mcp-server
npm install
```

## 环境变量配置

1. 首先，复制示例配置文件：
```bash
cp .dev.vars.example .dev.vars
```

2. 配置 GitHub OAuth 应用：
   - 点击前往 GitHub [申请开发者OAuth Apps](https://github.com/settings/developers)
   - 点击 "New OAuth App" 创建新应用
   - 填写应用信息：
     - Application name: 自定义名称
     - Homepage URL: `http://localhost:8787`
     - Authorization callback URL: `http://localhost:8787/callback`
   - 创建完成后，你会获得：
     - Client ID
     - Client Secret（点击 "Generate a new client secret" 生成）

3. 编辑 `.dev.vars` 文件，将获得的凭证填入对应位置：
```env
GITHUB_CLIENT_ID="你的Client ID"
GITHUB_CLIENT_SECRET="你的Client Secret"
```

4. 启动服务：
```bash
npm run start
```

5. 另外启动一个终端运行：
```bash
npx @modelcontextprotocol/inspector@latest
```

6. 启动后在网页打开：
   - Inspector界面：http://localhost:5173
   - 在界面中输入 MCP 服务地址：http://localhost:8787/sse

## 注意事项

- `.dev.vars` 文件包含敏感信息，已添加到 `.gitignore` 中，请勿提交到代码仓库
- 本地开发时请确保 8787 端口未被占用
- 如遇到 OAuth 相关错误，请检查配置的 Client ID 和 Secret 是否正确
