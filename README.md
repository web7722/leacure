# WSL2 git 설정하기 

**참고하기**
> http://pinedance.github.io/blog/2021/02/07/WSL-git-keychain


## setting

원격 저장소 설정하기


## 1. .gitignore 알아보기

.gitignore 파일의 역활은
필요에따라. 우리의 git로 관리하는 디렉토리 안에서 
git으로 관리하고 싶지 않은 파일을 만들때 생성합니다.
사용하는방법은 

프로젝트 루트 디렉토리에 .gitignore 파일을 생성합니다.
이후 파일에 

.env 라고 적어보고
프로젝트 폴더 안에서 .env 파일을 생성하고
이후에 PORT=3000이라는 텍스트를 적어봅시다.

혹시 올리고싶지 않은 파일을 github에 올렸다면
삭제를 하고싶을경우..

```
git rm -r [file Name] # 원격 저장소 및 로컬 저장소 파일을 삭제
git rm --cached -r [File Name] # 원격 저장소에 있는 파일 삭제
```

