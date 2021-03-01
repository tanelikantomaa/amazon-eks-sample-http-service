ECR_ENDPOINT := 109716644331.dkr.ecr.eu-west-2.amazonaws.com
ECR_REPO := $(ECR_ENDPOINT)/aws-lb-app

.PHONY: push
push: build
	aws ecr get-login-password --region eu-west-2 | docker login -u AWS --password-stdin $(ECR_ENDPOINT)
	docker push $(ECR_REPO)

.PHONY: build
build:
	docker build -t $(ECR_REPO) .
