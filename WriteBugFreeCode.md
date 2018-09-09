# How to write bug-free code

This is my best practice of writing bug-free code.
I'm not an expert right now so these practice may not be the best.
But I will try to think and evolve the methods while practicing and try keep this blog up-to-date.

## General Idea

The general idea behind writing bug-free code is not about
"be careful when writing the code,
then try to run some tests in your head to find the rest of bugs."

It should be
"Have a clear understanding of what you are writing,
think about the logic in a formal way and write bug-free code from the scratch."

Having a clear understanding requries you to know your favoriate programming language.
This can be learned after you have written thousands of line of codes using it.

Thinking about the logic in a formal way is harder.
Since rigorous logical thinking requires training and accumulation.
I list down the follwing checklist based on the mistakes I have made.
Most of the mistakes are made when I wrote Python code but I believe many of them apply for other programming language.

## Coding Checklist

### Know your variable type
Keep in mind of the type of your variable.
When you try to modify the string by creating a new list, notice that it is a list now, not a string.
