---
title : "[Trouble Shoot] git pull , fetch할때 cannot lock ref:"
date : 2021-07-21
categories : Git
---


git 을 사용하다 cannot lock ref : blabla 라는 Error 가 나며 Pull 이 안되는 상황에 마주쳤다

구글링 해보니 쓰레기값들이 쌓여서 문제가 되는듯 싶었다    

해결방법으로는 git gc 를 사용하는 방법이 있다  

```
$ git gc --prune=now
$ git remote prune origin
```  
  
이걸 사용하면 100이면 99는 해결되는가 싶었는데 한가지 불편한 점이있다  
.git 이있는 path 내부에 git과 관련되지 않은 file 이 있다면 깔끔하게 모두 없애버린다  

예를들면 dll 이라던지 resource file 이라던지 그 path 안에 있고 git에 포함되지 않은 file 이라면 날아가는 듯 싶다  
project 의 userfile 도 날아가서 다시 세팅해주기 귀찮았다 ㅠ
