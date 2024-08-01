# roim-picx 

### 一款基于Cloudflare的Worker、R2、Pages实现的图床应用，具有以下特点：

* 10GB的免费存储空间
* 每月300W次的不计流量的图片访问，每天10W的限制。
* 每月100W次的图片上传次数
* 不需要自己购买服务器，克隆代码后部署CloudFlare即可使用。
* 独立部署不需要担心被第三方删除数据。

### 已实现功能

* 图片批量上传
* 图片列表查询
* 图片删除
* 目录创建
* 按目录查询
* 链接地址点击复制
* 简单的身份认证功能，进入管理页面需要授权

### 使用教程-修改了readme

1. fork项目到自己的github  
2. 创建Page项目  
3. 输入编译参数  
  3.1 框架预设：无  
  3.2 构建命令：`npm run build`  
  3.3 输出目录：`dist`   
4. 完成创建  
5. 设置环境变量 {Workers和Pages} —— {设置} —— {环境变量}  
  5.1 `AUTH_TOKEN`：授权码(管理密码 —— 可自定义)  
  5.2 `COPY_URL`：`page域名/rest` 或 R2域名 `https://********.r2.dev` (末尾不加/)  
6. 绑定R2 {Workers和Pages} —— {设置} —— {函数} —— {R2 存储桶绑定}  
  6.1 `R2`：选择创建的R2存储桶  
7. 重新部署  

### 可选 修改R2 CORS 策略 允许所有
```
[
  {
    "AllowedOrigins": [
      "*"
    ],
    "AllowedMethods": [
      "GET",
      "POST",
      "PUT",
      "DELETE",
      "HEAD"
    ],
    "AllowedHeaders": [
      "*"
    ]
  }
]

```
---

项目fork自[roimdev/roim-picx](https://github.com/roimdev/roim-picx)  
项目导入自[liangliangle/roim-picx](https://github.com/liangliangle/roim-picx)  
原文链接[使用R2+Page部署免费的图床](https://blog.lianglianglee.com/posts/22b7ecba)  
