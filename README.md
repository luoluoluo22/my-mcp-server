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

点击前往github[申请开发者OAuth Apps](https://github.com/settings/developers)，获得
GITHUB_CLIENT_ID和GITHUB_CLIENT_SECRET，在.dev.vars文件中进行替换
```bash
npm run start
```

另外启动一个终端运行：
```bash
npx @modelcontextprotocol/inspector@latest
```
启动后在网页打开网页http://localhost:5173，输入mcp服务
http://localhost:8787/sse
