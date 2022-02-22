# JavaScriptPractice

## These functions demonstrate different problem solving methods or JavaScript methods
##### Memoization
Add each value calculated by a function to an object.  Search for the input (as a key) before running any calculations. This avoids repeated processes.

##### Window Sizing to talk about 
Comparing or calculating values from a range of neighboring indexes within an array. 
[ 0,1,2,3,4,5,6,7], 
find greatest from [i,i+1,i+2]
use nested for-loops

<!-- 
for (i=0;i<a.length-window_size;i++){
    for (j=i;i<a.length;i++){
    }
} 
-->

##### Caching: Use a cache to reduce process time
"Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker. Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker. " - redis.io
 CPU -> BROWSER -> cache -> API -> cache -> SERVER 
reduce load on the server and time spent waiting for server etc.

##### Classes, Objects, and Linked Lists
https://en.wikipedia.org/wiki/Linked_list#:~:text=In%20computer%20science%2C%20a%20linked,which%20together%20represent%20a%20sequence.

Nodes can be rewired without deleting and reassigning indexes to all of the succeeding elements.  (Arrays shift)
However nodes have to be searched in the sequence they are built on. (while loops etc. )
list nodes: 


function likedListNode(arg) {
    this.valueAtNode = arg
    this.refersTo = null;
}

Given integers a===4,s===5,d===6 can you draw this diagram? 
[node value of 4] refers to> [node value of 5] refers to> 6
4>5>6


Note: 6is the value at the *tail, the last node
        4 is the value at the *head.



function listLinker (a,s,d) {
    const nodeA = new linkedListNode(a)
    const nodeS = new linkedListNode(s)
    const nodeD = new linkedListNode(d)
    nodeA.refersTo = nodeS
    nodeS.refersTo = nodeD
    return nodeA // expect output [a,s,d]     
}