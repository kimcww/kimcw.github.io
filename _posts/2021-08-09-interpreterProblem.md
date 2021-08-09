---
title: "[Trouble Shoot] Pycharm, cannot run program"
date : 2021-08-09
categories : Trouble Shoot
---

1PC에서 실행 되던 프로젝트가 
2PC에서는 실행 되지 않았다  
같은 버전의 IDE 와 interpreter 를 사용했다  
에러 메세지는 아래와 같이 나왔다  
<br/>  

![image](https://user-images.githubusercontent.com/42766429/128696222-cfc9b70a-aa56-41df-9c4e-be4fb84e7223.png)  
  
인터넷엔 Interpreter 가 제대로 설정되지 않아서 이런 문제가 발생한다고 했다  
근데 내 interpreter 는 너무 잘 설정되어있다  
  
`진짜 문제는 PC1의 path 의 interpreter 를 접근하려고 하는 시도를 했다  `


PC2 는 PC1의 존재 조차 모르는데 PC1의 절대 경로를 알고 있는게 이상했다  
그래서 다시 보니 Project에 cache 부분이 있다!!  
  
![image](https://user-images.githubusercontent.com/42766429/128697959-1d4b3072-e8d4-4e74-a583-6738d027e228.png)  
  
아마 이게 문제일거라 생각이 되어 지웠더니 문제 없이 된다  
대신에 캐시 지우고 IDE 를 다시 켜줘야 된다  
.idea, __pycache__ 두개를 지워주면 된다  
내가 설정한 interpreter 에 잘 접근한다  

