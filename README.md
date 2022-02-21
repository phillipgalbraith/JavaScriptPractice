# JavaScriptPractice

## These functions demonstrate different problem solving methods or JavaScript methods
###### Memoization
Add each value calculated by a function to an object.  Search for the input (as a key) before running any calculations. This avoids repeated processes.

###### Windows/Frames
Comparing or calculating values from a range of neighboring indexes within an array. 
[ 0,1,2,3,4,5,6,7], 
calculate from [i,i+1,i+2]
use nested for-loops

for (i=0;i<a.length-window_size;i++){
    for (j=i;i<a.length;i++){
    }
}
