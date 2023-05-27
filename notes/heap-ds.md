# Heap Data Structure
A nearly complete binary tree.

All levels are filled except lowest. 

Lowest level is filled upto certain point starting from left.

## Uses
- heap sort
- priority sort

## Types
- Max Heap - node i value <= parent node value - used for heap sort
- Min Heap - node i value >= parent node value - used for priority queue

height - O(logn)

<img width="500" alt="heap-structure-as-array" src="https://github.com/anoushk1234/reading-list/assets/32778608/b953eba1-a14f-4c14-81dd-ec1e5a6e3dfe">

if A is the array then root = A[1] (starts from 1 because makes operations simler due to the math)

child left(i) = index * 2 

child right(i) = index * 2 + 1 

parent of i = floor(i/2) 
