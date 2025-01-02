# FindingPrimeNumbers
FindingPrimeNumbers 3 digit and starting with 5

I think the questions asks prime numbers from 500 to 599.
My strategy is so:

1 - Find the prime numbers sqrt(599). findPrimesToN function in the code.
  - For finding them I will create a list. Initially it has one member '2'.
  - Then I will iterate from 3 to integer<sqrt(599) by 2. I mean 3,5,7,9... . Because prime numbers except 2 are odd numbers.
  - In every step I will divide the number by all numbers in list. If it is not divided by any number in list, then I will add it in the list.

2 - I call findPrimesToN(sqrt(599)) and get a list of all prime numbers to sqrt(599) and put them in the 'list' variable. 
  - I iterate from 501 to 599 by 2 and divide it by numbers in the 'list' list variable.
  - If the number is can not divided by any number in list 'list', then I add it in the answer_list, 'ans_list' variable.
    

Python Code for the Algorithm:

import math 
def findPrimesToN(n):
    list = [2]
    flag = 1
    for i in range(3, n, 2):
        flag = 1
        for t in list:
            if i%t == 0:
                flag = 0
                break
        if flag == 1:
            list.append(i)
    return list
        


list = findPrimesToN(int(math.sqrt(599)))
print(list)

ans_list = []

for i in range(501, 600, 2):
    flag = 1
    for t in list:
        if i%t == 0:
            flag = 0
            break
    if flag == 1:
        ans_list.append(i)
       
print(ans_list) #this is the answer

