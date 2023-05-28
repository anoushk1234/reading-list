## Poison Memory
An address sanitizer essentially "poisons" memory around what you allocate,
Then on every memory access it checks if you have touched any of the poisoned memory. 
If you have it will give you a report of what memory you touched that wasn't yours.

It checks for any bad memory access.
