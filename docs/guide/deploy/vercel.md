# Deploy on Vercel

## Requirements:
- your own domain (the DNS resolution of vercel's domain is polluted so you have to use your own domain). Don't be worried about this, you can get one for free.  
- a vercel account (we will deploy on vercel)  

## How to get a free subdomain
If you have your own domain, skip this.  
In total you need only 1 subdomains  
Here is a list of services that provide free domains: [here](https://free-for.dev/#/?id=domain)  
Take <https://is-an.app/> for example  
First go to their [repo](https://github.com/tarampampam/free-domains#how-to-get-one)  
Read "How to get one" and follow the instruction. 
As for `"record"`, you should only set `"CNAME"` to `"cname-china.vercel-dns.com"`  
But **notice** that you should configure "proxy" to false  
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

## Steps
### Fork this repo
1. Fork [SubConv](https://github.com/SubConv/SubConv). If you need ZJU's configuration, fork [SubConv-4-ZJU](https://github.com/SubConv/SubConv-4-ZJU). You can open it in a new tab.
2. (optional) modify the configuration file `config.yaml`. For detailed configuration items, please refer to [Configuration](../configuration/overview)

### Deploy SubConv
Then you should deploy this on Vercel and add you own domain (I call this **sun-conv's domain**). If you are familiar with Vercel, go ahead and skip this part.  
  Then log in [Vercel](https://vercel.com). If you don't have an account plz register one.  
  <img src="/assets/deploy/vercel_deploy_1.png" width=600rem>  
  Click "Add New ..." button and choose "Project"  
  Then if it's the first time to use vercel, you'll be asked to link to a git service, choose GitHub and finish the authorization.  
  Click the "import" button at the right of the project you clone  https://github.com/SubConv/SubConv/
  <img src="/assets/deploy/vercel_deploy_2.png" width=600rem>  
  Then click the "Deploy" button and wait until deploy is completed.  
  Click the "Continue to dashboard" button and get into dashboard.  
  Click "View Domain" and add your own domain. Don't forget to add a CNAME record according to vercel's instruction to your domain.  
  <img src="/assets/deploy/vercel_deploy_3.png" width=600rem>  
  
## Finish
