# Lab-7_202001223

# Section - A

Design the equivalence class test cases

* Equivalence classes

  EC1 - date >=1 and date <= 31
  
  EC2 - date < 1
  
  EC3 - date > 31
  
  EC4 - month >= 1 and month <= 12
  
  EC5 - month < 1
  
  EC6 - month > 12
  
  EC7 - year >= 1900 and year <= 2015
  
  EC8 - year < 1900
  
  EC9 - year > 2015

  The dates should not be invalid - 30-02-2020 is an invalid date, since month 2 doesnot have 31 days.
  12 - 13 - 2005 is an example of out of range date.

* Equivalent test cases

  EC1 - day - 27, month - 7, year - 2003
  output - 26-07-2003

  EC2 - day - 0, month - 7, year - 2012
  output - Invalid date

  EC3 - day - 33, month - 2, year - 2012
  output - Invalid date

  EC4 - day - 1, month - 1, year - 1960
  output - 31/12/1959

  EC5 - day - 11, month - -3, year - 2001
  output - Invalid date

  EC6 - day - 12, month - 15, year - 2003
  output - Invalid date

  EC8 - day - 25, month - 12, year - 1899
  output - Invalid date

  EC9 - day - 13, month - 4, year - 2023
  output - Invalid date

* Valid dates - calculate previous dates

  1. 04-10-2010
  output - 03-10-2010

  2. 01-01-1975
  output - 31-12-1974

* Invalid dates 

  1. 13-04-2023
  2. 14-23-1899

* Boundary Value Analysis

  1. Earliest date - 1-01-1900
  2. Last possible date - 31-12-2015
  3. leap year - 29-02-2004
  4. invalid leap year date - 27-07-2003
  5. previous of earliest date - 31-12-1899
  6. a day after latest date - 01-01-2016


# Programs

# P1 
- The function linearSearch searches for a value v in an array of integers a. If v appears in the array
a, then the function returns the first index i, such that a[i] == v; otherwise, -1 is returned.
<pre>
public class lab7_1_lTest {
	public static int linearSearch(int v, int[] a) {
	    int i = 0;
	    while (i < a.length) {
	        if (a[i] == v) {
	            return i;
	        }
	        i++;
	    }
	    return -1;
	}
}
</pre>

<pre>
Equivalence Partitioning 

if v is present in a ------------> return index of v
if v is not present -------------> return -1

Boundary Value Analysis

empty array -----> return -1
not present -----> return -1
present at i=0 ---. return 0
</pre>

* Test Cases

1. v = 3; a[] = {1,2,3}; expected = 2

Test case passed!

![image](https://user-images.githubusercontent.com/123479469/231426798-50bef4db-d919-49d8-ba82-cccd5157cf6e.png)

2. v = 3; a[] = {1,2,4,5}; expected = 2

Test case failed!

![image](https://user-images.githubusercontent.com/123479469/231427614-cc32019d-b09a-49e5-b57a-b390b5f8e20d.png)

3. v = 3; a[] = {}; expected =-1;

Test case Passed!

![image](https://user-images.githubusercontent.com/123479469/231429497-3d842749-c599-4a83-bea4-56c6f834f690.png)

4. v = 10; a[] = {10,20,30}, expected = 0;

Test case Passed!

![image](https://user-images.githubusercontent.com/123479469/231430013-e83df95b-1729-40ea-b2a4-ffdcd63fb88c.png)


# P2 
- The function countItem returns the number of times a value v appears in an array of integers a.

<pre>
public class lab7_2_ltest {
	public static int countItem(int v, int a[])
	{
	int count = 0;
	for (int i = 0; i < a.length; i++)
	{
	if (a[i] == v)
	count++;
	}
	return (count);
	}
}
</pre>

<pre>
Equivalence Partitioning 

if v is present in a ------------> return number of times v appears
if v is not present -------------> return 0

Boundary Value Analysis

empty array -----> return 0
not present -----> return 0
present at i=0 ---> return 1
present multiple times ----> return count
</pre>
* Test cases

  1. v = 3; a[] = {1,2,3,3,3}; expected = 3

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231432035-788e9c27-f557-48d7-9255-3ad9e3579a53.png)

  2. v = 3; a[] = {1,2,4}; expected = 0

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231433724-7b6e9a7e-f082-4adc-8ad7-1dd4a27e20d8.png)

  3. v = 3; a[] = {}; expected = 0

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231433906-10d7d34e-529d-47c0-8c13-79ca406e0978.png)

  4. v = 10; a[] = {10, 20, 10}; expected = 1

  test case failed!

  ![image](https://user-images.githubusercontent.com/123479469/231434201-920886a5-55d0-4919-8a75-b2e8c5479135.png)


# P3 
- The function binarySearch searches for a value v in an ordered array of integers a. If v appears in
the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.
Assumption: the elements in the array a are sorted in non-decreasing order.

<pre>

public class lab7_3_lTest {
	public static int binarySearch(int v, int a[])
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
}
</pre>

<pre>
Equivalence Partitioning 

if v is present in a ------------> return index of v
if v is not present -------------> return -1

Boundary Value Analysis

empty array -----> return -1
not present -----> return -1
present at i=0 ---. return 0
</pre>


* Test Cases

  1. v = 3; a[] = {1,2,3,4,5}; expected = 3

  Test case failed!

 ![image](https://user-images.githubusercontent.com/123479469/231435489-213b225a-f001-42fa-80ce-9ab8cfe829c2.png)

  2. v = 3; a[] = {1,2,3,4,5}; expected = 2

  Test case passed!

 ![image](https://user-images.githubusercontent.com/123479469/231435612-70f56b7c-c137-40a3-bc52-07a591d34143.png)

  3. v = 5; a[] = {1,2,3,4,5,5}; expected = 4

  Test case passed!

 ![image](https://user-images.githubusercontent.com/123479469/231436256-953c7385-b990-4654-9452-4dbe7f2e937d.png)

  4. v = 5; a[] = {1,2,3}; expected = -1

  Test case passed!

 ![image](https://user-images.githubusercontent.com/123479469/231436516-7886ff36-198b-4224-906a-0758102997b7.png)

  5. v = 5; a[] = {1,2,3}; expected = 1

  Test case failed!

 ![image](https://user-images.githubusercontent.com/123479469/231436707-bced6a82-3373-49c7-b879-1e6ca6dda421.png)


# P4 
- The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). The
function triangle takes three integer parameters that are interpreted as the lengths of the sides of a
triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal),
scalene (no lengths equal), or invalid (impossible lengths).

<pre>

public class lab7_4_lTest {
	final int EQUILATERAL = 0;
	final int ISOSCELES = 1;
	final int SCALENE = 2;
	final int INVALID = 3;
	public  int triangle(int a, int b, int c)
	{
	if (a >= b+c || b >= a+c || c >= a+b)
		return(INVALID);
	if (a == b && b == c)
		return(EQUILATERAL);
	if (a == b || a == c || b == c)
		return(ISOSCELES);
		return(SCALENE);

	}
}

</pre>

<pre>
Equivalence Partitioning

a+b<=c -----------> INVALID
a=b=c ------------> Equilateral Triangle
a=b < c ------------> Isosceles Triangle
a< b < c ------------> Scalene Triangle

Boundary Value Analysis

a+b<=c ------> Invalid
b+c<=a ------> Invalid
c+a<=b ------> Invalid
a=b=c -------> Equilateral
a=b < c -------> Isosceles
b=c < a -------> Isosceles
c=a < b -------> Isosceles
a< b< c -------> Scalene

</pre>

* Test cases

  1. a = 3; b=3; c = 3; expected = 0 (equilateral)

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231439820-05ac4751-85fb-40f9-9339-32ca43245bb9.png)

  2. a = 1, b= 2, c= 3; expected = 0

  Test case failed!

  ![image](https://user-images.githubusercontent.com/123479469/231440133-80898353-58a9-41d7-93aa-e97644be8cde.png)

  3. a = -1, b = 2, c = 3, expected = 2

  Test case failed!

  ![image](https://user-images.githubusercontent.com/123479469/231440695-fe68346d-6476-4173-93a9-4897a73735bd.png)

  4. a = 3, b = 2, c = 3, expected = 1

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231440916-6a51fe17-b10e-42e1-a183-6cae225606f1.png)

  4. a = 4, b = 2, c = 3, expected = 2

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231441123-bb6f0a32-b6ef-48ee-ae23-20eb0661ab9e.png)



# P5 
- The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix
of string s2 (you may assume that neither s1 nor s2 is null).

<pre>
public class lab7_5 {
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
}
</pre>

<pre>
Equivalence Partitioning

empty s1 and s2 -----> true
empty s1 ------> true
s1 prefix of s2 ---> true
s1 not prefix of s2 ---> false
s1 longer than s2 ----> false

Boundary value analysis

empty s1 and s2 -----> true
empty s1 ------> true
s1 prefix of s2 ---> true
s1 longer than s2 ----> false

</pre>

* Test cases

  1. String s1 = "abc", s2 = "abcd"; expected = true

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231484300-1db67a0b-2697-46ff-a5cb-8e6d58456ccd.png)

  2. String s1 = "abc", s2 = "ab"; expected = true

  Test case failed!

  ![image](https://user-images.githubusercontent.com/123479469/231484719-7b59cbac-99d9-40da-8648-0dbb9e86201f.png)

  3. String s1 = "abc", s2 = "ab"; expected = false

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231485406-48e0c84d-f85d-4db4-a6a8-1a784e495018.png)

  4. String s1 = "abc", s2 = "abef"; expected = false

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231485967-583ca06a-05c2-4809-9540-24e43905990f.png)

  5. String s1 = "", s2 = "abef"; expected = true

  Test case passed!

  ![image](https://user-images.githubusercontent.com/123479469/231486226-22e60e43-d013-4053-8310-6081467596a2.png)


# P6 
- Consider again the triangle classification program (P4) with a slightly different specification: The program
reads floating values from the standard input. The three values A, B, and C are interpreted as
representing the lengths of the sides of a triangle. The program then prints a message to the standard output
that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.
Determine the following for the above program:

a) Identify the equivalence classes for the system

Equivalence Classes will contain:
1. All sides are positive, real numbers.
2. One or more sides are negative or zero.
3. The sum of the lengths of any two sides is less than or equal to the length of the remaining side.
4. The sum of the lengths of any two sides is greater than the length of the remaining side.

<pre>
Examples

E1 : a+b<=c (point 3)
E2 : a+c<=b (point 3)
E3 : b+c<=a (point 3)
E4 : a=b, b=c, c=a
E5 : a=b, a!=c 
E6 : a=c, a!=b
E7 : b=c, b!=a 
E8 : a!=b ,b!=c, c!=a
E9 : a^2 + b^2 = c^2 
E10: b^2 + c^2 = a^2
E11: a^2 + c^2 = b^2
E12 : a+b>=c (point 4)
E13 : a+c>=b (point 4)
E14 : b+c>=a (point 4)
</pre>

b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.

* Test cases
1. Right angled triangle (point 1 of (a)) - A = 3, B = 4, C = 5
2. Equilateral triangle (point 1 of (a)) - A = 7, B = 7, C = 7
3. Scalene triangle (point 1 of (a)) - A = 3, B = 4, C = 5
4. Isosceles triangle (point 1 of (a)) - A = 3, B = 5, C =3
4. Invalid Input - A = 1, B = 2, C = 6
5. Invalid Input - A = 0, B = 4, C = -1

c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.

* Test cases
1. A = 2, B = 3, C = 6
2. A = 5, B = 1, C = 6
3. A = 3, B = 4, C = 5

d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.

* Test cases
1. A = 5, B = 3, C = 5
2. A = 5, B = 3, C = 4.9
3. A = 5, B = 3, C = 5.1

e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.

* Test cases
1. A = 7, B = 7, C = 7
2. A = 7, B = 6.9, C = 7.1

f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.

* Test cases
1. A = 3, B = 4, C = 5
2. A = 5, B = 12, C = 13

g) For the non-triangle case, identify test cases to explore the boundary.

* Test cases
1. A = 2, B = 2, C = 4
2. A = 2, B = 4, C = 2

h) For non-positive input, identify test points.

* Test cases
1. A = -9, B = 3, C = 4.5
2. A = 0, B = 8, C = 3

# SECTION B

1. Control Flow Graph

![image](https://user-images.githubusercontent.com/123479469/231516744-1ec1e4b7-e4ed-42f6-8908-33a2906b55a6.png)

2. Construct test sets for your flow graph that are adequate for the following criteria:
a. Statement Coverage.
b. Branch Coverage.
c. Basic Condition Coverage.

a) Statement coverage test sets:

* Test cases 
<pre>
1. p is an empty vector
2. p is a vector with one point
3. p is a vector with two points having same y component
4. p is a vector with two points having different y components
5. p is a vector with three or more different points with different points with same y components
6. p is a vector with three or more different points with different points with different y components
</pre>
b) Branch coverage test sets: 

* Test cases
<pre>
1. p is an empty vector
2. p is a vector with one point
3. p is a vector with two points having same y component
4. p is a vector with two points having different y components
5. p is a vector with three or more different points with different points with same y components and with same x components.
6. p is a vector with three or more different points with different points with different y components and with same x components.
7. p is a vector with three or more points with the same x and y components
</pre>

c) Basic condition coverage test sets: 

* Test cases
<pre>
1. p is an empty vector
2. p is a vector with one point
3. p is a vector with two points having same y component
4. p is a vector with two points having different y components
5. p is a vector with three or more different points with different points with same y components and with same x components.
6. p is a vector with three or more different points with different points with different y components and with same x components.
7. p is a vector with three or more points with the same x and y components
8. p is a vector with some of them having same x component and all of them having same y component
</pre>
* Test cases examples: 
<pre>
1) p=[(x=2,y=3),(x=2,y=2),(x=1,y=5),(x=1,y=4)]
2) p=[(x=5,y=6),(x=3,y=2),(x=3,y=4),(x=1,y=2)]
3) p=[(x=5,y=6),(x=3,y=5),(x=1,y=5),(x=4,y=5),(x=2,y=7)]
4) p=[(x=7,y=8)]
5) p=[]
</pre>

These 5 test cases covers all - branch coverage,statement coverage and basic condition coverage. 


