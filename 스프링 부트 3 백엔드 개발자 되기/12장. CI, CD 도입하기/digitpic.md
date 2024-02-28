## CI (Continuous Integration)

- 지속적 통합
- 빌드와 테스트를 자동화

## CD (Continuous Delivery & Continuous Deployment)

- 지속적 제공 & 지속적 배포
- 빌드와 테스트가 성공적으로 진행됐을 때 코드 저장소에 자동으로 업로드
- 병합된 코드 내역을 배포 환경으로 보냄

## 깃허브 액션

- 코드 원격 저장소에 특정 이벤트가 발생하면 특정 작업을 하거나 주기적으로 특정 작업을 반복할 수 있게 한다

## .github/workflows/ci.yml

```
name: CI

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          distribution: 'zulu'
          java-version: '17'
      - name: Grant execute permission for gradlew
        run: chmod +x gradlew
      - name: Build with Gradle
        run: ./gradlew clean build
```

## .github/workflows/cicd.yml

```
name: CI/CD

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          distribution: 'zulu'
          java-version: '17'

      # 실행 권한 주기
      - name: Grant execute permission for gradlew
        run: chmod +x gradlew

      # 빌드
      - name: Build with Gradle
        run: ./gradlew clean build

      # 현재 시간 가져오기
      - name: Get current time
        uses: josStorer/get-current-time@v2.0.2
        id: current-time
        with:
          format: YYYY-MM-DDTHH-mm-ss
          utcOffset: "+09:00"
			
	# 배포용 패키지 경로 저장
	- name: Set artifact
          run: echo "artifact=$(ls ./build/libs)" >> $GITHUB_ENV

	# 빈스토크 배포
	- name: Beanstalk Deploy
          uses: einaregilsson/beanstalk-deploy@v20
          with:
	    aws_access_key: ${{ secrets.AWS_ACCESS_KEY_ID }}
	    aws_secret_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
	    application_name: springboot-developer
	    environment_name: springboot-developer-env
	    version_label: github-action-${{steps.current-time.outputs.formattedTime}}
	    region: ap-northeast-2
	    deployment_pakage: ./build/libs/${{env.artifact}}
```
