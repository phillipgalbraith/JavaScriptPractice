# JavaScript Practices

## These techniques demonstrate different problem solving methods or JavaScript methods


### Matrices

A matrix can be an array containing arrays(rows) of equal length(columns) 
[
    [1, 2, 3, 4],
    [5, 6, 7, 8],
    [9,10,11,12]
]

OR 
the same number of indexes in a single array
[ 
    1, 2, 3, 4,
    5, 6, 7, 8,
    9,10,11,12
]

#### 3D transform Matrices

x,y,and z are each an axis of the 3-Dimensional Coordinate System.  w is the perspective.

A point is [x,y,z,w]

Identity Matrix: 

idMatrix =[
    1,0,0,0,
    0,1,0,0,
    0,0,1,0
    0,0,0,1
]

##### Multiply Points by single Array Matrix

function pointTimes3DMatrix(pointInput,matrixInput) => {
    const x = pointInput[0]
    const y = pointInput[1]
    const z = pointInput[2]
    const w = pointInput[]
    // point = [x,y,z,w]


    const a0 = matrixInput[0][0]
    const a1 = matrixInput[0][1]
    const a2 = matrixInput[0][2]
    const a3 = matrixInput[0][3]
    
    const b0 = matrixInput[1][0]
    const b1 = matrixInput[1][1]
    const b2 = matrixInput[1][2]
    const b3 = matrixInput[1][3]

    
    const c0 = matrixInput[2][0]
    const c1 = matrixInput[2][1]
    const c2 = matrixInput[2][2]
    const c3 = matrixInput[2][3]
    
    const d0 = matrixInput[3][0]
    const d1 = matrixInput[3][1]
    const d2 = matrixInput[3][2]
    const d3 = matrixInput[3][3]

    <!-- multiplierMatrix = [
        a0,a1,a2,a3,
        b0,b1,b2,b3,
        c0,c1,c2,c3,
        d0,d1,d2,d3,
    ] -->

    const productPoint = [
        (a0*x + a1*x + a2*x + a3*x), // The sum of the products of x and each element of the first row
        (b0*y + b1*y + b2*y + b3*y),
        (c0*z + c1*z + c2*z + c3*z),
        (d0*w + d1*w + d2*w + d3*w)
] // [x,yNew,zNew,wNew]  
    return productPoint
}

##### Multiply two single Array Matrices



### Window Sizing looping Arrays 
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
### Data Elements

#### Caching: Use a cache to reduce process time
"Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker. Redis is an open source (BSD licensed), in-memory data structure store, used as a database, cache, and message broker. " - redis.io
 CPU -> BROWSER -> cache -> API -> cache -> SERVER 
reduce load on the server and time spent waiting for server etc.

##### Memoization
    Add each input-output pair of a function as key-value pair to an object( a cache ).  Search for the input (as a key) before running any calculations. This avoids repeated processes.

#### Classes, Objects, and Linked Lists
https://en.wikipedia.org/wiki/Linked_list#:~:text=In%20computer%20science%2C%20a%20linked,which%20together%20represent%20a%20sequence.

Changes are made in Constant Time: Nodes can be rewired without deleting and reassigning indexes to all of the succeeding elements.  (Arrays shift)
However nodes have to be searched in the sequence they are built on. (while loops etc. )
list nodes: 

function LikedListNode(arg) {
    this.valueAtNode = arg
    this.refersTo = null;
}

Given integers a===4,s===5,d===6 can you draw this diagram? 
[node value of 4] refers to> [node value of 5] refers to> 6
4>5>6

Note: 6is the value at the *tail, the last node
        4 is the value at the *head.

function listLinker (a,s,d) {
    const nodeA = new LinkedListNode(a)
    const nodeS = new LinkedListNode(s)
    const nodeD = new LinkedListNode(d)
    nodeA.refersTo = nodeS
    nodeS.refersTo = nodeD
    return nodeA // expect output [a.valueAtNode,s.valueAtNode,d.valueAtNode]     
}

##### String.prototype.charCodeAt() String.fromCharCode()
- charCodeAt() 122 is z, and if it's above 122 -= 26
- fromCharCode() can take a series of codes

## Algorithms

### Binary Search
Given a sorted list of values where differences of preceding and succeeding values are have no correlation, find a specific value.

1Guess the middle index of the range: min ... guess ... max
2Is it the value? 
3No: is goal higher or lower than guess?  
    4 Guess becomes the wall/bookend the range (min = guess + 1 or max = guess -1)
    5 repeat
