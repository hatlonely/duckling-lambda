# duckling lambda

在 aws 服务上通过 lambda 部署 facebook 的 duckling 服务

aws 命令工具操作都依赖 aws 访问凭证

```shell
aws configure

AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

## ecr

- `make image`: 制作镜像
- `make push`: 推送到 aws 镜像服务

## cdk

- `cdk bootstrap`: 初始化项目
- `cdk deploy`: 部署服务到 aws
- `cdk destroy`: 资源清理

## sam

通过 sam 部署 duckling lambda，包含镜像制作，使用这个方案可以跳过 ecr 的镜像制作

- `sam init`: 初始化项目
- `sam build`: 构建应用程序
- `sam deploy --guided`: 部署服务到 aws
- `sam delete`: 资源清理

## 参考链接

- facebook duckling: <https://github.com/facebook/duckling>
- aws-lambda-web-adapter: <https://github.com/awslabs/aws-lambda-web-adapter>
