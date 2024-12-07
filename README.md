# :envelope: 뿌려뿌려 - Front
팀 블루프린트의 본 웹 서비스 "뿌려뿌려"는 뿌리오 기업과 연계하여 생성형 AI를 활용한 포토문자 서비스 어플리케이션입니다. 

<br/>

## :bulb: 주요 기능
- 문자 생성 : LLM모델로 OpenAi의 gpt-4o를 이용하여 해당 사용자의 니즈에 맞는 텍스트 기반의 메세지를 생성할 수 있습니다.
- 이미지 생성 : OpenAi의 DALLE-3를 이용하여 사용자가 입력한 조직, 분위기에 맞는 이미지를 생성할 수 있습니다.
- GIF 생성 : OpenAi의 DALLE-3를 이용하여 사용자가 희망하는 확대, 축소, 스위치, 애니메이션 GIF 종류를 선택하여 생성할 수 있습니다.
- 문자 발송 : 뿌리오 기업에서 제공받은 API를 이용하여 문자, 이미지, GIF(URL)을 여러 사람들에게 일괄 발송할 수 있습니다.

<br/>

### ec2 public ip 주소 : 13.239.36.154
<br/>

## 👉🏻 실행 방법
1. vscode에 FrontEnd 폴더 불러오기
2. vscode에서 터미널 켜기
3. 빌드 명령어: npm run build
4. git bash에서 AWS로 빌드폴더 보내기 : scp -r -i ${본인 ec2 키 경로} ${ec2에 보낼 파일의 경로} ec2-user@13.239.36.154:/home/ec2-user/app
<br/>예시: scp -i "D:\24-2\SWFreeCapston_8\private_key_woojj1254577.pem" "D:\24-2\SWFreeCapston_8\Back\precapston\build\libs\precapston-0.0.1-SNAPSHOT.jar" ec2-user@13.239.36.154:/home/ec2-user/app<br/>(4번 명령어는 내 노트북 말고 다른 곳에서 쓰려면 scp -r -i 다음에 pem key 경로, build 파일 경로, ec2 어디에 보낼건지 경로 적어주면 됩니다.)
5. EC2 접속하기(putty, git bash) -> ssh -i ${pem 키 경로}ec2-user@${public ip 주소}
6. 접속하면 처음 위치: /home/ec2-user
7. app 디렉토리로 이동: cd app
8.  프론트 실행 전: pm2 kill
9. 프론트 실행: pm2 serve build/ 3000 --spa
10. 백 실행(실행 방법은 BackEnd의 README.md에 있음)
11. 웹에서 13.239.36.154:3000 접속하여 서비스 확인
### 이 후로는 종료 과정
12. 프론트 종료: pm2 kill
 
<br/>

## ⭐.gitignore 파일
<details>
<summary>.gitignore 파일 내용</summary>

 ```
 # See https://help.github.com/articles/ignoring-files/ for more about ignoring files.

# dependencies
/node_modules
/.pnp
.pnp.js

# testing
/coverage

# production
/build

# misc
.DS_Store
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log*


```

</details>


## 📝 Composition
<details>
<summary>메인 페이지</summary>
<div markdown="1">
  <br/>
기본 <br/>
<img width="580" alt="메인화면" src="https://github.com/user-attachments/assets/c0540202-f61a-4649-a118-71378fc10855">
<br/><br/>
문자 <br/>
<br/><br/>
문자 + 이미지 <br/>
<img width="580" alt="문자 + 이미지" src="https://github.com/user-attachments/assets/e49228d1-a3dd-4bda-b266-faf0cddcf7f2">

<br/><br/>
문자 + gif <br/>
<img width="580" alt="문자 + gif" src="https://github.com/user-attachments/assets/3c8fe825-9ffd-403c-a0d1-be9d592dd26c">


</div>
</details>

<details>
<summary>AI 문자 생성 팝업</summary>
<div markdown="1">
<br/>
AI 문자 생성 탭
<br/>
<img width="600" alt="AI 문자 생성 탭" src="https://github.com/user-attachments/assets/1d63c8b2-5a60-4a61-a064-b71bb51c4eec">
<br/><br/>
문자 생성 결과
<br/>
<img width="580" alt="문자 생성 결과" src="https://github.com/user-attachments/assets/1d192585-95ca-411b-bdc9-e1afdff7b661">


</div>
</details>
<details>
<summary>AI 이미지 생성 팝업</summary>
<div markdown="1">
<br/>AI 이미지 생성 탭<br/>
<img width="602" alt="AI 이미지 생성 탭" src="https://github.com/user-attachments/assets/556280ca-a1f4-4efb-94f0-cb75e40f52c0">
<br/><br/>이미지 생성 결과<br/>
<img width="602" alt="이미지 생성 결과" src="https://github.com/user-attachments/assets/bc8e5bbe-b548-4ca9-a929-fe386643d30d">


</div>
</details>
<details>
<summary>AI GIF 생성 팝업</summary>
<div markdown="1">
<br/>AI gif 생성 탭<br/>
<img width="580" alt="AI gif 생성 탭" src="https://github.com/user-attachments/assets/5213d988-2e34-4668-9259-ec3309c1585f">
<br/><br/>gif 생성 결과<br/>
<img width="580" alt="gif 생성 결과" src="https://github.com/user-attachments/assets/35c8f5d4-8812-490d-b62c-b541705dfd63">


</div>
</details>
<details>
<summary>로그인 페이지</summary>
<div markdown="1">
<br/>로그인 화면 <br/>
<img width="580" alt="로그인화면" src="https://github.com/user-attachments/assets/0d400beb-ab3b-458a-ba35-5ebb7d0d6c05">

</div>
</details>
<details>
<summary>회원가입 페이지</summary>
<div markdown="1">
<br/>회원가입 화면 <br/>
<img width="580" alt="회원가입화면" src="https://github.com/user-attachments/assets/8210164b-f89e-45d4-b953-ad648b481529">

</div>
</details>
<details>
<summary>마이 페이지</summary>
<div markdown="1">
<br/>마이페이지 화면 <br/>
</div>
</details>

<br/>

## 💻 Teachnology
![js](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white)
![html](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![css](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![react](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)

![visual studio code](https://img.shields.io/badge/Visual_Studio_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)
![Notion](https://img.shields.io/badge/Notion-%23000000.svg?style=for-the-badge&logo=notion&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)
![Github](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)

<br/>

## ✏️ 잘 나온 GIF들
[노션 소개페이지](https://www.notion.so/b44fcc8ccca34346ba369bee6098a83b)
