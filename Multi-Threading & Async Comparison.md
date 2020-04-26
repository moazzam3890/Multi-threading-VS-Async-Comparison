# General Overview:

- Today we have processor in our PC's that has many cores that works togather to increase the performance of computations.
- Each core has many threads that runs the code and perform computations.
- When we write a program in Rust (or may be in any other language) that runs on the main thread which means that it'll execute the code line by line or more precisely command by command.
- To execute the next command code must wait for the running command to execute.
- Here comes the multi-threading concept.

# Multi-threading:

- Multi-threading is use to perform multi-tasking or to run the CPU-intensive task simultaneously. 
- CPU-intensive tasks are those task that donot involve I/O operations. For instant; opening many tabs on a browser.
- Now assume that we have opened 4 tabs on a browser and palying youtube videos on all of them. They'll run all simultaneously on each thread and each thread will also performing some other tasks as well, like fetching data from youtube.com, dispalying ads etc.
- Please see below some coding for understanding of multi-threading:

> fn talk_drive_eat() {
>    let thread1 = thread::spawn(|| talk());
>    let thread2 = thread::spawn(|| drive()); 
>    let thread3 = thread::spawn(|| eat());
>    thread1.join().expect("thread1 panicked");    
>    thread2.join().expect("thread2 panicked");
> }
> fn main() {
>    talk_drive_eat();
> }

- A person is multi-threading because he is driving, eating and talking at the same time which is good but there are some insights which needs to be understand.
- There will be a switching between these three tasks and sharing data between them. If we apply this to our coding then switching and sharing data between many threads will be very difficult and complex task to do. Because we say that multi-threading run code simultaneously but it doesn't. The switching and sharing is soo fast due to our processor speed that we can't feel it.
- Also, when the thread doing nothing and waiting for code to execute it'll utilize system resources.
- Here comes the Async programming to eliminate these issues.

# Asynchronous Programming:

