Consider a program for determining the previous date. Its input is triple of day, month and year with the
following ranges 1 <= month <= 12, 1 <= day <= 31, 1900 <= year <= 2015.The possible output dates would be
previous date or invalid date. Design the equivalence class test cases?

Equivalence class test cases:

Equivalent classes: 
E1  = {1<=date<=31}

E2 =  { date<1}


E3= {date >31 } 

E4 = {1<=month <=12}

E5 = { month <1}


E6 = {month >12}

E7 = {1900<=year<=2015}

E8 = {year <1900}

E9 = {year>2015 } 

There are 9 equivalent classes 

Equivalent test cases :

Equivalent class 

![Screenshot (479)](https://user-images.githubusercontent.com/85830046/231547200-47fb2cd3-9e79-43f0-9470-126ce5e62c9a.png)



Programs
P1: 
The function linearSearch searches for a value v in an array of integers a. If v appears in the array
a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.
int linearSearch(int v, int a[])
{
int i = 0;
while (i < a.length)
{
if (a[i] == v)
return(i);
i++;
}
return (-1);
}

Test cases : 
v=2  , a={4,3,2}  expected output = 2



v=3  , a={4,2,1} expected output = -1 



v=4 , a={}  expected output = -1



v=20 , a= {10,20,30,20,40} expected output = 1



P2 :  
The function countItem returns the number of times a value v appears in an array of integers a.

int countItem(int v, int a[])

{
int count = 0;
for (int i = 0; i < a.length; i++)
{
if (a[i] == v)
count++;

}
return (count);
}


Test cases : 
1)v=2  , a={4,2,3,2,1}  expected output = 2

2)v=3 , a={4,2,3}  expected output =1

3) v= 20 , a= {1,2,3} expected output =0

4) v=1  , a ={}  , expected output = 0

P3. The function binarySearch searches for a value v in an ordered array of integers a. If v appears in

the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.

Assumption: the elements in the array a are sorted in non-decreasing order.

int binarySearch(int v, int a[])
{
int lo,mid,hi;
lo = 0;
hi = a.length-1;
while (lo <= hi)
{
mid = (lo+hi)/2;
if (v == a[mid])
return (mid);
else if (v < a[mid])
hi = mid-1;
else
lo = mid+1;

}
return(-1);
}
Test cases:


1) v=2 , a= { 0, 1,2,3,4}  expected output = 2

2) v= -4  ,  a= {1,2,3,4,5 } expected output = -1

3) v=5  ,  a= {2,3,4,5,5,6}   expected output = 3 or 4

P4. The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The
function triangle takes three integer parameters that are interpreted as the lengths of the sides of a
triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal),
scalene (no lengths equal), or invalid (impossible lengths).
final int EQUILATERAL = 0;
final int ISOSCELES = 1;
final int SCALENE = 2;
final int INVALID = 3;
int triangle(int a, int b, int c)
{
if (a >= b+c || b >= a+c || c >= a+b)
return(INVALID);
if (a == b && b == c)
return(EQUILATERAL);
if (a == b || a == c || b == c)
return(ISOSCELES);
return(SCALENE);

}

Test cases: 
1)a=4,b=4,c=4    expected output = EQUILATERAL

2)a=1,b=2,c=3   expected output= INVALID

3) a=-1,b=2,c=3 expected output = INVALID

4)a=3,b=4,c=5 expected output = SCALENE

5) a=5,b=5,c=9  expected output = ISOSCELES

6) a=5, b=5, c=10 expected output = INVALID

P5. The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix
of string s2 (you may assume that neither s1 nor s2 is null).
public static boolean prefix(String s1, String s2)
{
if (s1.length() > s2.length())
{
return false;
}
for (int i = 0; i < s1.length(); i++)
{
if (s1.charAt(i) != s2.charAt(i))
{
return false;
}
}
return true;
}

Test cases:
1)s1=”abc”, s2=”abcd”  , expected output =true


2)s1=”abd”  , s2=”abc”  , expected output = false


3)s1=”sdfs” , s2=”sdfs”, expected output=true


4) s1=”defg” , s2=”asdfsd”, expected output=false



P6: Consider again the triangle classification program (P4) with a slightly different specification: The program
reads floating values from the standard input. The three values A, B, and C are interpreted as
representing the lengths of the sides of a triangle. The program then prints a message to the standard output
that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.
Determine the following for the above program:
a) Identify the equivalence classes for the system

E1 : a+b<=c

E2 : a+c<=b

E3:  b+c <=a

E4 : a=b,b=c,c=a

E5 : a=b , a!=c 

E6: a= c, a!=b

E7: b=c, b!=a 

E8 : a!=b ,b!=c, c!=a

E9 : a^2 + b^2 = c^2 

E10: b^2+c^2 =a^2

E11: a^2 +c^2=b^2


b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case
would cover which equivalence class.
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence
classes)

Test case 
![Screenshot (481)](https://user-images.githubusercontent.com/85830046/231548799-97f7f274-e095-4ac7-911f-ae2b052fcba9.png)




c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.

	1)a=5 b=5 c=10
	
	2)a=5 b=5 c=9
	
	3)a=5 b=6 c=12
	
d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.

	1)a=5 b=4 c=5
	
	2)a=5 b=4 c=5.1
	
	3)a=5 b=4 c=4.9
	
e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.

	1)a=4 b=4 c=4
	
	2) a=4 b=3.9 c=4.1
	
f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.

	1)a=3,b=4,c=5
	
	2)a=5,b=12,c=13
	
g) For the non-triangle case, identify test cases to explore the boundary.

	1)a=1,b=2,c=3
	
	2)a=4.5 b=5.5 c=10
	
h) For non-positive input, identify test points.

a=-4.0 b=3.2 c=4.5

a=5,b=-4.2,c=-3.2


Section B:
The code below is part of a method in the ConvexHull class in the VMAP system. The following is a small
fragment of a method in the ConvexHull class. For the purposes of this exercise you do not need to know the
intended function of the method. The parameter p is a Vector of Point objects, p.size() is the size of the
vector p, (p.get(i)).x is the x component of the i

th point appearing in p, similarly for (p.get(i)).y. This exercise is
concerned with structural testing of code and so the focus is on creating test sets that satisfy some particular
coverage criterion.
For the given code fragment you should carry out the following activities.
1. Convert the Java code comprising the beginning of the doGraham method into a control flow graph
(CFG).

2. Construct test sets for your flow graph that are adequate for the following criteria:

a. Statement Coverage.

b. Branch Coverage.

c. Basic Condition Coverage.

Test cases : 
1) p=[(x=2,y=2),(x=2,y=3),(x=1,y=3),(x=1,y=4)]

2) p=[(x=2,y=3),(x=3,y=4),(x=1,y=2),(x=5,y=6)]

3) p=[(x=1,y=5),(x=2,y=7),(x=3,y=5),(x=4,y=5),(x=5,y=6)]


4) p=[(x=1,y=2)]

5) p=[]

These 5 test cases covers are adequate for statement coverage,branch coverage and basic condition coverage. 
