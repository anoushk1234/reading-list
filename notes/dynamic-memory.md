# Dynamic Memory

## Static Memory Allocation
Memory allocated at compile time.
```
int arr[5] = [1,2,3,4,5];
```
This is useful sometimes but also causes lack of flexibility and wastage of memory other times.

## Dynamic Memory Allocation
Allocating memory at runtime.<img width="314" alt="Screenshot 2023-05-28 at 3 56 39 PM" src="https://github.com/anoushk1234/reading-list/assets/32778608/97d17851-c711-4451-b6b1-ba4497bee674">

Stack is the part of the memory which is allocated/dealloc in a definite order whearas heap is done randomly.

Heap is used for dynamic mem alloc.

Dynamically allocated memory can only be accessed through pointers.

### Functions
- malloc()
- calloc()
- realloc()
- free()

