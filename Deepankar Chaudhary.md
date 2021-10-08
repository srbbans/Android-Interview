
https://proandroiddev.com/the-curious-case-of-survival-of-viewmodel-afe074992fbc


https://www.sitepoint.com/aidl-for-sharing-functionality-between-android-apps/




Android : Passing data between main thread and worker threads.
http://techtej.blogspot.com/2011/02/android-passing-data-between-main.html

why do we need to override equals and hashCode



https://medium.com/@abhilashmyworld/communicate-between-fragments-using-viewmodel-e83344e9df53

LAUNCH MODE:

https://medium.com/mindorks/android-launch-mode-787d28952959
`

What are the disadvantages of using inner classes?
* Using inner class increases the total number of classes being used by the application. For all the classes created by JVM and loaded in the memory, jvm has to perform some tasks like creating the object of type class. Jvm may have to perform some routine tasks for these extra classes created which may result slower performance if the application is using more number of inner classes.
* Inner classes get limited support of ide/tools as compared to the top level classes, so working with the inner classes is sometimes annoying for the developer.
1. Only being available within the context of the outer class. This will limit its use to any code outside the outer class. If there is functionality in that inner class that is useful in other areas, then that may be an issue.
2. Garbage collection. An object of an inner class automatically has a reference to the instance of its outer class. What that means is that if the outer object is not garbage collected, neither will the inner object, even though it is not being used anymore.
* 




onPause() is called when your activity is no longer at the top of the activity stack. A Dialog by itself is not an Activity, so will not replace the current Activity at the top of the stack, so will not cause anything to pause.
A dialog (lower-case) does not need to be implemented by a Dialog class, however. For example, it is not uncommon to implement one with an Activity whose theme is set to that of a dialog. In this case, displaying the dialog-as-an-Activity will cause the new Activity to be on the top of the stack, pausing what previously was there.

Fragment and activity life cycle call-backs:

https://google-developer-training.github.io/android-developer-advanced-course-concepts/unit-1-expand-the-user-experience/lesson-1-fragments/1-2-c-fragment-lifecycle-and-communications/1-2-c-fragment-lifecycle-and-communications.html


When the fragment is added to the backstack, and then getting replaced or removed - it will go like this:
onPause() -> onSaveInstanceState() -> onStop() -> onDestroyView() 
If the fragment is removed, or replaced without getting added to the back stack, then following happens:
onPause() -> onSaveInstanceState() -> onStop() -> onDestroyView()  -> onDestroy() -> onDetach() -> Fragment is destroyed.


The Fragment class has other useful lifecycle callbacks:
* onResume(): Called by the Activity to resume a Fragment that is visible to the user and actively running.
* onAttach(): Called when a Fragment is first attached to a host Activity. Use this method to check if the Activity has implemented the required listener callback for the Fragment (if a listener interface was defined in the Fragment). After this method, onCreate()is called.
* onActivityCreated(): Called when the Activity onCreate() method has returned. Use it to do final initialization, such as retrieving views or restoring state. It is also useful for a Fragment that uses setRetainInstance() to retain its instance, as this callback tells the Fragment when it is fully associated with the new Activity instance. The onActivityCreated() method is called after onCreateView() and before onViewStateRestored().
* onDestroyView(): Called when the View previously created by onCreateView() has been detached from the Fragment. This call can occur if the host Activity has stopped, or the Activity has removed the Fragment. Use it to perform some action, such as logging a message, when the Fragment is no longer visible. The next time the Fragment needs to be displayed, a new View is created. The onDestroyView() method is called after onStop() and before onDestroy().


Kotlin differfrnce betten run,apply,also ,let
Transient ,latent:

Val, var, lateinit, lazy
https://0xalihn.medium.com/kotlin-var-val-lateinit-lazy-get-when-to-use-what-bd50200b0a38#:~:text=lateinit%20var%20can%20be%20initialized,no%20immutability%20can%20be%20guaranteed



how app icon in internally work in android
https://android.jlelse.eu/android-application-launch-explained-from-zygote-to-your-activity-oncreate-8a8f036864b


THread executaion 


Important for interview:
How to make class immutable

Ans below
https://dzone.com/articles/how-to-create-an-immutable-class-in-java



MultiDex
Android application (APK) files contain executable bytecode files in the form of Dalvik Executable (DEX) files, which contain the compiled code used to run your app. The Dalvik Executable specification limits the total number of methods that can be referenced within a single DEX file to 65,536, including Android framework methods, library methods, and methods in your own code. Getting past this limit requires that you configure your app build process to generate more than one DEX file, known as a multidex configuration.


Next →
← Prev
Can we start a thread twice
No. After starting a thread, it can never be started again. If you does so, an IllegalThreadStateException is thrown. In such case, thread will run once but for second time, it will throw exception.


What if we call run() method directly instead start() method?
◦	Each thread starts in a separate call stack.
	◦	Invoking the run() method from main thread, the run() method goes onto the current call stack rather than at the beginning of a new call stack.
1. class TestCallRun1 extends Thread{  
2.  public void run(){  
3.    System.out.println("running...");  
4.  }  
5.  public static void main(String args[]){  
6.   TestCallRun1 t1=new TestCallRun1();  
7.   t1.run();//fine, but does not start a separate call stack  
8.  }  
9. }  

What if we call run() method directly instead start() method?
◦	Each thread starts in a separate call stack.
	◦	Invoking the run() method from main thread, the run() method goes onto the current call stack rather than at the beginning of a new call stack.

The join() method
The join() method waits for a thread to die. In other words, it causes the currently running threads to stop executing until the thread it joins with completes its task.

Overloading of run() method is possible. But Thread class start() method can invoke no-argument method. The other overloaded method we have to call explicitly like a normal method call.04-Oct-2017


CI CD pipe line jerkin


https://medium.com/avmconsulting-blog/automated-ci-cd-with-jenkins-39b21c7c8035



Android Solid principal:
https://android.jlelse.eu/android-development-the-solid-principles-3b5779b105d2


* 		Single Responsibility Principle
         
A class should have one, and only one, reason to change.


* 		Open-Closed Principle
  Software entities (classes, modules, functions, etc…) should be open for   extension, but closed for modification

* 		Liskov Substitution Principle
The Liskov Substitution Principle (LSP)
Child classes should never break the parent class’ type definitions.


* 		Interface Segregation Principle
he interface-segregation principle (ISP) states that no client should be forced to depend on methods it does not use.

This principale states that once an interface becomes too fat, it needs to be split into smaller interfaces so that client of the interface will only know about the methods that pertain to them. As you know, the Android View class is the root superclass for all Android views. You name it, if it’s a Button, the root superclass is View. Let’s dive to it, and show some code:


* 		Dependency Inversion Principle

1. High-level modules should not depend on low-level modules. Both should depend on abstractions.

2. Abstractions should not depend upon details. Details should depend upon abstractions.

As conclusion, we can said that the Single Responsibility Principle is about actors and high level architecture. The Open/Closed Principle is about class design and feature extensions. The Liskov Substitution Principle is about subtyping and inheritance. The Interface Segregation Principle (ISP) is about business logic to clients communication. And the Dependency Inversion Principale (DIP) is about leads or helps us respect all the other principles.


APPLY VS COMMIT SHARED PREF
https://stackoverflow.com/questions/5960678/whats-the-difference-between-commit-and-apply-in-sharedpreferences


Important for interview:
How to make class immutable

Ans below
https://dzone.com/articles/how-to-create-an-immutable-class-in-java

What is certificate pinning in Android?
Certificate pinning is the solution to this problem. It means hard-coding the certificate known to be used by the server in the mobile application. The app can then ignore the device's trust store and rely on its own, and allow only SSL connections to hosts signed with certificates stored inside the application.12-Mar-2014

Securing Mobile Banking on Android with SSL Certificate ...
infinum.com › the-capsized-eight › securing-mobile-ba...

1.  

Search for: What is certificate pinning in Android?

Pro guard interlnalwaroking

Memory Leak
https://www.geeksforgeeks.org/memory-leaks-in-android/

Android view life cycle 
https://proandroiddev.com/android-custom-view-level-3-81e767c8cc75

http://landenlabs.com/android/info/view-life-cycle/view-life-cycle.html

LRU CACHE Implementation
https://www.geeksforgeeks.org/lru-cache-implementation/


Kotlin preprations


- Any data class cannot have a modifier like abstract and open or internal. Data class can be extended to other classes too. In the following example, we will create one data class.

In kotlin, const and val both represents the immutability and read only values and act as final keyword in java. val keyword must be used to declare for run time values and const keyword must be used to declare compile time values


The init block is always called after the primary constructor. A class file can have one or more init blocks executing in series i.e. one after another.


Zoos android:
Technical round started with the Software Engineer providing description about the company, teams and the work they are doing (I wasn't highly impressed coz he mentioned that it will mostly be maintaining the existing apps and maybe few feature implementations) and then we dived into Android questions. a) On resume, I mentioned 3rd party libs (Okhttp, Retrofit, RoboElectric etc) so he asked about that, I said I used them previously and although I am bit rusty (coz I used them over 2 years ago) will catch up, he said its not mandatory but just cool to know about them.
b) Activity and Fragment lifecycle - Explained everything in absolute detail, then some questions on interaction between them, I struggled a bit as one question was not very clear, but eventually answered it and he was impressed.
c) Coding exercise ( find a number in a sorted rotated array), it was tricky coz it was not exactly sorted for Binary search approach. The interviewer was really nice
at this point of time as he just wanted to see my approach to problem solving rather than code, so we had a good discussion and eventually reached to a conclusion with which he looked satisfied.

* 		Design a checker game and based on that game design a chess game along with a hint feature(only class structure and data structure needed).1 Answer 
* 		Find the angle between hour hand and the minute hand on a clock.1 Answer 
* 		Find if you can insert a new time slot in a list of sorted non-overlapping time slots without any overlapping.1 Answer 
* 		Find a target integer in a random array. What's its run time? What if the array is sorted?1 Answer
* 
* 
* 
* 
* Zolando Interview Question:
* 
* 		Design shopping cart functionality in android app.Answer Question 
* 		Phone number formattingAnswer Question 
* 		Explain testing in android.
* 
* 
* 
*  


System design :
Splitwise application:


Difference between add and replace
On attach

Kotlin primary secondary init ……..quest

Buy and sell profit  programme

https://java2blog.com/stock-buy-sell-to-maximize-profit/

https://www.ideserve.co.in/learn/buy-and-sell-stocks-part-two




How This code is working in android:

getView().post(new Runnable() {

         @Override
         public void run() {
             getView().startAnimation(a);
         }
     });

 https://stackoverflow.com/questions/13840007/what-exactly-does-the-post-method-do

Dagger in android:


https://medium.com/@harivigneshjayapalan/dagger-2-for-android-beginners-dagger-2-part-i-f2de5564ab25



——When a configuration change occurs, the Android system shuts down your activity, calling onPause() , onStop() , and onDestroy() . Then the system restarts the activity from the beginning, calling onCreate() , onStart() , and onResume() .



Difference between data class and normal class

Syncronised block and Syncronisd method difference:

https://stackoverflow.com/questions/20906548/why-is-synchronized-block-better-than-synchronized-method#:~:text=The%20difference%20is%20in%20which,lock%20on%20the%20whole%20object.&text=synchronized%20blocks%20acquires%20a%20lock,until%20the%20synchronized%20block%20exits



Singelaton Class:

https://www.geeksforgeeks.org/singleton-class-java/




Latent vs lazy kotlin

https://blog.mindorks.com/learn-kotlin-lateinit-vs-lazy


Type pf observable hot and cold:


How to use CompositeDisposable to dispose 


Why we use latent and lazy in kotlin ?

https://medium.com/@waqarul/kotlin-lateinit-vs-lazy-properties-bc8ce42ea0a0


Scope function in koltin:
https://www.journaldev.com/19467/kotlin-let-run-also-apply-with



Can we use data class with multiple constructor in kotlin ?

Back pressure strategy in rx ?

Jetpack compose ?




Dagger and coroutine ?





Architecture:
ChatReciverand sender

Music player app implementation


Static method overload/ override scenario

Pattern:
Observable pattern
Factory pattern
Singleton
Builder pattern
State machine
Repositry pattern

Jet pack library


Amazon questions:

https://leetcode.com/discuss/interview-question/1183360/amazon-online-assesment-questions




How token verification work in android to handle session

App bundle and app

https://stackoverflow.com/questions/52059339/difference-between-apk-apk-and-app-bundle-aab



Api vs implementation
https://stackoverflow.com/questions/44413952/gradle-implementation-vs-api-configuration


Sterilisable and parcelable

Marker interface
A marker interface is an interface that has no methods or constants inside it. It provides run-time type information about objects, so the compiler and JVM have additional information about the object. A marker interface is also called a tagging interface

Marshalling is the process of writing Java objects to XML file. Unmarshalling is the process of converting XML content to Java objects.

https://www.3pillarglobal.com/insights/blog-posts/parcelable-vs-java-serialization-in-android-app-development/


Recycler internal working
https://blog.mindorks.com/how-does-recyclerview-work-internally


Sealed classes
https://kotlinlang.org/docs/sealed-classes.html#sealed-classes-and-when-expression

Work manger 
https://medium.com/androiddevelopers/introducing-workmanager-2083bcfc4712

https://androidwave.com/android-workmanager-tutorial/


Services
https://developer.android.com/guide/components/services


Onconfiguration change
https://developer.android.com/guide/topics/resources/runtime-changes


DAGGER @provides @Bind @inject
https://www.vogella.com/tutorials/Dagger/article.html



- Reverse a sentence. "I am a software developer" -> "developer software a am I"
- Implement Observer and Observable class (something like RxJava)

- How can fragment and activity communicate with each other (apart from viewmodel)?

- Do java thread share memory?
Yes
- How can you reduce APK size?
https://www.geeksforgeeks.org/how-to-reduce-apk-size-in-android/


Coroutine:
https://blog.mindorks.com/mastering-kotlin-coroutines-in-android-step-by-step-guide
So, we can say that Coroutines and the threads both are multitasking. But the difference is that threads are managed by the OS and coroutines by the users as it can execute a few lines of function by taking advantage of the cooperation.

Suspend function
https://blog.mindorks.com/suspend-function-in-kotlin-coroutinesi


Clean architecture with mvvm:
https://www.toptal.com/android/android-apps-mvvm-with-clean-architecture


Where to store key in android?


Fragment communication
Clean code architecture
MVVM
Add & replace
Reified in kotlin
Delegate in kotlin
By 
Lazy thread safe
Inline functions
Custom scopes in coroutines
Launch vs async 
@bind & @provides
Proxy design pattern
Chache mechanism in glide
UI performance testing tools
Bitmap view pull in glide
Contra variant
Inline
Cross inline 

Push notification open dialog if activity foreground and if activity background

Two fragment communicate without interface view model broadcast receiver()
 
 
What is scope  in courting 


876543

 




Linklist add
Profitable wala




























Q1) Directed graph-related
Q2) Stack implementation
Q3) BookMyShow design
One question related to the tweaked binary search.
One easy question related to DP.
The circular queue implementation and reverse the sublist of a linked list
=========================================================================================

Basic Algo Questions
array, stack, hash map, linked list
How do you sort linked list of integers?
given : [126,125,67,28, 658] expected: [9, 8, 13, 10, 19] without using a 2 loops
find an element in a rotated sorted array
Basic array questions and string operations
Round 1
Q1. Find min element in a sorted array rotated at a non-given point. E.g. 4 5 0 1 2 3
Q2. Given a binary tree and two nodes, find if the two nodes are cousins on not.
android 
kotlin
oops

linked list mai loop nikalna
array 4 zero and 4 1 --- 11110000 phle zero aaye phle 1 aaye
array sum of pair 1,3,5,4,2   then sum value 10 then need to find 2 elements of that sum value need to extract pair
binary search 
tik tak to

1st round DS & Java
2nd round android kotlin mvvm login page
3rd system designing APP architecture
4th managerial round 

two sum
reverse number
palindrome
Longest substring without repeating character
prefix match substring from given array of string
Binary search - follow divide and conquer rule & complexity will be log n & binary search tree

1. Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.
 
Example 1:
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]


Answer: We can search leniarly known as brute force. We will be having two loops. one will start from 0 & other will start 1 & we will check 
TargetValue = both i+j index values
And return i,j index

2nd Approach::

We will save value & index in a map . value as a key & index as a value because in the last we have to send pair of index.
So we will get 1st differece value from the loop 
e.g differece = target - array[i]
Then we will look that differece key in map & if it match then we can return value for that key & other will be i inxex 2nd value.
and i the last we will put key value in the map.

2. Three values sum from an array:

-Initially we will sort array in increasing order 
- we will start two loop as we did in brute force 
- 1st we will check i & j= i+1 & k will be the last index of array
if(i+j+k == sum ){
then return all three index
}
- else if we will check i+j+k < sum then need to increase j++ 
- else in case of i+j+k > sum then we will decrease k++ 

3 Reverse Integer: e.g 1345 Will be 5431

Simple formula :: 
while(number != 0){
1st we will find reminder:
var reminder = number%10;
var reverseNumber = reverseNumber *10 + reminder
number = number/10

}

- one challenge Integer Overflow need to check 

4. Palindrome Integer: 12321 (Will be same from every side)
 Initially we will start with the same logic & formula like reverseNumber
 while(num >0){
 int reverseNumber = reverseNumber*10 - value%10
 value = value/10 
 
 // now main logic will start from here to enhance the complexity:
 // if left value which is decreasing in every steps & we are getting reverseNumber on the other side so there will be one situation then left
 // and right value will be same e.g 12321 here 12 = 12  or some time value will be 12 & reverseNumber will be 123 then we will divide by 10 and match
 
 if(value == reverseNumber || value == reverseNumber/10){
   return true;// number will be palindrome
 }

 }
 
5. Prefix String: example "flower","flow","flight"  then output will be "fl" (longest common prefix)

-We will extract 1st index string first like flower 
-then start loop from next index 
-then we will check in next index string index(flow) of 0th index value (flower) if that will be match then it will return index but not zero
- we will check in while loop if indexOf != 0 then we will proceed
-   prefix = prefix.substring(0, prefix.length - 1) we will remove last char one by one untill it will match so fl will match 
- then same fl will match with next index and result will be same fl

6. Longest substring from a string:

- We will use look up technique for complexity 
- we will have a map<Char,Int> 
- will have three var output="" in string & start=0 & end=0 in integer
- start while loop 
- then we will see in map that value is exist or not 
- if exist then we need to change start index position  that will be max count b/w end+1 & previous start
- otherwilse we will concat substring from start & end index basis.

While(end < str.length){
var currChar = str[end]
if (map.containsKey(currChar){
start = Math.max(map[currChar]+1,start)
}
if(output.length < end - start +1){
  output = str.substring(start,end+1)
}

map[currChar] = end
end++

}

}

7.given : [126,125,67,28, 658] expected: [9, 8, 13, 10, 19] without using a 2 loops

1st way with two loops : like first for loop 
- we will get a value then with the help of formula like we used in reverse and palindrome we will calculate sum & will store in another array
-  sum = sum + value%10
- value = value/10 

But without two loops also we can calculate this:
- for loop simple 
- and in place of while loop we will use modulus 9 technique:
- if (n == 0)
        return 0;
        return (n % 9 == 0) ? 9 : (n % 9);

		
8. find an element in a rotated sorted array - complexity O(Log(n)) - binary search
- search(array[],low,high,key)
- if key is not in the array then return -1  
- if low > high then it means that key is not present because search has gone out of the array.
- find pivotal mid element  mid = (low+high)/2
- default low = 0 & high = array.length - 1
- if(array[mid] == key){
   return mid; // if mid pivotal will match with target key then we will return index as mid
   }
- if(arr[l] < arr[mid]){   //if 1st sub array is sorted if array low is less than from array mid 
- we can check whether key lies in left side or right side
- if(key >= arr[l] && key <= key[mid]){
retrun search(arr,low,mid-1,key)
// if key lies in 2nd half 
return search(arr,mid+1,h,key)
}

// if 1st sub array is not sorted right one need to sorted:
if(key >= arr[mid] && key <= arr[high]){
return search(arr,mid+1,high,key)
}
retrun search (arr,low,mid-1,key)

}    

9. How to sort Linked list?
- Initially we will create Node class with data & Node (which will point to next Node)
- Will be having head & tail Node as null in starting
- then we will start addNode
- we create val newNode = Node(3)
- first we will check that linked list is empty
if(head == null){
  head = newNode;
  tail = newNode;//because head and tail will same
}else{  // during 2nd node add 
 
 tail.next = newNode;  // 2nd element point will have newNode
 tail = newNode // so that next pointer will null 

}

- the we will sort List -----

for sort list we will having two node one is current will be head & 2nd is index which obviously point to next node
- initialize head current 

var current = head
var index:Node?
var temp:Int 

if(current == null){
return
}else {
while(current != null){
index = current.next 
while(index != null){
//swap data
if(current.data > index.data){
 temp = current.data
 index.data  = temp
 current.data = index.data
}
index = index.next
}
current = current.next

 }
}

10. Minimum number from array 

- 1st solution is we will have a temp = Int.Max value and check that if 
temp > array[i]
then temp = array[i]
complexity O(n)
2nd approach is binary search  complexity will be log n

will have a recursive method - search(arr,low,high)
low = 0
high = array.length - 1
- if array is not rotated more  if low > high return arr[0]
- if array have only one element then low == high & return array[low]
- find mid number & check if mid+1 is the min number -- if mid < high & array mid+1 < arr[mid]
- if mid is a min number - if low < mid && arr mid < arr mid-1 - return mid
- decide whether 1st half or 2nd half 
- if(arr[mid] < arry[high]) then left half otherwise right half

3rd approach:
 while(low < high)
    {
        int mid = low + (high - low) / 2;
        if (arr[mid] == arr[high])
            high--;
             
        else if(arr[mid] > arr[high])
            low = mid + 1;
        else
            high = mid;
    }
    return arr[high];
}
 
 11. isCousin
 class Node
{
    int data;
    Node left, right;
  
    Node(int item)
    {
        data = item;
        left = right = null;
    }
}
  
class BinaryTree
{
    Node root;
  
    // Recursive function to check if two Nodes are
    // siblings
    boolean isSibling(Node node, Node a, Node b)
    {
        // Base case
        if (node == null)
            return false;
  
        return ((node.left == a && node.right == b) ||
                (node.left == b && node.right == a) ||
                isSibling(node.left, a, b) ||
                isSibling(node.right, a, b));
    }
  
    // Recursive function to find level of Node 'ptr' in
    // a binary tree
    int level(Node node, Node ptr, int lev)
    {
        // base cases
        if (node == null)
            return 0;
  
        if (node == ptr)
            return lev;
  
        // Return level if Node is present in left subtree
        int l = level(node.left, ptr, lev + 1);
        if (l != 0)
            return l;
  
        // Else search in right subtree
        return level(node.right, ptr, lev + 1);
    }
  
    // Returns 1 if a and b are cousins, otherwise 0
    boolean isCousin(Node node, Node a, Node b)
    {
        // 1. The two Nodes should be on the same level
        //       in the binary tree.
        // 2. The two Nodes should not be siblings (means
        //    that they should not have the same parent
        //    Node).
        return ((level(node, a, 1) == level(node, b, 1)) &&
                (!isSibling(node, a, b)));
    }
  
    //Driver program to test above functions
    public static void main(String args[])
    {
        BinaryTree tree = new BinaryTree();
        tree.root = new Node(1);
        tree.root.left = new Node(2);
        tree.root.right = new Node(3);
        tree.root.left.left = new Node(4);
        tree.root.left.right = new Node(5);
        tree.root.left.right.right = new Node(15);
        tree.root.right.left = new Node(6);
        tree.root.right.right = new Node(7);
        tree.root.right.left.right = new Node(8);
  
        Node Node1, Node2;
        Node1 = tree.root.left.left;
        Node2 = tree.root.right.right;
        if (tree.isCousin(tree.root, Node1, Node2))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}

12. Detect loop in a linked list?

import java.util.*;
 
public class LinkedList {
 
    static Node head; // head of list
 
    /* Linked list Node*/
    static class Node {
        int data;
        Node next;
        Node(int d)
        {
            data = d;
            next = null;
        }
    }
 
    /* Inserts a new Node at front of the list. */
    static public void push(int new_data)
    {
        /* 1 & 2: Allocate the Node &
                  Put in the data*/
        Node new_node = new Node(new_data);
 
        /* 3. Make next of new Node as head */
        new_node.next = head;
 
        /* 4. Move the head to point to new Node */
        head = new_node;
    }
 
    // Returns true if there is a loop in linked
    // list else returns false.
    static boolean detectLoop(Node h)
    {
        HashSet<Node> s = new HashSet<Node>();
        while (h != null) {
            // If we have already has this node
            // in hashmap it means their is a cycle
            // (Because you we encountering the
            // node second time).
            if (s.contains(h))
                return true;
 
            // If we are seeing the node for
            // the first time, insert it in hash
            s.add(h);
 
            h = h.next;
        }
 
        return false;
    }
 
    /* Driver program to test above function */
    public static void main(String[] args)
    {
        LinkedList llist = new LinkedList();
 
        llist.push(20);
        llist.push(4);
        llist.push(15);
        llist.push(10);
 
        /*Create loop for testing */
        llist.head.next.next.next.next = llist.head;
 
        if (detectLoop(head))
            System.out.println("Loop found");
        else
            System.out.println("No Loop");
    }
}


Remove Loop Logic::::::::

  // traverse the list
        while (curr != null)
        {
            // set the previous pointer to null if the current node is seen before
            if (set.contains(curr))
            {
                prev.next = null;
                return;
            }
 
            // insert the current node into the set
            set.add(curr);

 
            // update the previous pointer to the current node and
            // move the main pointer to the next node
            prev = curr;
            curr = curr.next;
			
Middle Element:::::::::::::::

We will move fast pointer by two & slow pointer by one when fast.next.next == null then slow will be the middle element of linked list.			

15. Fibonacci::::::::::::
 int n1=0,n2=1,n3,i,count=10;    
 System.out.print(n1+" "+n2);//printing 0 and 1    
    
 for(i=2;i<count;++i)//loop starts from 2 because 0 and 1 are already printed    
 {    
  n3=n1+n2;    
  System.out.print(" "+n3);    
  n1=n2;    
  n2=n3;    
 }    
 
 16. Bubble sort - compare with pair & swap those value complexity average and worst n2

 17 . Insertion sort:- 
 
 18. missing number in an integer array n n+1 /2
nullsafty in kotlin

?. Operator - null   !!. - notNull  
?: assignment operator - x = y?:z  in case if y is null then then equation x=z other x=y

var  - variable & val - final variable 
constval - constant values k liye

difference b/w val- runtime & constval  - compiletime?

lateint- lazy initialization    var k sath use hota hai  , lateinit var x; isme x = value will be assign late like coming from API
lazy  - lazy initialization means late jabtak use nhi krenge initialize nhi hoga, val k sath use hota hai , lazy block whi par define jha par initialize hoga variable val
e.g lazy {
val 
}

how to check that lateinit is initialize or not ::variableName.IsInitialized

- delegation:-

- sealedClass is like enum  sealed class is collection of data classes, sealed class is abstract class not able to create object,

- inline function - like i have created fun a & fun b 

then i want to call fun b inside fun a  then compiletime fun a k ander b ka sara code copy ho jata hai or sara ek hi function mai manage ho jayega

- higher order function - ek function ko dusre fun mai as a perameter pass krna like coroutine generic function se response aana

- extenstion - if koi class final hai ya inherit hai or overrride nhi kar sakte but us case mai hum apna function extension bna dete hain aur usko access kar lete hain

- map and flapmap in kotlin  -- data convert from one data class to another data class
flatmap- transformation function - collection list or - synchronus call for two apis & get data
- scope function  let, with,run, also, apply   difference
- object se single - puri class object k andar 
- companion object - kisi class k andar koi function aur variable static bnana hai to companion object 
- primary init secondary 
- ek se jyada init block  & will be call in sequence 

Architechture MVP & MVVM difference -
major - relationship view know presenter & presenter know view , interface
MVVM - view know presenter but presenter know view but viewmodel don't know konsa view hai
- viewmodel (Mutable Data)can be reused  , observer ya live data, viewModel automatic update on view 
- MVVM test case - mockito mock k 

scnario kha to MVP aur kha MVVM use krna chaiye
- project chhota hai to MPV or MVVM 
- large project then MVVM because testing will be good 
- android recommend MVVM now 
- clean architectue - testable & maintable if code large to large & multiple team work then very easy to work & pull push conflict also & parallely multiple teams work
domain pure kotlin code (Business rule) in future if we need to move or migrate in different technology than easiliy can be migrated 
core module - share pref, dagger , constants, location , network helper 
easy testing 

- Project folter UI view - LoginActivity & viewmodel- LoginViewModel, data- / repository, entity
- koin / 
- Room /
- Services,AIDL
- Hashmap internal working
- inner class
- large image maintain
- LRU Cache for recent list used / Dish Cache - old deta dish cache
- Android 11 latest changes - toash background mai native & in forground can be shown custom , Storage folder permission will be required,
-  APK and Bundle creation - inside gradle put an entry means different difference apk for different screen size or screen density basis or 
- bundle only will be use for that perticular screen or version only 
- CI/CD
- work manager
- Launch mode
- jat pack 
- live deta mvvm
- android x - sari library ek sath le aaye hain 
- android profiler - memory CPU 
- retro fit 
- design patter - singleton,factory dont expose object creation, builder pattern - flexivility for fields 2 chahe ya 3 baki default set ho jate hain, observer,adapter patter (create bridge 2 unrelated chezo k beech mediator), facate related to factory, abstract factory - we use 2-level abstraction   interface layer 
- Solid - Single responsibility, O - Open for extension can add new method but cannot modification older ,
L- Liscosubstitution - b extend a & c extend a then if we need c extend b then should not effect 
i- interface segrigation - interface should be specific , not should take too much signature in a single interface , 
D- diversion of control - class k ander object create to solid principle not allow according to rule if you need  we need to send in construction dagger is example  
- Recycler View  - view holder internal 
- Data Binding 
- fragment inside fragment 

app 
common - architectue 
-
