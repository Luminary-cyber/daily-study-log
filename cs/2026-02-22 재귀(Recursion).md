재귀(Recursion) : 재귀함수(재귀알고리즘)=함수(알고리즘) 내부에서 한번 이상 자신의 함수를 호출

예1:
1. 1++....+n
sum(n)=[1+2++....+(n-1)]-->sum(n-1)+n
```Python
def sum(n):
    if n == 1:
        return 1
    return sum(n-1)+n   

```
-> sum(4)=sum(3)+4
         =sum(2)+3    
         =sum(1)+2

수행시간 : T(n)=T(n-1)+c
            =T(n-2)+c+c
            =T(n-2)+2c
             ......
             =T(n-(n-1))+ n-1 +c
             =T(1)+(n-1)c
             =__T(n)=O(N)__
 
 
 1. n == 1 테스트:바닥 조건(base case)
 2. 재귀호출: T(n)= 점화식








예2: sum(a,b)= a+(a+1)+.....+(b-1)+b
 sum(3,8)=[3+4+5] (sum(3,5))-->sum(a,m)+ [6+7+8] (sum(6,8))-->sum(m+1,b)
def sum(a,b):
    if a== b: return a
    if a>b :return 0
    m = (a+b)//2
    return sum(a,m)+sum(m+1,b)

수행시간:
T(n) = 2 x T(n/2)+c, T(1)=c
    =2** 2T(n/2** 2)+2c + c
    =
    =
    =2 ** kT(n/2** k)+c(1+2+2 ** 2+ .....+2 ** k-1)
    = c x 2** k +c(2** k -1/2-1)
    =2cn-c
    =O(n)





예3: reverse 함수: A=[1,2,3,4,5] reverse A=[5,4,3,2,1]
 1. reverse(A)=reverse()+A[0]
         =reverse(A[1:])+A[0]--->리스트 연결

    수행시간:
    T(n)=T(n-1)+c
      =O(n)
2. reverse(A,start,stop)=A[start].....A[stop-1]
                   =A[stop-1]    A[start] 
                [reverse(A[sstart+1]    A[stop-2])]
                [reverse(A[A,start+1,stop-2])]
수행시간:
T(n) =T(n-2)+c
    =T(n-4)+2c
     :
     :
    =T(1)+n/2 x c
    =O(n)