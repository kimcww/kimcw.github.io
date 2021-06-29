---
title : "[Trouble Shoot] return type class 를 못찾을 경우"
date : 2021-06-29
categories : Python
---

```python
class A():
    def get(self) -> A: 
        return self
        
    def getB(self) -> B:
        return A.B()
        
    class B():
        def __init__(self):
            pass
```  

![image](https://user-images.githubusercontent.com/42766429/123736700-98080800-d8dc-11eb-8d02-1099fd1694e7.png)


이와 비슷한 상황 처럼  
Class 본인 또는 class 내부에 있는 class정의가 뒤쪽에 있는경우 
return type hint 로 사용할때는 module(A와  B)을 찾지 못해 에러가 난다
interpreter 언어의 특성상 한줄씩 읽어가면서 Class Instance Object 를 만들기 때문에 아직 정의 되지 않은 경우이다

이럴때   
`from __future__ import annotations`  
<br/>  
을 사용하면 forward referencing 을 할 수 있다  
<br/>  

![image](https://user-images.githubusercontent.com/42766429/123737336-c20dfa00-d8dd-11eb-837b-62814f0bb618.png)



C++ 에서 class 전방선언의 확장판이라고 볼수 있겠다  
C++ 에서도 그렇지만 전방선언은 좋은 코딩이라고 볼 수 없다  
임의로 연결고리를 끊으려는 상황에 쓰이기 때문에 구조를 다시 살펴볼 필요가 있다  
