# Replication

## Leader Follower
A leader is selected, node wants to make write, sends write request to leader, leader writes to local storage and keeps changelog of operations
, leader then sends change to all followers as replication log or change stream, every follower executes log on local copy in same order to avoid race condition.
When client wants to read, it can request from any node or leader.


<img width="935" alt="Screenshot 2023-02-13 at 4 00 47 PM" src="https://user-images.githubusercontent.com/32778608/218434282-d0bba55c-0810-4e57-a42f-66384b6fc87f.png">

## Async vs Sync Replication
<img width="935" alt="Screenshot 2023-02-13 at 4 20 18 PM" src="https://user-images.githubusercontent.com/32778608/218438443-44bc2583-1e8f-4b3a-a9c1-576ef042a3d1.png">

### Async
Client makes a write req to leader, leader propagates change to followers but doesnt wait for confirmation and returns ok to client

**Pros**
- If a node fails to replicate the leaders change then the leader has to block all writes until the sync node returns back, with async it doesnt wait.

**Cons**
- There's no guarantee that all followers have completely replicated the data

### Sync
Client makes write req, leader propagates change to all followers and waits for all to return ok.

**Pros**
- Guarantee of data replication across followers


**Cons**
- One sync node failure can cause leader to lock writes until node is back up

Realistically you can maintain one sync node and other async nodes
