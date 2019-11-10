---
layout: post
title: 설탕 배달
author: Eollugii
date: '2019-11-10 18:34:00 +0900'
category: java
summary: 백준 2839번 문제
thumbnail: thumbnail/lang/java.png
---

**백준 2839번 설탕 배달**

~~~
public int sugarEnvelope(int n) {
    int result = -1;

    int envelope1 = 5;
    int envelope2 = 3;

    int max = n / envelope1;

    while(max > -1) {
        int remainder = n - max * envelope1;

        if(remainder % envelope2 == 0) {
            result = max + remainder / envelope2;
            break;
        }
        max--;
    }
    return result;
}
~~~

*두 봉투 중 무거운 것*으로 나누어 무거운걸 최대로 가질 수 있는 **max** 변수값을 지정해준다.  
그리고 **n**에서 무거운 봉투로 *최대로 가져갈 수 있는 양을 뺀 나머지*를 **remainder** 변수에 넣어 준다.  
**remainder**값을 작은 봉투의 무게로 나누었을 때 *나머지 값*이 **0**이 되면 **max** 값과 **remainder** 값에서 적은 무게가 나가는 봉투의 무개를 나누어 나온 값을 더하면 가장 적게 들고 갈 수 있는 개수가 되게 된다.  
이때 적은 봉투의 무게로 나누어서 *나머지*가 **0**이 나오지 않는다면 **max**값을 줄여가며 계산한다.  
마지막까지 나머지가 **0**이 나오지 않는다면 정확히 **n**의 무게를 들고갈 수 있는 *조건이 성립하지 않으므로* **1** 반환한다.  