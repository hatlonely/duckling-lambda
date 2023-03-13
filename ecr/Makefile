NAME ?= duckling-for-lambda
VERSION ?= 1.0.0
AWS_ACCOUNT_ID ?= 864651255535	 # AWS 服务账号
AWS_REGION_ID ?= ap-northeast-2  # AWS 镜像服务地区
REGISTRY ?= ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_REGION_ID}.amazonaws.com

image:
	aws ecr get-login-password --region "${AWS_REGION_ID}" | docker login --username AWS --password-stdin ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_REGION_ID}.amazonaws.com
	docker build -t ${REGISTRY}/${NAME}:${VERSION} .

push:
	docker push ${REGISTRY}/${NAME}:${VERSION}

run:
	docker run -ti --rm -p 9000:8080 ${REGISTRY}/${NAME}:${VERSION}
