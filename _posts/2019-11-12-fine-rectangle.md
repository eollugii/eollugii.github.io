---
layout: post
title: 멀쩡한 사각형
author: Eollugii
date: '2019-11-12 22:17:00 +0900'
category: java
summary: 프로그래머스 멀쩡한 사각형
thumbnail: thumbnail/lang/java.png
---
~~~
public long fineRectangle(int w, int h) {
    long result = 0;
    long ea = euclideanAlgorithm(w, h);

    result = (long)w*(long)h - ((long)w + (long)h - ea);

    return result;
}

public long euclideanAlgorithm(int a, int b) {
    long result = 0;

    if(b > a) {
        int tmp = a;
        a = b;
        b = tmp;
    }

    while(true) {
        int tmp = a%b;
        if(tmp > 0) {
            a = b;
            b = tmp;
        } else {
            result = b;
            break;
        }
    }

    return result;
}
~~~
w 넓이, h 높이, gcd 최대공약수라 칭한다.  
*유클리드 호제법*을 이용하여 **최대공약수**를 구한다.  
(0,0)에서 (w,h)까지 직선을 그엇을 때 손실되는 사각형의 개수는 (w + h + gcd) 이다.  
그러므로 멀쩡한 사각형의 개수는 w * h - (w + h gcd) 이다.  