<div align="right">
    <a class="btn" href="https://ruoxiqin.github.io">Back to home</a>
</div>

# How to write bug-free code

This is my best practice of writing bug-free code.
I'm not an expert right now so these practice may not be the best.
But I will try to think and evolve the methods while practicing and try keep this blog up-to-date.

# Rule #0
Focus, focus and focus.

Even though I try to find a systematically best-practice to write bug-free code.
Focus is still the most important ability to achieve this.
You must have a clear understanding of your algorithm, and then your code.
So clear that you can play with every variable in it.
Then you can try to follow this best practice and keep the checklist below in the back of your head to avoid mistake in the training phase.

The final phase of this training: **Every check point and rule mentioned below should be a native thinking during the coding.**


## General Idea

The general idea behind writing bug-free code is not about
"be careful when writing the code,
then try to run some tests in your head to find the rest of bugs."

It should be
"have a clear understanding of what you are writing,
think about the logic in a formal way and write bug-free code from the scratch."

Having a clear understanding requries you to know your favoriate programming language.
This can be learned after you have written thousands of line of codes using it.

Thinking about the logic in a formal way is harder.
Since rigorous logical thinking requires training and accumulation.
I list down the follwing checklist based on the mistakes I have made.
Most of the mistakes are made when I wrote Python code but I believe many of them apply for other programming language.

## Best Practice

Here are the steps to write code (after you have designed the algorithm and selected the data structure):

1. Write down the steps in natural language.
The reason of using natural language is that you need to think about the logic behind them.
1. Consider the logic behind them, the pre-condition and post-condition.
For the loop, write down the loop invariant.
Then check the initialization and termination conditions.
1. Code your logic.
Follow your writting and implement sentence by sentence.
Don't fly while coding, keep on the track.
Think whether your code express exactly the same as your natural language.

Another very important thing is to give good variable names and function names.
You can have ``i``, ``j``, ``k``, as long as you make sure they are always temp looping variable and will be useless right after the loop.
Otherwise you should give them a good (long) name.

## Coding Checklist

### Know your variables' type
Keep in mind of the type of your variable.
1. When you try to modify the string by creating a new list,
notice that it is a list now, not a string.
2. You can unzip tuple but not list.

### Define the meaing of your variable
Give a specific definition of your variables.
Then you will have an assertion (or invariant).
More importantly, you should justify whenever your **variable changes or doesn't change**.

## Loop
You should have a clear understanding of your loop.
What is it for?
What are the meaning of the variables you defined in the loop?
Then there are 3 important things you need to keep in mind while designing or **editing** a loop:
1. Initialization: are all the variables being initialized as the meaning you defined at the beginning of the loop?
1. Loop range: do you loop over the full range you want to loop over?
Especially check the beginning and the end.
2. Loop invariants:
are all variables maintain their defined meanings?
Do they change when they should, and when they change do they really need to?
You can also have some sophisticated loop invariants (assumptions) you want to hold during the loop if your loop is not trivial.

### Keep the small constraints even if it may not be necessary
In the design phase,
try to keep the local small constraints true even if you think you have a better idea to prevent the bad things happen.
This is because it requires experience and great insight to know what a changes will affect the whole system.
So if you cannot do this,
keep the constraints since it costs little overhead.
It is also an extended idea from the defensive programming.

The local small constraints can be:
a list or string should not be empty.

### Index out of range/Key doesn't exist
The pre-condition of indexing is always that the key exist (Except for the defaulDict).
Make sure you think about it when coding and try you best to consider it in your natural language description.
Especially, think in 2 ways:
1. From a range view:
will the index go over every index you want?
Check the beginning and the end index.
2. From the index variable itself's view:
is the index value always valid?
For example,
if your index is in form ``index - 1``,
then ``index`` might be legal,
but what about ``index-1``?
3. When you do some process involving your neighbours.
Are you sure your neighbours are also in the list/dict?
Sepcifically, if you do the process with several neighbours,
Are all of them in the list/dict?

### Be careful with break/continue
In the natural language description you may need to interrupt the current loop under some conditions.
When you code this,
make sure how the program behave.
Should it be a ``break`` or a ``continue``?

However, you are not encouraged to use the ``break`` and ``continue``.
The reason is exactly the existence of this checkpoint -- if you use it,
it can break any conditions and assumptions you have designed before and thus you must have this checkpoint in mind and do all the checks again.

### Container manipulation in loops
When you manipulate the elements of a container while looping it,
be careful about adding or deleting elements.
Some containers like ``dict`` doesn't allow these changes during the loop.
But more importantly, make sure your manipulation doesn't break all your invariants and assumptions.


<div align="right">
    <a class="btn" href="https://ruoxiqin.github.io">Back to home</a>
</div>
