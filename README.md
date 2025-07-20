

## 1. Basic

### 1.1 C++ Solution Template

```c++
#include <bits/stdc++.h>

#define DEBUG false
#define OJ_DEBUG

#define $(x) {if (DEBUG) {cout << __LINE__ << ": "; {x} cout << endl;}}
#define _(x) {cout << #x << " = " << x << " ";}

const double E = 1e-8;
const double PI = acos(-1);

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    
}
```

#### 1.1.1 Optional include list

> Use it when there is no `bits/stdc++.h`

```c++
#include <iostream>
#include <cstring>
#include <cmath>
#include <algorithm>
#include <climits>
#include <stack>
#include <queue>
#include <vector>
#include <set>
#include <map>
#include <list>
#include <cassert>
#include <unordered_map>
```

### 1.2 Strings

#### 1.2.1 C++ String
##### Read a String Till First Space

cin

```C++
string a;
cin>>a
cout << a << endl;
```

Input

```
Hello World!!!
```

Output

```
Hello
```
##### Read One Line With Spaces till \n or EOF

getline()

```C++
string a;
getline(cin, a);
cout << a << endl;
```

Input

```
Hello World!!!
```

Output

```
Hello World!!!
```

##### Convert to char array

```C++
string cppstr = "this is a string";
char target[1024];
strcpy(target, cppstr.c_str());
```

#### 1.2.2 C String (Character Array)

##### Input C String

gets()

> Reads characters from the standard input (stdin) and stores them as a C string into str until a newline character or the end-of-file is reached.

```c++
char s[12];
gets(s);
cout << "\"" << s << "\"" << ", length: " << strlen(s) << endl;
```

Input

```
hello world
new line
```

Output

```
"hello world", length: 11
```

##### Convert to C++ string

```c++
char arrstr[] = "this is a string";
string target = string(arr);
```

### 1.3 STL Algorithm

> Include the algorithm library if you do not use the solution template.

```C++
#include <algorithm>
```

#### 1.3.1 Permutation

Usage
```c++
bool next_permutation (BidirectionalIterator first, BidirectionalIterator last);
bool next_permutation (BidirectionalIterator first, BidirectionalIterator last, Compare comp);
```

Example

```C++
// next_permutation example
#include <iostream>     // std::cout
#include <algorithm>    // std::next_permutation, std::sort

int main () {
  int myints[] = {1,2,3};

  std::sort (myints,myints+3);

  std::cout << "The 3! possible permutations with 3 elements:\n";
  do {
    std::cout << myints[0] << ' ' << myints[1] << ' ' << myints[2] << '\n';
  } while ( std::next_permutation(myints,myints+3) );

  std::cout << "After loop: " << myints[0] << ' ' << myints[1] << ' ' << myints[2] << '\n';

  return 0;
}
```

Output

```
The 3! possible permutations with 3 elements:
1 2 3
1 3 2
2 1 3
2 3 1
3 1 2
3 2 1
After loop: 1 2 3
```

#### 1.3.2 Binary Search

Usage

```C++
bool binary_search (ForwardIterator first, ForwardIterator last, const T& val, Compare comp);
// return true if found, false if not
```

#### 1.3.3 Lower Bound

> Returns an iterator pointing to the first element in the range [first,last) which does not compare less than val.

Usage

```c++
ForwardIterator lower_bound (ForwardIterator first, ForwardIterator last, const T& val, Compare comp);
```

#### 1.3.4 Swap

Usage

```c++
void swap (T& a, T& b);
void iter_swap (ForwardIterator1 a, ForwardIterator2 b);
```

`iter_swap` example

```C++
int myints[]={10,20,30,40,50 };              //   myints:  10  20  30  40  50
std::vector<int> myvector (4,99);            // myvector:  99  99  99  99

std::iter_swap(myints + 3,myvector.begin() + 2); //   myints:  99  20  30 [99] 50
                                             // myvector:  10  99 [40] 99
```

#### 1.3.5 Heap

* make_heap: Rearranges the elements in the range [first,last) in such a way that they form a heap. The element with the highest value is always pointed by first.
* pop_heap: Rearranges the elements in the heap range [first,last) in such a way that the part considered a heap is shortened by one: The element with the highest value is moved to (last-1).
* push_heap: Given a heap in the range [first,last-1), this function extends the range considered a heap to [first,last) by placing the value in (last-1) into its corresponding location within it.
* sort_heap: Sorts the elements in the heap range [first,last) into ascending order.

Usage

```c++
void make_heap (RandomAccessIterator first, RandomAccessIterator last, Compare comp);
void pop_heap (RandomAccessIterator first, RandomAccessIterator last, Compare comp);
void push_heap (RandomAccessIterator first, RandomAccessIterator last, Compare comp);
void sort_heap (RandomAccessIterator first, RandomAccessIterator last); Compare comp);
```

#### 1.3.6 Sort

> Sorts the elements in the range [first,last) into ascending order.
`stable_sort` preserves the relative order of the elements with equivalent values.

Usage

```c++
void sort (RandomAccessIterator first, RandomAccessIterator last, Compare comp);
void stable_sort ( RandomAccessIterator first, RandomAccessIterator last, Compare comp );
```


##### Compare function

> Binary function that accepts two elements in the range as arguments, and returns a value convertible to bool. It should returns true if the first element is considered to be "smaller" than the second one.

Using by `sort`, `make_heap` and etc.

```c++
bool myfunction (int i,int j) { return (i<j); }
```



#### 1.4.1 Map




##### Commonly used method

```
begin()
end()

empty()
size()

operator[] // if not found, insert one

insert(pair<first type, second type)
erase()
clear()

find() // if not found, return end()
count() // return 1 or 0
```


##### Hash Map (Unordered Map)

> Unordered map is implemented as a hash table.

```c++
#include <unordered_map>
```


##### Commonly used method

``` C++
// most are similar to map
```

// TODO add more interface

#### 1.4.2 Pair

#### 1.4.3 Vector

##### Constructor

```c++
std::vector<int> second (4,100);  // four ints with value 100
```

##### Methods

* begin(), end()
* front(), back()
* clear()
* size()
* push_back(const value_type& val)
* pop_back()

#### 1.4.4 List

> List containers are implemented as doubly-linked lists.

##### Methods

* begin(), end()
* front(), back()
* clear()
* push_front(const value_type& val)
* push_back(const value_type& val)
* pop_front(): remove the first element.
* pop_back(): remove the last element.
* remove(const value_type& val): remove all elements of value val.
* insert(iterator position, const value_type& val)
* size()
* reverse()
* sort(), sort (Compare comp)
* 
* resize()
* reserve()

#### 1.4.5 Queue

```C++
#include <queue>
```
Constructor
```C++
queue<int> my_queue;
queue<int, list<int> > my_queue (my_list);
// use list<int> as container, copy my_list into my_queue
```
Methods
```C++
void queue::push(const value_type& val);
void queue::pop();
bool queue::empty() const;
size_type queue::size() const;
const_reference& queue::front() const;
```

# 1.4.7 Stack

``` c++
#include <stack>
```

Constructor
```C++
stack<int, vector<int> > my_stack (my_data);
// use vector<int> as container, copy my_data into my_stack
#### 1.4.8 Priority Queue

``` c++
#include <queue>
```

```C++
// constructor
priority_queue<int> my_priority_queue;
priority_queue<int, vector<int>, greater<int> > two_priority_queue; // if use greater<int>, must have vector<int>
priority_queue<My_type, vector<My_type>, Comparator_class> my_priority_queue (my_data.begin(), my_data.end()); // use Comparator_class as comparator, use vector<My_type> as container, copy my_data into my_priority_queue

bool priority_queue::empty() const; // return true if empty, false if not
size_type priority_queue::size() const; // return size of queue
const_reference priority_queue::top() const; // returns a constant reference to the top element
void priority_queue::push(const value_type& val); // inserts a new element, initialize to val
void priority_queue::pop(); // removes the element on top
```
```C++
struct My_type {
    int weight;
    int other;
};

struct My_class_for_compare {
    public:
        bool operator() (My_type a, My_type b) {
            return a.weight < b.weight;
        }
};

vector<My_type> my_vector = {(My_type){2, 789}, (My_type){1, 127}, (My_type){3, 456}};

priority_queue<My_type, vector<My_type>, My_class_for_compare> one_priority_queue (my_vector.begin(), my_vector.end());
one_priority_queue.push((My_type){4, 483});
while (one_priority_queue.size() != 0) {
    My_type temp = one_priority_queue.top();
    one_priority_queue.pop();
    SHOW_B(temp.weight, temp.other);
}

vector<int> my_int = {2, 3, 1};

priority_queue<int, vector<int>, greater<int> > two_priority_queue (my_int.begin(), my_int.end());
while (two_priority_queue.size() != 0) {
    SHOW_A(two_priority_queue.top());
    two_priority_queue.pop();
}

priority_queue<int> three_priority_queue (my_int.begin(), my_int.end());
while (three_priority_queue.size() != 0) {
    SHOW_A(three_priority_queue.top());
    three_priority_queue.pop();
}


// output
// temp.weight = 4, temp.other = 483
// temp.weight = 3, temp.other = 456
// temp.weight = 2, temp.other = 789
// temp.weight = 1, temp.other = 127
// two_priority_queue.top() = 1
// two_priority_queue.top() = 2
// two_priority_queue.top() = 3
// three_priority_queue.top() = 3
// three_priority_queue.top() = 2
// three_priority_queue.top() = 1
```


#include <stdio.h>
#include <sstream>
#include <iomanip>
#include <cstring>
#include <cmath>
#include <algorithm>
#include <climits>
#include <vector>
#include <stack>
#include <queue>
#include <set>
// #include <unordered_set>
#include <map>
// #include <unordered_map>
#include <cassert>

#define SHOW(...) {;}
#define REACH_HERE {;}
#define LOG(s, ...) {;}
#define LOGLN(s, ...) {;}

// #undef HHHDEBUG
#ifdef HHHDEBUG
#include "template.h"
#endif

using namespace std;

int len(unsigned long long x) {
	if (x == 0)
		return 1;

	int ret = 0;
	while (x > 0) {
		ret++;
		x /= 10;
	}
	return ret;
}

unsigned long long will_boom(unsigned long long a, unsigned long long b) {
    if (a == ULLONG_MAX || b == ULLONG_MAX)
        return ULLONG_MAX;
    
	int la = len(a);
	int lb = len(b);
	if (la - 1 + lb - 1 + 1 > 20)
		return ULLONG_MAX;
	return a * b;
}





#### 2.2.3 Lowest Common Ancestor

> Reduction from LCA to RMQ
>
> let n = number of nodes in the tree
>
> preprocess: euler tour O(n) + RMQ init O(nlog(n))
> 
> query: RMQ O(1)


```c++

ray
	// to get a matched range
	// let m = pattern.length()
	// let n = s.length()
	// time complexity: O(mlog(n))
}
```

#### 2.5.3 Longest Common Prefix

> length of common prefix between suffix_array[i-1] and suffix_array[i]
>
> let n = s.length()
>
> O(n)

```c++

//
// ...
//

int longest_common_prefix[HH]; // lcp[i] = length of common prefix between sa[i-1] and sa[i]
int phi[HH]; // phi[sa[i]] = sa[i-1] // naming ? // useless when built
int permuted_lcp[HH]; // useless when built temp for lcp

void compute_lcp() {
	// theorem: number of increase/decrese on cur_lcp is O(len)
	// so time complexity: O(len) for computing lcp
	int len = s.length();
	phi[suffix_array[0]] = -1;
	for (int i = 1; i < len; i++)
		phi[suffix_array[i]] = suffix_array[i - 1];
	for (int i = 0, cur_lcp = 0; i < len; i++) {
		if (phi[i] == 0)
			permuted_lcp[i] = 0;
		else {
			while (s[i + cur_lcp] == s[phi[i] + cur_lcp])
				cur_lcp++;
			permuted_lcp[i] = cur_lcp;
			cur_lcp = max(cur_lcp - 1, 0);
		}
	}
	for (int i = 0; i < len; i++)
		longest_common_prefix[i] = permuted_lcp[suffix_array[i]];

	for (int i = 0; i < len; i++)
		cout << "i: " << i << ", suffix " << suffix_array[i] << " (lcp: " << longest_common_prefix[i] << ") : " << s.substr(suffix_array[i], s.length() - suffix_array[i]) << endl;
	cout << endl;
}
```

#### 2.5.4 Longest Repeated Substring

> let n = s.length()
>
> O(n)

```c++
void longest_repeated_substring() {
	int len = s.length();
	int max_repeated = -1;
	int i_max = -1;
	for (int i = 0; i < len; i++) {
		if (longest_common_prefix[i] > max_repeated) {
			max_repeated = longest_common_prefix[i];
			i_max = i;
		}
	}
	cout << "longest repeated substring: " << s.substr(suffix_array[i_max], max_repeated) << endl;
}
```

#### 2.5.5 Longest Common Substring

> string a, b (also applies to multiple strings)
>
> construct Suffix Array of a.b & find Longest Common Prefix
>
> let n = max(a.length(), b.length())
>
> O(nlog(n) + n)

```c++
void longest_common_substring(const string& a, const string& b) {
	s = a + base_char + b;
	cout << "concatenated string: " << s << endl;
	
	build_suffix_array();
	compute_lcp();

	int len = s.length();
	int max_common = -1;
	int i_max = -1;
	for (int i = 1; i < len; i++) {
		int cur_lcp = longest_common_prefix[i];
		if (cur_lcp > max_common) {
			if ((suffix_array[i] < a.length()) ^ (suffix_array[i - 1] < a.length())) {
				max_common = cur_lcp;
				i_max = i;
			}
		}
	}
	cout << "longest common prefix: " << s.substr(suffix_array[i_max], max_common) << endl;
}
```



### 3.2 Dynamic Programming

#### 3.2.1 Longest Increasing Subsequence (LIS)

> O(nlog(n))

```c++
vector<int> sequence;
vector<int> lis(sequence.size() + 1, INT_MAX); // [i]: min value in sequence that have LIS = i
for (int i = 0; i < sequence.size(); i++) {
    int r = sequence[i];
    auto ptr = lower_bound(begin(lis), end(lis), r);
    *ptr = min(*ptr, r);
}
```



### 6.3 Number Theory

#### / gcd

```c++
int gcd(int a, int b) {
    return b == 0 ? a : gcd(b, a % b);
}

int lcm(int a, int b) {
   if(gcd(a,b)>0){ 
   	return (a / gcd(a, b)) * b;
   }
   return 0;
   
}
```
