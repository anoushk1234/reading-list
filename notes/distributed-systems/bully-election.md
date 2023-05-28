# Bully Election Mechanism

Message Types
- Ok 
- Coordinator
- Election

The Coordinator is also known as the leader.

Only the process with largest ID can be the coordinator.

Let's say we have processes from 0 to 7.

7 is the coordinator but let's say 7 goes down and 4 wants to send a message to it but realises it's not getting a response.

4 sends an election msg to 5 and 6, if it doesn't get a response from anyone it means it's the largest process in the network and becomes
the coordinator.

If it gets a message from 5 and 6 then it doesn't become the coordinator instead 5 and 6 both get to know an election has started
and send messages to processes higher than them, 5 sends to 6 and 7, 6 sends to 7. Now 6 > 5 so 5 can't be the coordinator, 
6 however doesnt receive any response from 7 so it becomes the highest process and becomes the coordinator.


