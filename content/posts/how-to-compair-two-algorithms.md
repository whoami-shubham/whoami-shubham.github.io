---
layout: post
title:  How to Compare Two Algorithms
date:   2018-11-17 04:18:45
summary: "Let's understand this with a story.
Alice,Bob, and john are best friends, Let's assume Alice and Bob took a programming course this semester and john didn't. john  went to hangout with alice and bob"
tags: [algorithm]
---

<style type="text/css">
	.conv{
		padding: 10px;
	    text-align: justify;
	}
	.john{
		color:#4285F4;
	}
	.bob{
		color:#F4B400;
	}
	.alice{
		color:#DB4437;
	}
	body{
        font-size: 1.2rem;
	}
	@media (max-width: 768px){
           body{
             font-size: 0.7rem;
            }
            .post-title{
                font-size:28px;
            }
        }
</style>
<br/><br/>
<span class="conv">
Let's understand this with a story.
Alice,Bob, and john are best friends, Let's assume Alice and Bob took a programming course this semester and john didn't. john  went to hangout with alice and bob. conversation goes like this.<br/><br/>
 <span class="john">John:</span> <span class="conv">"Hey Alice what are you doing ?" </span><br/>
 <span class="alice">Alice:</span><span class="conv"> "We are writing programs for our assignments."</span><br/>
 <span class="john">John:</span><span class="conv"> "Hey Bob are You coding the same problem ?"</span><br/>
 <span class="bob">Bob:</span><span class="conv">"Yes."</span><br>
 <span class="john">John:</span><span class="conv"> "It's look like alice code is more efficient than your's isn't it?"</span><br>
 <span class="bob">Bob:</span><span class="conv">"Why do you think so ?"</span><br>
 <span class="john">John:</span><span class="conv">"As length of her program is lesser."</span><br>
 <span class="bob">Bob:</span><span class="conv"> "we can't compare two Algorithm by just number of lines of code ."</span><br>
 <span class="john">John:</span><span class="conv"> "why?"</span><br>
 <span class="bob">Bob:</span><span class="conv"> "Suppose if i have written a program in c in 100 lines then i can write same program in python in 20 lines or less that doesn't mean
 c program is less efficient than python"</span><br>
 <span class="john">John:</span><span class="conv"> "Then you must be comparing it with running time. right ? "</span><br>
 <span class="bob">Bob:</span><span class="conv"> " Nope .we can not compare two Algorithm by execution time."</span><br>
 <span class="john">John:</span><span class="conv"> "why ?"</span><br>
 <span class="bob">Bob:</span><span class="conv"> "Because suppose Alice computer is faster than mine . 
      My computer will take more time to run than her."</span><br>
 <span class="john">John:</span><span class="conv"> "What if we run both program on same computer ?"</span><br>
 <span class="bob">Bob:</span><span class="conv"> "Well, there are a lot's of processes running at same time.
      suppose i am playing a  game and running this program same time 
      then game is hogging all my memories that might slow my program.
      even if i would run same program on my computer multiple times, 
      execution time would be different each time and  the differnce 
      between these execution time would be random. to compare them by execution time you must have to determine CPU time."</span><br>
 <span class="john">John:</span><span class="conv">"Then Why don't you calculate CPU time ?"</span><br>
 <span class="bob">Bob:</span><span class="conv">"Measuring CPU time is difficult. If you are running on a multi-user machine, then elapsed time is not the correct measure. You must measure CPU time. But for certain programming languages, additional features might run at unpredictable results and you may not wish to include these in your measurements. For example, if you use Java, the Java garbage collector will run at various points to reclaim the memory space used
 by unneeded objects. You may want to exclude from your measurements any
 time spent garbage collecting. Another problem is that the timing commands
 provided by many programming languages do not report times to a sufficient
 level of precision. for most problems there can be many bottleneck
 test cases you have to find out CPU time of program for each test case and then take average of that to find out execution time."</span><br>
 <span class="john">John:</span><span class="conv"> "Then what is best way to compare two Algorithms ?"</span><br>
 <span class="bob">Bob:</span><span class="conv"> "There is a notation called asymptotic notation to measure efficiency of Algorithm."</span><br>
 <span class="john">John:</span><span class="conv"> "It sounds like complex. can you explain it in simple way ?"</span><br>
 <span class="bob">Bob:</span><span class="conv"> " it's not  complex . in asymptotic notation 
     we always talk about rate of growth of program.rate of growth means
     how  does the execution time changes as the size of input grows. 
     for example if you have to print a number from 1 to n then it will 
     take linear time why ? because run time of your program is proportional to n . 
     how do you know that ? suppose if n is 10 then your print statement will
     execute 10 times if i change n to 100 then print statement will execute 100 times. 
     as n is grows 10 times your task of printing is also grows 10 times."</span><br>
                           
   <center><span style="text-align: center;font-weight: bold;">**story over**</span></center> <br><br><span class="conv">
now you'll have basic understanding how to compare two programs.
now you would be thinking why we care about efficiency it is not sufficient my program is giving correct output ?. suppose if you want to buy some product on Amazon and  amazon takes 10s or more each time whenever you click on some option. would you use it in 2018 ? 
yes you won't. now if you're thinking how to predict  how much time a program will take to execute in general then skim through the following functions and their rate of growth with respect to input size 'n'

![growth](/images/rate_of_growth.png)

<br>
a normal computer can execute 10<sup>9</sup> instruction per second. suppose we have two algorithm and you are going to run both for input size  1000 and one algorithm has <span title="it is just  a fancy word for rate of growth">time complexity</span> of O(n) then how much second computer will take to give you result ?
1000/10<sup>9</sup>  = 1 micro second but it is not exact value it would took few mili seconds in worst case. and other hand we take second algorithm for same input size with different time complexity lets take O(2<sup>n</sup>) then it will take 2<sup>1000</sup>/10<sup>9</sup> = 10<sup>301</sup>/10<sup>9</sup> > 10<sup>290</sup> seconds if we divide it by number of seconds in a year(3 * 10<sup>7</sup>) which will still > 10<sup>280</sup> years which is more than  10<sup>269</sup> times of age of universe , you don't want to write such algorithms for real world problem.then what is solution ? chose algorithm that fulfill your needs. to know which algorithm will fulfill your needs you should  know  how to measure complexity of algorithm.
There are two types of complexity that we talk about for algorithms
 <span class="list-group-item conv">1.Time Complexity</span> 
 <span class="list-group-item conv">2.Space Complexity</span>

<span class="list-group-item conv" style="color: skyblue;">1.Time Complexity:</span> 
<span class="conv">
let's talk about  how to find Time complexity of a program .
consider following code snippet.</span>
```c
	#include<stdio.h>
	int main(){
	int n;
	scanf("%d",&n);
	while(n>0){
		printf("%d\n",n);
		n--;
	}
	 return 0;
	}
```
<span class="conv">
what will be the output of this program? your answer would be it depends on  "n".
can  we still predict how many times  while loop will executed ?<br> yes we can still find out three cases<br><br>
<span class="list-group">
	<span class="list-group-item">1.maximum how many times loop will be executed.(worst case)</span><br>
	<span class="list-group-item">2.minimum how many times loop will be executed.(best case)</span><br>
	<span class="list-group-item">3.average how many times loop will be executed.(average case)</span><br>
</span>
<br><br>
what will be the minimum number of times while loop will be executed ? 0 times .when n<=0.what will be the maximum number of times while loop will be executed ? n times (n would be max size of int) now what will be the average number of times while loop will be executed ? (0+n)/2 = n/2 times.In asymptotic notations we  do similar analysis.There are three most often used asymptotic notations are following <br> <br>
<span class="list-group">
 <span class="list-group-item">1.Big O ( for worst case)</span> <br>
 <span class="list-group-item">2.Omega ( for best case)</span><br>
 <span class="list-group-item">3.Theta ( for average case)</span><br>
</span><br>
suppose You have bought a Macbook pro in 1499$ . and one of  your friend asked you how much did it cost ? what would you say ? 1500$ right ? (unless you have a friend which would tell you i could  have bought this for you for free . moreover he would have  made you CEO of apple .)<br>
why did you say that ? because 1499$ was huge compare to 1$ you can neglect it. similarly most of the time we are neglecting some constants or less dominating terms in this analysis. for e.g
You have a function f(x) = n<sup>3</sup> + n + 1 is can be equal to n<sup>3</sup> by multiplying some constants into it. it will be more clear when we move further.
let's discuss about Asymptotic notations.<br><br>
<span class="list-group-item">
	<span style="color:#4285F4;">1.Big O notation (upper bounding function): </span>
we represent worst case complexity of an algorithm using this notation.
suppose you have a function f(x) then what would be the upper bounding function of f(x)?
upper bounding function mean the function which gives f(x) maximum rate of growth for large input .<br>
for example f(x) =  n<sup>3</sup> + n + 1 for larger value of n , n<sup>3</sup> would give more rate of growth to f(x) than n and 1 hence  n<sup>3</sup> is upper bounding function of 
f(x) let's denote upper bounding function with g(x) then mathematically<br>

![bigo](/images/bigo.png)

where c can have infinte numbers of values , c>0<br>
e.g: f(x) = 2n + 4<br>
what would be g(x) ?<br>
in 2n and 4 , 2n have higher rate of growth hence g(x) = n<br>
what will be c? 2n+4<=c*n<br>
for c<=2 c*n could never greater or equal to f(x), let's take c=3<br>
2n+4<=3n when n>=4 hence 2n+4 = O(n) <br>
after some value of n ,c*g(x) will be always >= f(x)<br>
so any function which is asymptotically greater than g(x) will be also upper bounding function of f(x).e.g 2n+4 = O(n<sup>2</sup>) but most of the time we are interested in tightest upper bounding function which is O(n)
</span><br>
<span class="list-group-item">
<span style="color:#F4B400;">2.Omega notation (lower bounding function):</span>
we represent best case complexity of an algorithm using this notation.
suppose you have a function f(x) then the lower bounding function mean the function which gives the largest rate of growth which is less than or equal to the rate of growth of f(x) for example f(x) =  n<sup>3</sup> + n + 1 for larger value of n , n<sup>3</sup> would give less than  the  of growth to f(x) hence  n<sup>3</sup> is upper bounding function of f(x) let's denote lower bounding function with g(x) then mathematically<br>

![omega](/images/omega.png)

where `c` can have infinte numbers of values<br>
e.g: f(x) = 2n + 4 <br>
what would be g(x) ?<br>
n have rate of growth less than f(x) hence g(x) = n<br>
what will be c? 2n+4>=c*n<br>
c<=2 c*n could never greater than  f(x),take c=2<br>
2n+4<=2n when n>=0 hence 2n+4 = &#x2126;(n) 
</span><br>
<span class="list-group-item">
<span style="color:#DB4437;">3.theta notation (order function):</span>
We represent average complexity of an algorithm using this notation.
This notation decides whether upper and lower bounds of a function is same.
if  upper and lower bounds of a function is same then theta would be also same. mathematically<br>

![theta](/images/theta.png)
    
<br>
where c1<=2 and c2>=3 and c1,c2>0<br>
e.g: f(x) = 2n + 4<br>
f(x) = O(n)<br>
f(x) = &#x2126;(n)<br>
f(x) = &#920;(n)<br>
</span>
	
```c
     
	#include<stdio.h>
	 int main(){
		{
	        // block 1  n
	     }
	     
	     {
	     	// block 2   n^2
	     }
	     {
	     	 // block 3   1
	     }
	 return 0;
	}
 ```	
<span class="conv">
in the above code suppose block 1 has n cost block 2 has n<sup>2</sup> cost and block 3 has 1 (constant) cost. then total cost is n<sup>2</sup> +n+1 . but here n and 1 is very smaller than n<sup>2</sup> . when n<sup>2</sup> will be greater than n and 1 ? since we generally talk about large inputs to find complexity hence as we increase n>1 , n<sup>2</sup> will be always greater than 1 and n. now you would be thinking how to find cost ?. cost is nothing but how much times  instructions get executed. let's understand this by an example.lets analyse each block one by one<br>
</span>


```c

	  for(i=0;i<n;i++) //  1st block
		{
		printf("hello world !");
	    }

```
<span class="conv">
<span class="list-group-item">in first block how many times for loop will be executed ? n times right ? hence cost of this block is n or time complexity is O(n) in worst case. what will be the best case time complexity ? when n<=0 loop will execute 0 times hence best case time complexity will be &#x2126;(1),what will be  time complexity for average case ? in average case for loop will be executing (0+n)/2 = n/2 times so average time complexity would be  &#920;(n)
</span>

 ```c

	    for(i=0;i<n;i++) // 2nd block
	  {
		   for(j=0;j<n;j++)
			{
		       printf("hello world !");
		    }
	    }

```	

<span class="list-group-item conv">in 2nd block how many times outer for loop gets executed ? n times  and for each outer loop iteration inner loop also get executed n times hence total cost would be n*n = n<sup>2</sup>, time complexity O(n<sup>2</sup>) for worst case.what will be the best case time complexity ? when n<=0 loop will execute 0 times hence best case time complexity will be &#x2126;(1) , in average case for loop will be executing (0+n<sup>2</sup>)/2 = n<sup>2</sup>/2 times so average time complexity would be  &#920;(n<sup>2</sup>)
</span>

```c

		 for(i=0;i<n;i++) // 3rd block
		{
		    printf("hello world !");
		    if(i==2){
			break;
		       }
		 }

```


<span class="list-group-item conv"> for 3rd block how many times for loop get executed ? maximum 3 times i=0 to i=2 right ? due to break statement loop will be broken when i reaches 2, time complexity O(1) .
</span>

 ```c
	  for(i=1;i<n;i=i*2) // 4th block
	          {
                    printf("hello world !");
                  }    

 ```

<span class="list-group-item conv"> for 4th block how many times for loop get executed ?
	take few examples to convience yourself . value of i will be increasing from 1 till i<n.
	1 2 4 8 2<sup>k</sup> when will be 2<sup>k</sup> > n . take log base 2 both sides
	log2(2<sup>k</sup>)>log2(n)<br>
	k >log2(n)<br>
	so this loop will be executing around log2(n) times.  time complexities would be O(log(n)), &#x2126;(1) and
    &#920;(log(n))<br>  what if i start at  i=0 ? how many times this loop would be executed ? forever right ? if n>0
    </span>

```c
		  
     for(i=1;i<10;i++) // 5th block
	{
        printf("hello world !");
    }   
```

<span class="list-group-item conv"> for 5th block how many times for loop get executed ? 10 times because here no matter what is input size it will always run 10 times. so this is constant time operation time complexity O(1).but if our input size is <= 10<sup>k</sup> and value of constant is >= 10<sup>k</sup> then constant would affect execution time. 
</span>

 ```c
		  
    j=0;
    for(i=0;i<n;i++) // 6th block
	{
	      for(;j<n;j++)
		{
	       printf("hello world !");
	    }
    }
	
 ```

<span class="list-group-item conv"> for 6th block how many times for loop get executed ?
	for i=0 inner loop will execute n times after that inner loop will not executed why ? because unlike 2nd block we are not initializing j for each i . so how may times loop will be executed ? 1*n ( first time i=0 inner loop will execute n times and outer loop will executed 1 times) + n-1( i=1 to n-1) times = 2n-1 now we will eliminate constants so it will become n ,
	time complexities O(n),&#x2126;(1) and
    &#920;(n)
</span>

 ```c
   void  merge(int a, int b, int low,int mid, int high)
   {
         // some O(n) operation
  }  
   void mergesort(int a, int b, int low, int high) // T(n)
		
		{

            int mid;
		    if(low<high)
		    {
		        mid=(low+high)/2;      // O(1)
		        mergesort(a,b,low,mid); // T(n/2)
		        mergesort(a,b,mid+1,high); // T(n/2)
		        merge(a,b,low,mid,high);  // O(n)
		    }


		}
		 
```
<span class="list-group-item conv"> <span style="color: #DB4437;">For recursive function:</span>
for recursive function like above you need to calculate time complexity using back substitution algorithm. lets see how this works.
suppose time complexity of this function is T(n)<br>
then how can we write T(n)? <br>
T(n) = 2T(n/2) + cn  &nbsp;&nbsp;&nbsp;&nbsp;  ---- (1) (neglected O(1) operation) <br>
T(n/2) = 2T((n/2)/2) + cn/2 <br>
T(n/2) = 2T(n/4) + cn/2 <br>
now substitute value of T(n/2) into equation (1) we will get <br>
T(n) = 2 * 2T(n/4) + 2* cn/2 + cn  <br> 
T(n) = 4T(n/4) + 2cn  <br>
from above observation you would get following result<br>
T(n) = 2<sup>k</sup>*T(n/2<sup>k</sup>) + kcn <br>
when n=1 then T(n)=1 <br>
 so, n/2<sup>k</sup> = 1 <br>
 2<sup>k</sup> = n <br>
 k = log2(n) <br>
on substituting value k in T(n) ,T(n) = 1 + log(n)*c*n<br>
so time complexity would be O(nlogn)<br>
we can also calculate this using [master's theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms)) also but this is
more generalized method.

<span class="list-group-item conv" ><span style="color: #F4B400;">2.Space Complexity:</span><br>
if you have learned above concepts then you already know how to calculate sapce complexity . This article become long that's why i wouldn't discussed this. for 5 min read  go to [this](https://www.cs.northwestern.edu/academics/courses/311/html/space-complexity.html) link
</span> 


 

