# MyUnderstandingOfConcurrency

# MyUnderstandingOfConcurrencyModels
나는 다음과 같이 concurrency model들을 이해하고있다.  
1. traditional function call
2. event(=task) loop (non-blocking 연산들만을 가진 task(=lambda)들을 처리)
3. job processing (blocking 연산을 가진 job(=lambda)들을 처리)

### 1. traditional function call 개념도
일반적인 OS thread의 동작을 의미함.
`여기서 context-switch 비용이 거의 없어지고, thread별 stack size가 on-demand(dynamic)인 것 = java virtual thread`로 이해하고 있다.


![thread-diagram-v1](https://github.com/user-attachments/assets/4352a524-92aa-499b-ad14-d6005b8da2f9)

### 2. event loop 개념도
reactor와 같은 reactive programming의 concurrency model을 event loop으로 이해하고 있다.
가령, reactive-streams의 signal(=onNext, onError, onComplete, ...)(=marble diagram의 circle(onNext)들이나 |(onComplete), X(onError)들)이 하나의 event(lambda)이다.

![event-queue-diagram-v1](https://github.com/user-attachments/assets/84d3cb79-5aae-425c-b3bd-9a190e049d37)

### 3. job processing 개념도
tomcat과 같은 thread per request의 concurrency model을 job processing으로 이해하고 있다.
`여기서 context-switch 비용이 거의 없어지고, thread별 stack size가 on-demand(dynamic)인 것 = java virtual thread`로 이해하고 있다.

![job-queue-diagram-v1](https://github.com/user-attachments/assets/39174976-2c50-4439-9d0b-8d912cd6bdc0)

## 참고자료
https://eherrera.net/project-reactor-course/




