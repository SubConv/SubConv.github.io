# 在 Vercel 上部署

## 要求：
- 一个域名（由于 Vercel 的域名被 DNS 污染，因此您需要自己的域名）。不必担心，您可以免费获得域名。  
- 一个 Vercel 账户（我们将会在 Vercel 上部署）  

## 如何获得免费的二级域名
如果您有自己的域名，您可以跳过这一步。  
总共您只需要一个二级域名  
以下是提供免费域名服务的列表：[here](https://free-for.dev/#/?id=domain)  
用 <https://is-an.app>  
首先进入他们的 [仓库](https://github.com/tarampampam/free-domain#show-to-get-one)  
阅读 "How to get one?" 并按照步骤操作  
对于域名的DNS记录，仅需要设置CNAME记录到`cname.vercel-dns.com`  
但是**注意**，您应该将"proxy"设置为false  
<img src="/assets/deploy/vercel_domain.png" width=600rem>  
example: suppose you need `example.is-an.app`  
```json
{
  "$schema": "../schemas/domain.schema.json",
  "description": "<describe your project in this field>",
  "domain": "is-an.app",
  "subdomain": "example",
  "owner": {
    "email": "<your email>"
  },
  "record": {
    "CNAME": "cname.vercel-dns.com"
  },
  "proxy": false
}
```

## 步骤
### Fork 这个仓库
1. Fork [SubConv](https://github.com/SubConv/SubConv)。如果需要ZJU配置，请fork [SubConv-4-ZJU](https://github.com/SubConv/SubConv-4-ZJU)。你可以在新标签页中打开它。
2. （可选）修改配置文件 `config.yaml`。详细配置项请参考[配置](../configuration/overview)

### 部署 SubConv
然后你应该在 Vercel 上部署它，并添加你自己的域名（我称之为 sun-conv 的域名）。如果你熟悉 Vercel，可以跳过这部分。  
  然后登录 Vercel。如果你没有账号，请注册一个。  
  <img src="/assets/deploy/vercel_deploy_1.png" width=600rem>  
  点击 "Add New ..." 按钮，选择 "Project"  
  如果这是你第一次使用 vercel，你将被要求链接到一个 git 服务，选择 GitHub 并完成授权。  
  点击项目右侧的 "import" 按钮，克隆 https://github.com/SubConv/SubConv  
  <img src="/assets/deploy/vercel_deploy_2.png" width=600rem>  
  然后点击 "Deploy" 按钮，等待部署完成。  
  点击 "Continue to dashboard" 按钮，进入仪表盘。  
  点击 "View Domain" 并添加你自己的域名。别忘了根据 Vercel 的指示为你的域名添加 CNAME 记录。  
  <img src="/assets/deploy/vercel_deploy_3.png" width=600rem>  

## 完成
