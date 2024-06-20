Software Development Experience 2 - CPSC/ECE 3520 
December 8, 2023

Sean Hermes
C15404781
shermes@clemson.edu
Clemson University

On my honor I have neither given nor received aid on this exam. 

Files: 
                                sde2.log
This file contains the log and testcases for testing each function in sde2.caml
I used vscode to write all of the code in the project, and I used and the 
command line application utop to run and test the project. 
I copied all of the testcases and their responses and pasted it into the log 
file by hand. 
This file essentially is a log of testcases and what is return.

                                sde2.caml
This file holds all of the ocaml code, this file contains 6 different functions.

1 - First Duplicate
Signatures:
    val fD_helper : int list * int list -> int = <fun>
    val first_duplicate : int list -> int = <fun>

This function will traverse a list recursivly, I have a helper function that I 
call, with the parameters of two int lists. The second list that is initially 
empty will act as a list of visited indexes. While traversing, if any given 
index is a member of my visited list, it will return that index. This approach
will successfully find the first duplicate, at its second occurence, not the 
element with a repeat later in the list. 


2 - First Non-Repeat
Signatures: 
    val remove : 'a * 'a list * 'a list -> 'a list = <fun>
    val nonRepeateHelper : int list * int list * int list -> int = <fun>
    val first_nonrepeating : int list -> int = <fun>

This function has two helper function, one that traverse through the list 
finding the answer, the other will remove all occurences of an element from a 
list. The helper hasthree parameters, all being lists. The first one is the input 
list, the second will initially be an empty list that will act a list of visited
elements, and the last will be an output list, that initially is the same as the 
input. While it traverses the input list, it adds elements to the visited list,
if the current element is a member of the visited list, I remove all occurences 
of that element in the output. At the end, when the whole input list is empty, 
the output list will contain every element that only occurs once, so I return 
the head of that list, which would be the first non repeating element of the i
nitial list.


3 - Sum of Two
Signatures: 
    val isTarget : int * int * int -> bool = <fun>
    val checkSum : int * int list * int -> bool = <fun>
    val sumOfTwo : int list * int list * int -> bool = <fun>

This function has two helper functions, checksum, and isTarget. isTarget has 3 
ints as parameters, and simply returns true if the first two add up to the third,
check some, takes in 2 ints, and a list. The first int is the element of the first 
list inputed to sumOfTwo, and that will check all elements of the list, which is 
the second list of sumOfTwo, and check to see if they add up to the target int 
using the isTarget function. sumOftwo recursivly iterates throught the first
list calling checkSum for each element of that list, essentially acting as a 
nested loop to check each combination of elements in the two lists.


4 - Take
Signatures: 
    val takeHelper : int * int * 'a list * 'a list -> 'a list = <fun>
    val take : int * 'a list -> 'a list = <fun>

This function has a helper function that will loop through the list and output 
the returning list. The helper function takes in the target index, a counter int,
the input list, and an empty output list that is will return. The actual take 
function only calls this function, and returns what ever it returns. 
In take helper is will recursivly iterate through the input list, while 
incrementing the counter, and appending each element to the output list. 
Until the target index equeals the counter. When this happens it will return
the output list, which will be everything in the input list up to that point.

    
5 - Drop
Signatures: 
    val dropHelper : int * int * 'a list * 'a list -> 'a list = <fun>
    val drop : int * 'a list -> 'a list = <fun>

This function acts very similary to the take function, will a small difference. 
When the counter is equal to the target it will just return the tail of the list,
which would be the rest of the input list

6 - Powerset
Signatures: 
    val psHelper2 : 'a list * 'a list * 'a list * 'a list list -> 'a list list = <fun>
    val psHelper1 : 'a list * 'a list * 'a list list -> 'a list list = <fun>
    val powerset : 'a list -> 'a list list = <fun>
    
The powerset function is pretty complicated, but I will try to break it down as
simply as I can. My thought process was to have two helper function essentially
acting as a nested loop. 
The first function will loop through the input list, while building up a second 
list to pass to the helper2. Ex. inputList otherList -> (1,2,3,4) () -> (2,3,4) (1) ->
(3,4) (1,2) -> (4) (1,2,3) -> () (1,2,3,4)
Helper2 will take both of these list and append them in different ways to ensure 
each sublists are met. It first appends both list together, and then list test
the list appended to the head of b, and so on then after b is empty it will 
repeat with the tail list of a. 
These two functions will run through every subset of the initial set, while
in each subset checking it if it is member of the powerset, if it isn't the set
will be added to the powerset, if not is iterates. 
 



