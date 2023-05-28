# Concurrency in Rust

### 3 ways to go about it
- Fork Join Parallelism
- Shared Mutable State
- Channels

### Fork Join Parallelism
You can split up the task into chunks and run each chunk on a seperate thread. To fork means to start a new thread and to join is to wait for it to finish.

- easy to implement
- no shared state so no locks etc
- can speed up any cpu bound task even after thread results have to be aggregated once all threads have executed
- produces deterministic results and prevents race conditions provided each thread is completely independent with state

it's important to join threads because if the main thread exits before the other threads finish executing then they just get killed so the join handle here waits for them to execute

One of the advantages of rust threads is that it isolates panic per thread, each thread gives an std::thread::Result which has an Error if the thread panics making multithreading way more robust than C++

Join handle also returns the value of the thread to the main thread

If threads depend on reading the same data you can use Arc<DataType> and use clone on it to give an arc ref to every thread. This works because data in Arc is immutable so the data is actually moved to the heap and your ref is pointing to Arc which keeps a count of all the references so even if main thread exits we arent dependent on it because of Arc but also we dont have to clone the data per thread which would be a memory hog

Rayon is better designed to handle fork joins
```rust
  use rayon::prelude::*;
  
  // "do 2 things in parallel"
  let (v1, v2) = rayon::join(fn1, fn2);
  
  // "do N things in parallel"
  giant_vector.par_iter().for_each(|value| {
    do_thing_with_value(value);
  });
```
  
Rayon has a worker pool of threads, in theory we think rayon allocates one thread per task we give it but to be more efficient rayon spawns one worker thread per cpu core and splits the tasks across the pool of worker threads

rayon also supports sharing refs across threads which wont require Arc
