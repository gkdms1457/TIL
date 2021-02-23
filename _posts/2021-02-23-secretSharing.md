---
title : shamir's secret sharing
category :
    - cryptography
tag :
    - cryptography algorithm
    - shamir
    - secret sharing
---

secret-sharing의 종류 중 하나

비밀을 여러 부분으로 나누어 각 참가자에게 고유한 부분을 부여하는 방식

---
## shamir's scheme

 2개의 점으로 직선정의 가능, 3개의 점으로 포물선 정의가능, 4개의 점으로 3차 곡선 정의 가능하다는 것이 Adi Sharmir scheme의 핵심 아이디어이다.  
 즉, n차 다항식의 계수를 알기 위해서는 n+1개의 점이 필요하다는 것이 이 아이디어의 핵심인 것이다.  
 ![shamir's secret sharing](/TIL/assets/images/shamir.PNG)
 
 위의 사진처럼 5차 다항식이 있을 때, 그 직선위의 점이 최소 6개 있어야 해당 식을 알 수 있다. 만약 6개보다 적게 알고 있다면 원래의 다항식은 알 수  없다.  
 이를 통해 
 1. 비밀값 1개, 비밀값을 복구할 수 있는 키를 나누어가진 사람 n명 존재할 때
 2. n명 중 최소 6사람만 모이면 비밀값 복구 가능하다.  

 라는 것을 이용하여 secret-sharing을 구현하였다.


## sharing 방법
 전체 사람의 수 `N`, 임의의 수 `k(k <= N)`, 비밀값 `S` 일때,
 다항식 P(x)  
 ![다항식 P(X)](/TIL/assets/images/shamir_share.PNG)  
 를 설정한다.  
 이 다항식 위 N개의 점 (1,P(1)), (2,P(2)), (3,P(3)), ...(N,P(N))은 비밀값을 복구할 수 있는 키로 shared secret이 된다. N명의 사람들이 해당 키를 나누어 갖는 것이다.

 
## secret 복구
1. 전체 N명중 K+1명을 모은다.  
이때, k+1명은 어느 누구든 상관없다. k+1명만 모으면 된다.
2. k+1명이 각자 가지고 있는 shared secret으로 P(x)를 알아낸다.
3. P(0)를 구한다. (P(0)=a_0이므로 P(0)를 구하면 비밀값을 구한것이다.)

## shamir's secret sharing의 특징
 1. 모든 구성원이 갖는 비밀키가 유일하며 평등하다.
 2. k+1개 이상의 조각만 있으면 비밀을 복구할 수 있으므로 일부 조각이 손상되어도 안전하다.