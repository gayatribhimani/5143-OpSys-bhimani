Name: Gayatri Bhimani
Date: 04/06/2016
M#: M20222781

1. Explain the differences between Threads1 and Threads2 using lines from the code and a precise explanation.

Answer: In the thread1.py both the threads A and B are accessing a shared resource and all the instructions are atomic.Threads1 does not 
use a sharedCounter, which means that, the 2 threads are created and executed independently. it works like parallelprogramming when 2 
different threads get their own space to work with the processor. Where as in Threads2 the concept of sharedCounter
is implemented to asyncronusly run both the threads. This will link the threads, but causes race conditions which requires the 
implementation of locks to avoid it. 
                                      sharedCounter += 1.


2. After running Thread3.py does it fix the problems that occured in Threads2.py? What's the down-side?

Answer: In thread3.py, the threads A and B uses lock() method while peformong the computation. this will locks the shared resource between 
the two threads.  Yes, it does fix the problems that occured in Threads2.py. By using lock.acquire() and lock.release() 
methods.in thread2.py, the resource -shared memory is accessed by both the threads Aand B at the same time and the modification done to 
it is parallel which causes redundancy problem.In Thread2.py, the atomicity of the shared data is compromised whereas in thread3.py 
the same property is satisfied using LOCKS.

3. Comment out the join statements at the bottom of the program and describe what happens.

Answer: the main purpose of Join() operation is to makes sure that child threads need to finish bfore parent thread terminates.
In our program if  we remove join() in main method finish first then threadA and threadB terminates.

4.What happens if you try to Ctrl-C out of the program before it terminates?
Answer: When we try to Pressing Ctrl + c while a program is running will cause to raise a KeyboardInterupt.all the other threads are 
interepted untill child threads finish their work.

5. Read and run Threads4.py. This generates a different and more ridiculous race condition. Write concise 
explanation of what's happening to cause this bizarre behavior using lines from the code and precise explanation.

Answer: 

              sharedNumber = 1                          
              if sharedNumber != 1:                     
               print 'A: that was weird' 

When threadA access sharedNumber it will assign it as 1 and prints some statement and when threadB access the same variable it will 
reassign it as 2 and print some statements.it is dependes on execution and accesing of shared variable.

6. Does uncommenting the lock operations clear up the problem in question 5?

Answer: Yes, it does clear up the problem by locking the resources when other thread is using it. so thereis no other processor can no manipulat the 
data. in our program 1 in threadA and 2 in threadB without interacting with eachother they are doing nothing. so thread A and thread B 
terminates with out printing any statements.

