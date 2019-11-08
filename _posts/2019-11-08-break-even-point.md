---
layout: post
title: 손익분기점
author: Eollugii
date: '2019-11-09 23:08:00 +0900'
category: java
summary: 백준 1712번 문제
thumbnail: thumbnail/lang/java.png
---

**백준 1712번 손익분기점**

~~~
public long bep(String str) {
    long result = 0;

    String[] tmpArr = str.split(" ");

    if(tmpArr.length != 3) return -1;

    long fixedCost = Integer.parseInt(tmpArr[0]);
    long cost = Integer.parseInt(tmpArr[1]);
    long price = Integer.parseInt(tmpArr[2]);

    if(cost < price) {
        for(long num = 1; ; num++) {
            if(fixedCost + cost * num < price * num) {
                result = num;
                break;
            }
        }
    } else result = -1;
    return result;
}
~~~

고정비용, 가변비용 그리고 가격을 차례대로 받아 각각 숫자형 변수로 넣어준다.  
*가격이 가변비용을 초과하지 못하면* 이익이 발생할 수 없으므로 가격이 가변비용을 ***초과***할 경우 판매량을 계산한다.  
반복문을 사용하여 판매량을 계산하게 하였으며 이때 외부에 카운트 변수를 선언하지 않고 종료 조건이 없는 for문을 사용하였다.  