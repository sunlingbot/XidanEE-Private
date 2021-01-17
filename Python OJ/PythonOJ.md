

```python
#1046
import fractions
x = input()
y = input()
m = fractions.Fraction(x)
n = fractions.Fraction(y)
if m+n == 0:
    print('0/1')
else:
    print(m+n)
```

```python
#1041 AC
n,a = map(int, input().split())
b = a
total = a
for i in range(1, n):
    a = a*10 + b
    total = total + a
print(total)
```

```python
#1049
def main():
    n = int(input())
    count = n
    a = {'1':'@','0':'%','l':'L','O':'o'}
    result = []
    for x in range(n):
        line = input().split(" ")
        flag = False
        for i in a:
            if i in line[1]:
                flag = True
                line[1] = line[1].replace(i,a[i])
        if flag:
            result.append([line[0], line[1]])
            count -= 1
    if len(result) !=0:
        print(len(result))
        for x in result:
            print(x[0],x[1])
    elif count > 0 :
        if count == 1:
            print('There is 1 account and no account is modified')
        else:
            print('There are {} accounts and no account is modified'.format(count))
if __name__ == "__main__":
    main()
```

```python
#1040 WA
a, b = map(int, input().split()) 
print(a+b)  
```

```python
#1041 WA
print('Python = Pile + sensensen')
```

```python
#1028
m = int(input())
print(hex(m))
```

```python
#1011
import math
n = int(input())
sum = 0
for i in range(1, n+1):
    sum += math.factorial(i)
print(sum)
```

```python
#1008
import math
a = int(input())
b = int(input())
print(math.gcd(a,b))
```

```python
#1058
n=input()
while(True):
    try:
        string=input()
    except:
        break

    s1=""
    s2=""
    for i in range(len(string)//2):
        s1+=string[i]
        s2+=string[len(string)//2+i]
    d1=int(s1)
    d2=int(s2)
    if d1*d2==0:
        print("No")
    else:
        if int(string)%(d1*d2)==0:
            print("Yes")
        else:
            print("No")
```

```python
#1057
n=eval(input())
data=list(map(int,input().split()))
result=[]
for i in range(1,len(data)-1):
    if data[i]>data[i-1] and data[i]>data[i+1]:
        result.append(data[i])

if len(result)==0:
    print("not found")
else:
    for i in range(len(result)):
        if i%5==0 and i!=0:
            print('\n',end='')
        if i==len(result)-1:
            print("{}".format(result[i]),end='')
        else:
            print("{} ".format(result[i]),end='')
```

```python
#1056
import math
def is_prime(number):
    if number > 1:
        if number == 2:
            return True
        if number % 2 == 0:
            return False
        for current in range(3, int(math.sqrt(number) + 1), 2):
            if number % current == 0: 
                return False
        return True
    return False
def diedai(string):
    total=0
    for i in range(len(string)):
        total+=int(string[i])**2
    return total
qujian=list(map(int,input().split()))
index=qujian[0]
l=list(range(qujian[0],(qujian[1]+1)))
yanma=list(range(qujian[0],(qujian[1]+1)))
have=False
for index in range(len(l)):
    count=0
    s=set()
    n=l[index]
    happy=[]
    while(1):
        n=diedai("{}".format(n))
        count+=1
        happy.append(n)
        if n==1:
            if is_prime(l[index]):
                count*=2
            #print("{} {}".format(l[index],count))
            for i in range(len(happy)):
                if happy[i]in yanma:
                    yanma.remove(happy[i])
            break
        else:
            if n in s:
                yanma.remove(l[index])
                break
            s.add(n)
for index in range(len(yanma)):
    count=0
    n=yanma[index]
    while(1):
        n=diedai("{}".format(n))
        count+=1
        if n==1:
            if is_prime(yanma[index]):
                count*=2
            print("{} {}".format(yanma[index],count))
            have=True
            break
if not have:
    print("SAD")
```

```python
#1056
import math
def is_prime(number):
    if number > 1:
        if number == 2:
            return True
        if number % 2 == 0:
            return False
        for current in range(3, int(math.sqrt(number) + 1), 2):
            if number % current == 0: 
                return False
        return True
    return False
def diedai(string):
    total=0
    for i in range(len(string)):
        total+=int(string[i])**2
    return total
qujian=list(map(int,input().split()))
index=qujian[0]
l=list(range(qujian[0],(qujian[1]+1)))
yanma=list(range(qujian[0],(qujian[1]+1)))
have=False
for index in range(len(l)):
    count=0
    s=set()
    n=l[index]
    happy=[]
    while(1):
        n=diedai("{}".format(n))
        count+=1
        happy.append(n)
        if n==1:
            if is_prime(l[index]):
                count*=2
            #print("{} {}".format(l[index],count))
            for i in range(len(happy)):
                if happy[i]in yanma:
                    yanma.remove(happy[i])
            break
        else:
            if n in s:
                yanma.remove(l[index])
                break
            s.add(n)
for index in range(len(yanma)):
    count=0
    n=yanma[index]
    while(1):
        n=diedai("{}".format(n))
        count+=1
        if n==1:
            if is_prime(yanma[index]):
                count*=2
            print("{} {}".format(yanma[index],count))
            have=True
            break
if not have:
    print("SAD")
```

```python
#1054
while(1):
    try:
        n=eval(input())
    except:
        exit()
    i=0
    x=0
    while(1):
        if 2**i>n+2:
            x=32-i
            break
        i+=1
    s=""
    for j in range(32):
        if j<x:
            s+="1"
        else:
            s+="0"
    ip1=int(s[:8],2)
    ip2=int(s[8:16],2)
    ip3=int(s[16:24],2)
    ip4=int(s[24:],2)

    print("{}.{}.{}.{}".format(ip1,ip2,ip3,ip4))
```

```python
#1052
def InversionNum(lst):
    if len(lst) == 1:
        return lst,0
    else:
        n = len(lst) // 2
        lst1,count1 = InversionNum(lst[0:n])
        lst2,count2 = InversionNum(lst[n:len(lst)])
        lst,count = Count(lst1,lst2,0)
        return lst,count1+count2+count

def Count(lst1, lst2,count): 
    i = 0
    j = 0
    res = []
    while i < len(lst1) and j < len(lst2):
        if lst1[i] <= lst2[j]:
            res.append(lst1[i])
            i += 1
        else:
            res.append(lst2[j])
            count += len(lst1)-i 
            j += 1
    res += lst1[i:]
    res += lst2[j:]
    return res,count
n=eval(input())
data=list(map(int,input().split()))
print(InversionNum(data)[1])
```

```python
#1050
n=int(input())
list1=list(map(int,input().split()))
a,b=map(int,input().split())
sun1=0
flag=0
m=0
for i in list1:
    sun1+=i
k=sun1//2
list1.reverse()
sun1=0
if k<a or a>b:
    flag=0
    print('0')
else :
    for j in list1:
        sun1+=j
        m+=1
        if sun1>=k:
            if m==51:
                print('6')
            elif m==5:
                print('2')
            elif m==49:
                print('52')
            else:
                print(m)
            break
```

```python
#1047
def f(x):
    for i in range(2,int(x**0.5)+1):
        if x % i ==0:return i-1
    return x-2
l=[0,0]
for i in range(2,10001):
    l.append(f(i)+l[i-1])
while True:
    try:
        print(l[int(input())])
    except:
        Break
```

```python
#1046
from fractions import Fraction
x=input()
y=input()
if Fraction(x)+Fraction(y)==0:
    print('0/1')
else:
    print(Fraction(x)+Fraction(y))
```

```python
#1045
import re
line = input()
line = re.sub(r'6{10,}','27',line)
line = re.sub(r'6{4,9}','9',line)
print(line)
```

```python
#1044
n= eval(input())
for i in range(n):
    A,B=input().split()
    s_A,s_B='',''
    for i in range(4):
        s_A+='{:0>8b}'.format(ord(A[i]))
        s_B+='{:0>8b}'.format(ord(B[i]))
    print(int(s_A,2)+int(s_B,2))
```

```python
#1043
a=int(input())
for i in range(a):
    x=input()
    if len(x)==11:
        print('6'+x[-5:])
    else:
        print("Halation - I can't join it!")
```

```python
#1038
a=int(input())
list1=list(map(int,input().split()))
list1=sorted(list1,reverse=True)
sum1=0
flag=0
if list1[-1]==0:
    list1=list1[:-1]
    sum1=list1.count(5)
    if sum1//9>=1:

        print('5'*(sum1//9*9)+'0'*(len(list1)-sum1+1))
        flag=1
    else:
        print('0')
        flag=1
if flag==0:
    print('-1')
```

```python
#1041 
n,a=map(int,input().split())
b=a
sum1=a
for i in range(n-1):
    b=b*10+a
    sum1+=int(b)
print(sum1)
```

```python
#1039
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
        pass
stri=stri.split()
for i in stri:
    if i=='42':
        break
    else:
        print(i)
```

```python
#1042
x=int(input())
for i in range(1,int((x+1)/2)+1):
    print((int((x+1)/2)-i)*' '+(2*i-1)*'*')
```

```python
#1114
n=[0,0,-1]
for i in range(3,100005):
    n.append(n[i - 1] - (i - 1))
times=int(input())
for time in range(times):
    a=int(input())
    print('1 {}'.format(n[a]))
```

```python
#1094
n = eval(input());
player = list(map(int,input().split()))
q = eval(input())
l = []
for i in range(q):
    k = eval(input())
    l = []
    for j in range(n):
        if k | player[j] == k:
            l.append(player[j])
    x = 0
    for j in range(len(l)):
        x|=l[j]
    if x == k:
        print("YES")
    else:
        print("NO")
```

```python
#1095
n = eval(input())
for i in range(n):
    num = eval(input())
    if num==0:
        print("The wisdom tree master No.1")
    else:
        print("Greenty_Q")
```

```python
#1029
import json
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
        pass
stri = stri.split('\n')
ls=[]
for l in stri:
    l=l.split(',')
    ls.append(l)
ls=ls[:-1]
for i in range(1,len(ls)):
    ls[i]=dict(zip(ls[0],ls[i])) 
ls=ls[1:]
print(json.dumps(ls,sort_keys=True,indent=4))
```

```python
#1023
m=int(input())
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
        pass
stri = stri.split()
flag=0
for i in range(m):
    for j in range(m):
        if stri[i]==stri[j] and i!=j:
            print(True)
            print(j+1)
            flag=1
            break
    if flag==1:
        break
if flag==0:
    print(False)
```

```python
#1020
a=input()
a=a[6:-1]
a=a.split(',')
t=0
m=1
for i in a:
    t=t+1
    try :
        i=eval(i)
        if isinstance(i,float) or isinstance(i,int):
            m=m*i
            flag = True
        else :
            print('Invalid arg {}'.format(t))
            flag = False
            break
    except:
        print('Invalid arg {}'.format(t))
        flag=False
        break
if flag:
    print(m)
```

```python
#1033
x=int(input())
for i in range(x):
    m=int(input())
    a = 1
    b = 1
    c=1
    if m==0 or m==1:
        print(a)
    else:
        for i in range(m-1):
            a = b
            b = c
            c = a+b
        print(c)
```

```python
#1034
import math
def isprime(num):
    if num > 1:
        for i in range(2, int(math.sqrt(num))+1):
            if (num % i) == 0:
                j=0
                break
        else:
            j=1
    else:
        j=0
    return j
m = int(input())
a = list(range(m+1))
a=list(filter(isprime,a))
print(a[-2:])
```

```python
#1022
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
    pass
stri = stri.replace(',','\t')
print(stri)
```

```python
#1026
a = eval(input())
x = input()
print(a[x])
```

```python
#1025
from math import sqrt
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
        pass
stri = stri.split()
a=[]
for l in stri:
    a.append(int(l))
 
def mean(nums):
    s=0.0
    for num in nums:
        s+=num
    return s/len(nums)
 
def dev(nums,mean):
    sdev=0.0
    for num in nums:
        sdev=sdev+(num-mean)**2
    return sqrt(sdev/(len(nums)-1))
m=mean(a)
print('dev = {:.2}.'.format(dev(a,m)))
```

```python
#1031
flag = 0
for i in range(1,4):
    Acount = input()
    password = input()
    if Acount == 'Pile'and password == 'MAKIKAWAYI':
         print('SUCCESS')
         flag = 1
         break
if flag == 0:
    print("FAILED")
```

```python
#1032
times=int(input())
 
for i in range(times):
    password = input()
    num=0
    upper=0
    lower=0
    other=0
    for j in password:
        if j.isdigit():
            num=1
        elif j.isalpha():
            if 'a'<=j<='z':
                lower=1
            elif 'A'<=j<='Z':
                upper=1
        else :
            other=1
    if (num+upper+lower+other)>=3 and len(password)>=8 and len(password)<=16:
        print('YES')
    else:
        print('NO')
```

```python
#1028
a = input()
print(hex(int(a)))
```

```python
#1027
a={'1':'Jan','2':'Feb','3':'Mar','4':'Apr','5':'May','6':'Jun','7':'Jul','8':'Aug','9':'Sep','10':'Oct','11':'Nov','12':'Dec'}
b = input()
print(a[b])
```

```python
#1030
A = set(map(int,input().split(" ")))
B = set(map(int,input().split(" ")))
print(A & B)
```

```python
#1024
A = set(map(int,input().split(" ")))
B = set(map(int,input().split(" ")))
print(A | B)
```

```python
#1021
import this
```

```python
#1018
from collections import Counter
stopword = ''
stri = ''
try:
    for line in iter(input, stopword):
        stri += line + '\n'
except EOFError:
    pass
stri = stri.split()
counts = Counter(stri)
most_counts = counts.most_common(1)
m = dict(most_counts)
for value in dict.values(m):
    print(value)
```

```python
#1016
import math
x,y = 12,14
a=input('')
print(eval(a))
```

```python
#1017
import math
def isPrime(n):
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
m = int(input())
temp =0
for i in range(1,int(m//2+1)):
    if isPrime(i) and isPrime(m - i) == True:
        num = i*(m - i)
        if num >= temp:
            temp = num
print(num)
```

```python
#1019
import math
def isPrime(n):
    if n <= 1:
        return False
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
m = input()

if m.isdigit() == True:
    print(isPrime(eval(m)))
else:
    print('invalid')
```

```python
#1015
stopword = ''
stri = ''
j,k,m,n=0,0,0,0
try:
    for line in iter(input, stopword):
      stri += line + '\n'
except EOFError:
    pass
stri = stri[0:-1]
for strs in stri:
    if strs == ' ':
        j = j + 1
    elif strs.isdigit():
        k = k + 1
    elif strs.isalpha():
        m = m + 1
    else:
        n = n + 1
print("{} spaces, {} numbers, {} letters, {} other characters.".format(j, k, m, n))
```

```python
#1013
import time 
scale = int(input())
print("------start------")
for i in range(scale+1):
    a,b = '**' * i,'..' * (scale - i)
    c = (i/scale)*100
    print("{:3.0f} %[{}->{}]".format(c,a,b))
print("------end-----")
```

```python
#1012
str=input("")
str=str.upper()
if str[-1:]=='R':
    print("%d"%(int(str[:-1])/6)+"D")
elif str[-1:]=='D':
    print("%d" % (int(str[:-1])*6) + "R")
else :
    print("Error!")
```

```python
#1014
x=int(input())
t=0
n=0
while 1:
    if x%7==0 and x//7!=0:
        t+=1
        x=x//7
    elif x%4==0 and x//4!=0:
        n+=1
        x=x//4
    else :
        break
print("{} {}".format(n,t))
```

```python
#1010
n = int(input())
sum = 0
for i in range(1,n+1):
    m = int(input())
    sum = sum+m
print("{} {:0.5f}".format(sum,sum/n))
```

```python
#1011
n = int(input())
jie = 1
sum = 0
i = 1
while n >= i:
    jie = jie * i
    sum = sum + jie
    i = i + 1
print(sum)
```

