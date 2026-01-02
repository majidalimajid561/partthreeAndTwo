# partthreeAndTwo
these are just a practice solutions not a complete alogs 
import json
import csv

# pre fix sum of list 
def presum(list):
    sum=0
    for  i in list:
        sum+=i
    return sum
# remove duplicates
def removeduplicates(list):
    i=0
    j=0
    ans=[]
    ans.append(list[0])
    for i in range(1,len(list)-1):

        if list[i] != list[j] :
            ans.append(list[i])
            j=i
    
    return ans
# create list that start with even numbers
def eventoodd(list):
    i=0
    j=0
    for i in range(0,len(list)) :
        if list[i]%2==0 :
            list[j],list[i]=list[i],list[j]
            j+=1
    return list
# max sum of list
def  knadieanalogrithm(list):
    currentSum=0
    maxSum=list[0]
    n=len(list)
    i=0
    for i in range(n):
        currentSum+=list[i]
        if currentSum<0:
            currentSum=0
        if  currentSum>maxSum :
            maxSum=currentSum
    return maxSum
# wealthy person
def wealthy(list):
    i=0
    j=0
    maxmoney=list[0][0]
    for i in list:
      current=0
      for j in i:
        current+=j
      if current>maxmoney:
          maxmoney=current
    return maxmoney
# spiral printing of square matrics
def sp(list):
 top=0
 left=0
 right=len(list)
 down=len(list)
 n=len(list)*len(list)
 ele=0
 while ele<n:
  for j in range(0,right) :
     print(list[top][j],end=' ')
     ele+=1
  top+=1
  for i in range(top,down) :
     print(list[i][right-1],end=' ')
     ele+=1
  right-=1
  for j in range(right-1,left,-1) :
     print(list[down-1][j],end=' ')
     ele+=1
  down-=1
  for i in range(down,top,-1):
     print(list[i][left],end=' ')
     ele+=1
  left+=1
# create a comprehension list of squares
def squareList(list):
   return [i*i for i in list]
# create a comprehension list of even numbers
def evenList(list):
   return [i for i in list if i%2==0]
# String  Questions 
def defangIpaddr(addrs):
    ans=""
    for i in addrs:
       if  i!=".":
         ans+=i
       else:
         ans+="[.]"
    return ans
# is palindrom
def ispalinderom(str):
    i=0
    j=len(str)-1
    while i<j :
        if str[i]!=str[j] :
         return False
        i+=1
        j+=1
    return True

# count vowels in strings
def countvowel(str):
      count=0
      for  i in str:
        if  i=='a' or i=='e' or i=='i' or i=='o' or i=='u':
         count+=1 
      return count
# print sub Strings 
def allSubstrings(s):
     for i in range(0,len(s)) :
        ans=""  
        for j in range(i,len(s)):
           ans+=s[j]
           print(ans, end=" ")
        print()

# is anagram Strings
def isanagram(s1,s2):
   if len(s1) != len(s2) : return False
   l1=sorted(s1)
   l2=sorted(s2)
   for i in range(0,len(l1)) :
    if l1[i]!=l2[i] :return False
   return True

#most frequent character
def mostfrequent(s):
   s=sorted(s)
   i=0
   j=0
   ans=' '
   max=-1
   n=len(s)
   while j<n:
      if s[i]==s[j]:
        j+=1
      else :
         currlen =j-i
         if  currlen>max :
            max= currlen
            ans =s[i]
         i=j 
   currlen =j-i
   if  currlen>max :
     max= currlen
     ans =s[i]
   return ans

s1 ={1,2,3,4,5}
s2 ={6,7,3,8,9}
# unioun of sets
#print(s1|s2)
# intersection
#print(s1 & s2)
# difference mean  elements of s1 that are ont present in s2
#print(s1-s2)
# symmetric defference mean print all element except commens
#print(s1^s2)
# largest word
def lagets_word(s) :
    words=s.split() 
    largest_word=''
    for word in words :
       if len(word)>len(largest_word) :
        largest_word=word
    return largest_word 

# count word in paragraph 
def countword(s):
   word=s.split()
   wordsinPara=len(word)
   return wordsinPara
# remove puctuations
def removeP(s):
    result=""
    for ch in s:
      if ch.isalnum() or ch.isspace() :
         result+=ch
    return result
# count subString fre
def frequencycount(s):
   return s.count("co")

# remove multiple spaces 
def removeSpaces(s):
    reslut =""
    prev=False
    for ch in s:
      if ch==" ":
         if not prev:
            reslut +=ch
            prev=True
      else :
         reslut+=ch
         prev=False
    return reslut
# swapin of last and first character
def swaping(s):
    ans=""
    n=len(s)
    if n>1:
        ans+=s[n-1]
        for i in range(1,n-1):
           ans+=s[i]
        ans+=s[0]
    else:
       print("lenght of string is smalller")
    return ans

# with open('snip.jpg.png' ,'rb') as f :
#    with open('newsnip.jpg.png','wb') as s:
#       s.write(f.read())
# list = [1,2,3,4,5]
# with open("my.txt",'w') as f:
#    json.dump(list,f)
# with open('my.txt','r') as f:
#    print(json.load(f))

# s={'name':'majid ','rollNum':16,'depart':'BSCS'}
# with open('new.txt','w') as f:
#    json.dump(s,f)
# with open('new.txt','r') as s:
#    print(json.load(s))

# creating file and searshing for words by usiing memberships operator 
def searchinfile(file) :
  search_word='python'
  if search_word in file:
      print(f"'{search_word}' is found ")
  else :
     print(f"'{search_word}'not  found ")
 # with open('majid.txt','w') as f:
# f.write("python is easy but i did not understan in one day so I have to spend days for learn it")
# with open('majid.txt','r') as f:
#    file=f.read()

# writing an dreading CSV files
with open ('student.csv','w',newline='') as s:
   myscvfile=csv.writer(s)
   myscvfile.writerow(['Name','rollNo','Depar.'])
   myscvfile.writerow(['1st Name',' 19 rollNo','BSCS'])
   myscvfile.writerow(['2nd Name','20 rollNo','BSCS'])
   myscvfile.writerow(['3rd Name','22 rollNo','BSCS'])

with open('student.csv','r') as f:
   optfile=csv.reader(f)
   for row in optfile:
      print(row)



# Exceptions
# Syntax
#try Kesyword:
# risky code
# except Keyword Name of error:
#printing the info.. for user to understand the error
 def divsion(n,m):
    if m==0 :
       raise Exception("ya devie nai  hogaa")
    print(n/m)
 try:
  divsion(1,0)
 except Exception as e :
    print(e)  
# custom Exception Class
class MyException(Exception):
    def __init__(self,info):
        print(info)

def division(num,den):
    if type(num)!=int or type(den)!=int:
        raise MyException("ary bhai number input do")
    if den==0:
        raise Exception("denoirator zero ha ")
    return num/den
try:
    division(1,'ll')
except MyException as e:
    pass
except Exception as e:
    pass

    numberlist =[1,2,3,4,5]
def squaresbylmda(numbers):
 print(list(map(lambda x:x**2,numbers)))

#converting  to upper case 
words=['hello','abc','de','fg']
def covertingCase(words):
 print(list(map(lambda x:x.upper(),words)))


# odd numbers in list
def filteringevenAndOddNum(li):
   evenList=list(filter(lambda x:x%2==0,li))
   print(evenList)
   oddList=list(filter(lambda x:x%2==1,li))
   print(oddList)

def findinsumbyreducefun(numberlist):
   sum=functools.reduce(lambda a,b:a+b,numberlist)
   print(sum)

def findinProductbyreducefun(numberlist):
   pro=functools.reduce(lambda a,b :a*b,numberlist)
   print(pro)


def My_Decorator(func):
   def wrapper(*args):
      print("---****---")
      start=time.time()
      func(*args)
      print("total agruments",len(args))
      print("---****---")
      e=time.time()
      print("Execution time is :",e-start,"sec")
      return len(args)
   return wrapper

@My_Decorator
def add(*args):
   print("Sum of Two :",sum(args))



def decor(n):
   def outer(func):
      def wraper(*args):
         for i in range(*args) :
          func(*args)
      return wraper
   return outer

