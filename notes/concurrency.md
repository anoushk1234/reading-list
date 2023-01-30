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
