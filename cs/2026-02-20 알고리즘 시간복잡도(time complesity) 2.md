algorithm ArrayMax(A,n):
    CurrentMax = A[0]
     for i = to n-1 do
         if CurrentMax < A[i] :
             CurrentMax=A[i]
     returun CurrentMax
저번에 말했듯 우리는 무수히 많은 입력 n의 값을 매번 구하여 시간복잡도를 나타낼 수 없다는 것을 알았다
그러한 문제들을 해결하는 방법이 있다


A=[_,_,_,_,_,_] n: inputsize

1. 모든 입력에 대해 기본연산 횟수를 더한 후 평균=>현실적으로 무한히 많은 경우의 수를 고려하는 것은 불가능하다.

2. 가장 안 좋은 입력(worstcase input)에 대한 기본 연산 횟수를 측정(worstcae time complexity)
   =>어떠한 입력에 대해서도 worstcae time complexity보다 수행시간이 크지 않다!

**알고리즘 수행시간
알고리즘 수행시간= 최악의 입력에 대한 기본연산 횟수


algorithm ArrayMax(A,n):
    CurrentMax = A[0]
     for i = to n-1 do
         if CurrentMax < A[i] :
             CurrentMax=A[i]★
     returun CurrentMax
이 코드에서 CurrentMax = A[0] 이 기본 연산은 무조건 한 번 실행 된다
if CurrentMax < A[i] : 이 비교연산도 무조건 한 번은 실행 된다
★로 마크된 곳은 위에 코드가 참이여야지 실행된다
그럼 최악의 입력은 비교문이 항상 참이여한다
 for문 안에 있는 코드는 2번이 반복되므로
 그러므로 (n-1) x 2를 해서 2n-2이다
 **T(n)= 2n-1 이다.
 


