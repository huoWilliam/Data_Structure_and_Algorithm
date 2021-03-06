# Chapter 1

## exercise 1. 1

> For an array with a size of 100 elements, provide the number of steps that the following operations would take for:
> 
> 1. Reading
> 2. Searching
> 3. Insertion at the very beginning of the array
> 4. Insertion at the very end of the array
> 5. Deletion at the very beginning of the array
> 6. Deletion at the very end of the array

1. 需要1步，**数组的读取只需要1步**。

2. 最少需要1步，即目标元素在数组的第1个位置。最多需要100步，即目标元素不存在或者在数组的最后一个位置。

3. 需要101步，前100步移动数组，将第一个数组位置腾出，最后1步将元素插入即可。

4. 需要1步，PC可以直接确定最后一个位置，然后将元素插入即可。

5. 需要100步。第1步删除元素，后99步将剩余的元素向前移动。

6. 需要1步。删除最后一个位置的元素即可。

## exercise 1.2

> For an **array-based** *set* with a size of 100 elements, provide the number of steps that the following operations would take for:
> 
> 1. Reading
> 2. Searching
> 3. Insertion at the very beginning of the set
> 4. Insertion at the very end of the set
> 5. Deletion at the very beginning of the set
> 6. Deletion at the very end of the set

1. 需要1步。同数组读取。

2. 最少需要1步，最多需要100步。同数组查找。

3. 需要201步，前100步进行查找，判断插入元素是否已经重复了。再用100步移动元素，将第一个数组位置腾出，最后1步将元素插入即可。

4. 需要101步，前100步进行查找，判断插入元素是否已经重复了。最后1步在数组末尾插入元素即可。

5. 需要100步。同数组删除第一个元素。

6. 需要1步。同数组删除最后一个元素。

## exercise 1.3

> For a regular array, how many steps would it take to search for all of a certain item. For example, we want to search for every 55 contained within an array to determine how many times it appears. Give your answer in terms of N.

分最多和最少两种情况：n，表示目标元素出现的次数

最多步数的情况（所有目标元素都集中数组尾部）：则需要 `N! / (N - n - 1)!` 步

最少步数的情况（所有目标元素都集中数组头部）：需要 `n!` 步

## exercise 1.4

> How many steps would it take to delete all the 72’s from the following array: [72, 44, 66, 2019, 72, 55, 101, 72, 99, 2]. (The array would become [44, 66, 2019, 55, 101, 99, 2].)

分最多和最少两种情况：

最多步数的情况（顺序删除）：

1. 删除第1个72：删除元素，然后前移剩余元素，需要1+9=10步

2. 删除第2个72：需要1+5=6步

3. 删除第3个72：需要1+2=3步

4. 总共需要10+6+3=19步

最少步数的情况（逆序删除）：

1. 删除第3个72：需要1+2=3步

2. 删除第2个72：需要1+4=5步

3. 删除第1个72：需要1+7=8步

4. 总共需要3+5+8=16步

## exercise 1.5

> How many steps would it take to insert a 44 at both the beginning and end of the following array: [5, 6, 7, 8, 9, 10]. (The insertions would turn the array into: [44, 5, 6, 7, 8, 9, 10, 44].)

分最多和最少两种情况：

最多步数的情况：

1. 先在最后一个位置插入：需要1步

2. 再在第一个位置插入：移动元素，腾出位置，然后插入元素，需要7+1=8步

3. 总共需要1+8=9步

最少步数的情况：

1. 现在第一个位置插入：需要6+1=7步

2. 再在最后一个位置插入：需要1步

3. 总共需要7+1=8步

## [exercise 1.6](exe1_6.cpp)

> Use your favorite object-oriented programming language to create a class that represents an array-based set. It should include functions/methods that serve as the key operations: Read, search, insert, and delete. Ensure that the insert operation will not insert duplicate values.

# Chapter 2

## exercise 2.1

> There’s an age old puzzle that goes as follows: You’re at a river with two buckets. One holds exactly 3 liters, and one holds exactly 5 liters. Figure out how to measure out exactly 4 liters using those two buckets.
> 
> 1. Develop two different algorithms for measuring out 4 liters.
> 2. Which of your algorithms is more efficient? That is, how many steps does each algorithm take?

算法1：

1. 5L桶装满水。

2. 由5L桶向3L桶倒水，倒满为止。**5L桶中余下2L水。**

3. 把3L桶的水倒掉，由5L桶向3L桶倒水。**3L桶中现有2L水，5L桶中没有水。**

4. 5L桶装满水。

5. 由5L桶向3L桶倒水，倒满为止。**5L桶中现有4L水。**

算法2：

1. 将3升的桶装满，倒到5升里面，重复执行两次，此时**3升桶里面剩余1升。**

2. 将5升的桶中的谁倒掉，将第一步中的1升水倒入5升桶中。

3. 将3升的桶装满，向5升的桶中倒，则**5升桶中有4升水了。**

## exercise 2.2

> How many steps would it take to insert the number 7 into the ordered array of [2, 4, 6, 8, 10, 12]?

1. 搜索插入位置：4步

2. 元素后移：3步

3. 插入元素：1步

4. 总共需要 4 + 3 + 1 = 8步

## exercise 2.3

> How many steps would it take to search for the number 8 in the ordered array: [2, 4, 6, 8, 10, 12]?

使用二分查找算法需要2步。使用顺序查找需要4步。

## exercise 2.4

> How many steps does it take to perform binary search on array of size 200?

至多需要8步。

## exercise 2.5

> How many steps does it take to perform binary search on array of size 400?

至多需要9步。

## [exercise 2.6](exe2_6.cpp)

> Use your favorite object-oriented programming language to create a class that represents an ordered array. It should include functions/methods that serve as the key operations: Read, search, insert, and delete. Ensure that the insert operation inserts the value in the correct place within the ordered array.

# Chapter 3

## exercise 3.1

> Inspect the following algorithm, and describe its time complexity in terms of Big O Notation:
> 
> ```python
> x = 1
> while x < 100
>   print x
>   x += 1
> end
> ```

该算法总共会执行99步。用大O记法表示为 `O(N)`

## exercise 3.2

> In the below graph, six algorithms are depicted. The x axis represents the number of data elements, and the y axis represents how many steps the algorithm takes. By color, list the algorithms from fastest to slowest.
> 
> ![](https://commonsensecomputerscience.com/old-site/img/exercises/chapter_3_graph.png)

青色 > 紫色 > 橘色 > 绿色 > 红色 > 蓝色

## exercise 3.3

> How would you describe the following algorithm in terms of Big O Notation: Looking up someone in a phone book by starting with the first name in the book and reading each subsequent name until you find the name you’re looking for.

顺序查找的时间复杂度为 `O(N)`

## exercise 3.4

> How would you describe the following algorithm in terms of Big O Notation: Looking up someone in a phone book by starting with the middle of the book - and, when seeing that the name is higher or lower, jumping to the next halfway point, and so on until you find the correct name.

二分查找的时间复杂度为 `O(logN)`

## exercise 3.5

> How would you describe the following algorithm in terms of Big O Notation: You’d like to use one laptop to clone its operating system to 15 other laptops, so you take the original laptop, and one by one, you use it to clone each other laptop.

时间复杂度为 `O(N)`

## exercise 3.6

> How would you describe the following algorithm in terms of Big O Notation: You’d like to use one laptop to clone its operating system to 15 other laptops, so you take the first laptop and clone a second laptop. You then take the 2 completed laptops and clone 2 other laptops. You then take the 4 completed laptops to clone 4 other laptops. Finally, you take the 8 completed laptops and use them to clone 8 other laptops, so you end up with 16 completed laptops.

时间复杂度为 `O(logN)`

# Chapter 4

## exercise 4.1

> Regarding the array [50, 60, 70, 20, 30, 10]:
> 
> 1. Describe the exact steps that Bubble Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了 5+4+3+2+1=15次比较，同时进行了 3+3+3+1+1=11次交换。总共要使用26步，才能排序完成。

2. 15次

3. 11次

## exercise 4.2

> Regarding the array [10, 20, 30, 40, 50, 60]:
> 
> 1. Describe the exact steps that Bubble Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred

1. 数组已经有序了，进行5+4+3+2+1=15次比较就可以了。

2. 15次

3. 0次

## exercise 4.3

> Regarding the array [60, 50, 40, 30, 20, 10]:
> 
> 1. Describe the exact steps that Bubble Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了15次比较，和15次交换。总共要使用30步，才能排序完成。

2. 15次

3. 15次

## exercise 4.4

> Describe the following code in terms of Big O Notation:
> 
> ```python
> first_array = [5, 4, 9, 7, 2]
> second_array = [3, 1, 6, 8, 0]
> 
> first_array.each do |x|
>   second_array.each do |y|
>     print x * y
>   end
> end
> ```

假设 `first_array` 和 `second_array` 的元素个数都为N。则时间复杂度为 `O(N^2)`

# Chapter 5

## exercise 5.1

> Regarding the array [50, 60, 70, 20, 30, 10]:
> 
> 1. Describe the exact steps that Selection Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了5+4+3+2+1=15次比较，和4次交换。总共要使用19步，才能排序完成。

2. 15次

3. 4次

## exercise 5.2

> Regarding the array [10, 20, 30, 40, 50, 60]:
> 
> 1. Describe the exact steps that Selection Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了15次比较，0次交换。总共要使用15步，才能排序完成。

2. 15次

3. 0次

## exercise 5.3

> Regarding the array [60, 50, 40, 30, 20, 10]:
> 
> 1. Describe the exact steps that Selection Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了15次比较，5次交换。总共要使用20步，才能排序完成。

2. 15次

3. 5次

## exercise 5.4

> How would you describe in Big O Notation:
> 
> 1. An algorithm that takes 2N steps?
> 2. An algorithm that takes log(N / 2) steps?
> 3. An algorithm that always takes 2,532 steps?

1. `O(N)`

2. `O(N)`

3. `O(1)`

# Chapter 6

## exercise 6.1

> Regarding the array [50, 60, 70, 20, 30, 10]:
> 
> 1. Describe the exact steps that Insertion Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了1+1+3+4+5=14次比较，0+0+3+3+5=11次平移，5次的插入，5次的移除。总共要使用35步，才能排序完成。

2. 14次

3. 11次

## exercise 6.2

> Regarding the array [10, 20, 30, 40, 50, 60]:
> 
> 1. Describe the exact steps that Insertion Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了5次比较，0次平移，5次插入，5次移除。总共要使用15步，才能排序完成。

2. 5次

3. 0次

## exercise 6.3

> Regarding the array [60, 50, 40, 30, 20, 10]:
> 
> 1. Describe the exact steps that Insertion Sort would take on the array.
> 2. How many comparisons occurred?
> 3. How many swaps occurred?

1. 进行了15次比较，15次平移，5次插入，5次移除。总共要使用40步，才能排序完成。

2. 15次

3. 15次

## exercise 6.4

> Describe in the following cases whether Bubble Sort is more efficient, or Insertion Sort is more efficient.
> 
> 1. The best-case scenario.
> 2. An average-case scenario.
> 3. The worst-case scenario.

1. 最好情况下，冒泡排序等于插入排序

2. 平均情况下，插入排序优于冒泡排序

3. 最坏情况下，插入排序差于冒泡排序

# Chapter 7

## exercise 7.1

> Assume that we have a hash table with a superb load factor, which means that on average, there's only one piece of data in each cell. Describe in Big O Notation the efficiency of:
> 
> 1. Reading from the hash table.
> 2. Inserting into the hash table.
> 3. Deleting from the hash table.

1. `O(1)`

2. `O(1)`

3. `O(1)`

## exercise 7.2

> While we mentioned that an ideal load factor is 0.7, I’ve seen others say that 1 is an ideal load factor. If we followed this new advice, and we wanted to store 100 key/value pairs in a hash table, how many cells should it have?

需要100个格子。

## exercise 7.3

> If we had a hash function that distributes data evenly, and a load factor of 3, how many key/values would be stuffed into each cell on average?

3对键值对。

# Chapter 8

## exercise 8.1

> Describe the steps that occur when we add the numbers 5, 3, 9, 2, 8 to a stack and then remove each number from the stack.

入栈

【空栈】->入栈5【5】->入栈3【5，3】->入栈9【5，3，9】->入栈2【5，3，9，2】->入栈8【5，3，9，2，8】

出栈

【5，3，9，2，8】->出栈8【5，3，9，2】->出栈2【5，3，9】->出栈9【5，3】->出栈3【5】->出栈5【空栈】

## exercise 8.2

> Describe the steps that occur when we add the numbers 5, 3, 9, 2, 8 to a queue and then remove each number from the queue.

入队

【空队】->入队5【5】->入队3【5，3】->入队9【5，3，9】->入队2【5，3，9，2】->入队8【5，3，9，2，8】

出队

【5，3，9，2，8】->出队5【3，9，2，8】->出队3【9，2，8】->出队9【2，8】->出队2【8】->出队8【空队】

## [exercise 8.3](exe8_3.cpp)

> In your favorite programming language, use a stack to implement an algorithm that reverses a string.

# Chapter 9

## [exercise 9.1](exe9_1.cpp)

> You can technically use recursion to replace any loop. Write a function that prints to the terminal "HELLO" 10 times - but don’t use a loop! Use a recursive function instead.

## [exercise 9.2](exe9_2.cpp)

> Write a recursive function that prints out all even numbers from 2 until 100.

## [exercise 9.3](exe9_3.cpp)

> Fibonacci numbers are numbers that follow this pattern: 1, 1, 2, 3, 5, 8, 13, 21, 34, ... that is, each number is the sum of the two immediate numbers that precede it. Write a recursive function that prints out the list of fibonacci numbers up to 987.

## [exercise 9.4](exe9_4.cpp)

> Write a recursive function that accepts an array of numbers and returns the sum.

## [exercise 9.5](exe9_5.cpp)

> Write a recursive function that reverses a string.

## [exercise 9.6](exe9_6.cpp)

> Write a recursive function that accepts two numbers (a numerator and denominator), and returns the remainder if you divide the numerator by the denominator. The catch: Do not use the modulo operator!

## [exercise 9.7](exe9_7.cpp)

> Write a recursive binary search function.

## [exercise 9.8](exe9_8.cpp)

> Write a recursive function that accepts two numbers and calculates one by the power of the other. For example, if the numbers were 2 and 5, it would calculate 25. Do not use any built-in power operations provided by your computer language.

## [exercise 9.9](exe9_9.cpp)

> Write a recursive function that returns all anagrams of a string (even if the anagrams aren’t words themselves). For example, the anagrams of cat are cat, cta, act, atc, tac, tca.

# Chapter 10

## exercise 10.1

> Describe the exact steps that Quicksort would take for the following array: [90, 100, 20, 60, 80, 110, 120, 40, 10, 30, 50, 70].

1. 第一次分区：进行了13次比较，5次交换。【50，30，20，60，10，40，**70**，110，80，100，90，120】

2. 第二次分区：进行了13次比较，3次交换。【10，30，20，**40**，50，60，**70**，110，80，100，90，**120**】

3. 第三次分区：进行了13次比较，4次交换。【10，**20**，30，**40**，50，**60**，**70**，80，**90**，100，110，**120**】

4. 第四次分区：进行了3次比较，1次交换。【10，**20**，30，**40**，50，**60**，**70**，80，**90**，100，**110**，**120**】

5. 排序完成。

## exercise 10.2

> Create a table that compares the best-, middle-, and worst-case scenarios for Bubble Sort, Selection Sort, Insertion Sort, and Quicksort.

| 类别   | 最好情况       | 平均情况       | 最坏情况     |
| ---- | ---------- | ---------- | -------- |
| 冒泡排序 | `O(N)`     | `O(N^2)`   | `O(N^2)` |
| 选择排序 | `O(N^2)`   | `O(N^2)`   | `O(N^2)` |
| 插入排序 | `O(N)`     | `O(N^2)`   | `O(N^2)` |
| 快速排序 | `O(NlogN)` | `O(NlogN)` | `O(N^2)` |

## exercise 10.3

> Describe the exact steps that Quickselect would take for the second-to-lowest value in the following array: [90, 100, 20, 60, 80, 110, 120, 40, 10, 30, 50, 70].

1. 第一次分区：第一次分区：进行了13次比较，5次交换。【50，30，20，60，10，40，**70**，110，80，100，90，120】

2. 对左半部分进行分区：进行了7次比较，2次交换。【10，30，20，**40**，50，60，**70**，110，80，100，90，120】

3. 继续对左半部分进行分区：进行了4次比较，1次交换。【10，**20**，30，**40**，50，60，**70**，80，90，100，110，120】。故第二小的数字是20
