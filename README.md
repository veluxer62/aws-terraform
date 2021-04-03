# 테라폼 설정

해당 설정은 Mac OS를 기준으로 작성되었습니다.

## AWS 회원가입

[https://portal.aws.amazon.com/billing/signup#/start](https://portal.aws.amazon.com/billing/signup#/start) 링크를 통해 가입

## 계정 생성

Root 계정을 사용하지 않고 IAM에서 `terraform` 계정을 생성한 후 해당 계정으로 Terraform을 실행합니다.

Access Type은 `Programmatic access`으로 설정합니다.

계정의 권한은 본인이 사용할 인스턴스에 맞도록 주는게 맞으나 편의를 위해 `AdministratorAccess`를 사용합니다.

생성이 완료되면 Access Key가 발급되는데 해당 키 파일은 저장해 둡니다. (잊어버리면 다시 만들어야 하니 관리에 주의를 기울이세요.)

## AWS CLI 설정

AWS CLI 설치

```bash
brew install awscli
```

## AWS 계정 크리덴셜 추가

```bash
aws configure --profile <profile-name>
```

아래 프롬프트가 뜨면 값을 입력해주면 됩니다.

```bash
AWS Access Key ID [None]: <ACCESS-ID>
AWS Secret Access Key [None]: <SECRET-KEY>
Default region name [None]: us-northeast-2
Default output format [None]: json
```

## 환경변수 추가

```bash
export AWS_ACCESS_KEY_ID=<ACCESS-ID>
export AWS_SECRET_ACCESS_KEY=<SECRET-KEY>
```

환경변수 확인

```bash
env | grep AWS
```

## 테라폼 설치

```bash
brew install terraform
```

버전 확인

```bash
terraform version
```

프로젝트 초기화

```bash
terraform init
```

## 키페어 생성

```bash
$ ssh-keygen -t rsa -b 4096 -C "<EMAIL_ADDRESS>" -f "$HOME/.ssh/web_admin" -N ""
```