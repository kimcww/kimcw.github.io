---
title : "[Qt] Connection type"
date : 2021-07-19
categories : Qt
---

view 는 사라지고 model은 view 에 뭔가 업데이트 하려는 상황을 마주했을때  
queuedConnection 을 알게되었는데  
좋은 해결책은 아니었다  
그래도 간단히 개념을 정리해 놔야겠다  
<br/>  

[Qt Connection Type](https://doc.qt.io/qt-5/qt.html#ConnectionType-enum)

### Qt::AutoConnection  
---
수신기( 받는쪽이 ) 송신(신호를 내보내는) Thread 에 있는경우 Qt::DirectConnection 이 사용됨, 그렇지 않으면 Qt::QueuedConnection이 사용됨  
<br/>  

### Qt::DirectConnection  
---
slot 은 신호가 방출(emit) 되는 즉시 호출된다, slot 은 신호가 발생한 thread 에서 실행된다  
<br/>  

### Qt::QueuedConnection
---
수신기 Thread 로 반환 될때 slot이 호출된다  
다른 Thread 에서 작업을 하다가 다시 수신기 thread 에서 작업을 할때 slot을 호출해 준다는 의미로 보임
<br/>  
  
### Qt::BlockingQueuedConnection
---
slot이 반환될 때까지 signal thread 가 차단됨
나머지 기능은 Qt::QueuedConnection 이랑 같음
<br/>  

### Qt::UniqueConnection
---
비트 연산을 사용해서 위의 connection 과 결합할 수 있다
동일한 신호가 동일한 slot에 연결되어 있는경우 connect가 실패한다
중복 connection 을 막아주는 역할을 한다





