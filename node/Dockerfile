# Node 이미지 가져오기
# Docker 위에 NodeJS 가 올라갈 수 있는 것!
FROM node:14.16.1

# Maintainer
MAINTAINER tester<onre-boni@onre.co.kr>

# Set the working directory.
# 작업 디렉토리 명시. 존재하지 않을 경우, 해당 디렉토리를 생성함.
WORKDIR server

# Copy the file from your host to your current location.
# package.json 에 적혀 있는 dependency 가 있는 모듈들을
# 현재 프로젝트 디렉토리에 설치하기 위한 명령어
COPY package*.json .

# Prevent User Interaction
# 컨테이너 실행 중 인터랙션 발생 방지해주는 것
ENV DEVIAN_FRONTEND=noninteractive
# Set Environment to Production
# 주의! production 인 경우 devDependencies 가 설치 되지 않아 NOT FOUND 에러 발생할 수 있음.
ENV NODE_ENV production
# development

# Run the command inside you image filesystem.
RUN npm install
# For production
# RUN npm ci --only=production

# Inform Docker that the container is listening on the specified port at runtime.
# 컨테이너 접속할 때 사용할 포트
EXPOSE 8080

# Run the specified command within the container.
# 설치 종류 후 실행할 명령어
CMD [ "npm", "start" ]

# Copy the reset of your app's source code from your host to your image filesystem.
# Docker 이미지 안에 앱의 소스코드가 복사 되도록 함.
COPY . .