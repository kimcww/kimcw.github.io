---
title : "PQXXLibrary"
date : 2021-05-26
categories : PostgreSQL
---


# int PQconsumeInput()  
### return 1 is okay , 0 is Error
---
싱크를 맞추기 위해 데이터를 받기전에 호출 해줌으로써 이전에 있는 select 검사 조건을 다 지워줌  
이후에 Result 를 얻으면 바로 값을 정확하게 얻을 수 있다
