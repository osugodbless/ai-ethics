## Part A: My self-assessment

### How have I used AI for coding so far?

I have used AI for learning programming concepts quickly, and sometimes deeply when I am really curious.

### Do I ask AI for solutions before trying myself?

No I don't. Most times I try to solve the problem myself first. Then if I run into errors and I get stuck, I copy the part of the code I suspect the error is coming from and ask AI for help.

### Can I explain code I've submitted without AI's help?

Yes I can.

### What would happen if AI was unavailable during an exam or job test?

I have never relied on AI during an examination or test, so I'll be fine without it.

### My current pattern

Learner B: uses AI as a learning amplifier.

### Write a brief paragraph: Where am I now, and where do I want to be?

I currently use AI to learn deeply. However, on a few occassions when I'm in a hurry, I have used it to generate answers only. I want to become a learner who only uses it learn deeply and only use generated code I understand perfectly.

## Part B: Palindrome solution + reflection

## Step 1 - Do it myself
### Write pseudocode for a function that checks if a string is a palindrome.

- BEGIN Palindrome checker
  - SET right_index to (length of input string) - 1 
  - FOR each index postion of the input string (starting from 0):
      - IF character at the index position is the same as character at the right_index position:
          - SET right_index to decrease by 1
      - ELSE:
          - RETURN false
  - RETURN true
- END
- CALL Palindrome checker with a string as input

### Implement my solution in Python.

```python
def is_palindrome(s):
    right_index = len(s)-1

    for i in range(len(s)):
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))

```
### Test with examples like "racecar", "hello", and "A man a plan a canal Panama".

- "racecar" test returned True
- "hello" test returned False
- "A man a plan a canal Panama" test returned False

### Add comments explaining my logic.

```python
def is_palindrome(s):
	# variable holding the index number of the last character in the string
    right_index = len(s)-1

	# loop as many times as the length of the input string
    for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))
```
## Step 2 - Strategic AI use After I have a working solution, ask AI:

### What's the time complexity?
Time complexity is 0(n)

### What edge cases might I miss?
- Empty string
- Single character string
- Case sensitivity
- Spaces and punctuation
- Non-string input

### Alternatives and trade-offs?

Yeah. A better approach is by comparing just half of the string. In my previous approach, I was comparing more than I needed to.

```python
def is_palindrome(s):
    right_index = len(s)-1

    for i in range(len(s)//2):
        if s[i] == s[right_index]:	
            right_index -= 1
        else:
            return False
        
    return True

print(is_palindrome("racecar"))
```

## Step 3 - Reflection

### What did I learn by struggling first?
I learned that I'll probably be able to figure things out if I stay long enough trying to understand the problem. 

### How is my understanding different than if I'd asked for the solution?

After using AI to learn, I understood how not thinking of specific edge cases could break a program even when the solution is perfect.

### Can I now implement similar functions (reverse a string, find duplicates) without AI?
YES! I can.

### What mental model did I build?
First Principles Thinking


## Part C: Testing My Understanding

### Variations (ignore spaces & punctuation, case-sensitivity, etc.)

```python
import re

def is_palindrome(s):
	# variable holding the index number of the last character in the string
	s = re.sub(r'[^a-z0-9]', '', s.lower())
	right_index = len(s) - 1
	
	# loop as many times as the length of the input string
	for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
		if s[i] == s[right_index]:
			right_index -= 1
		else:
			return f"Stopped being a palindrome at position {i}"
	
	return True

print(is_palindrome("hellh"))
```

## Then use AI strategically:
"I modified my palindrome function to handle these cases: [show my modifications] Did I miss any edge cases? How could I make this more efficient?"

#### Answer
```python
import re

def is_palindrome(s):
	# variable holding the index number of the last character in the string
    if len(s) <= 1:
        return "Empty input"

	if not isinstance(s, str):
		return False

	s = re.sub(r'[^a-z0-9]', '', s.lower())
	right_index = len(s) - 1
	
	# loop as many times as the length of the input string
	for i in range(len(s)//2):
		# compare the first char to the last char
		# if it matches decrease the right_index number by 1
		# if any char doesn't match, return false as it is not a palindrome
		if s[i] == s[right_index]:
			right_index -= 1
		else:
			return f"Stopped being a palindrome at position {i} and {right_index}"
	
	return True

print(is_palindrome("hello"))
```


### Reflect on what AI added that I didn't consider initially.

AI added two reporting position which is better because mismatch is actually between two position. Also it handled empty string input and non-string input, which is actually guards the program from crashing unexpectedly. 

Following this, whenever I am developing any program, I'll be sure to think extensively about all possible edge cases.

## Part D: Personal Fairness Contract

### I will use AI when:

- I have tried myself to solve the problem.

- I don't understand how something works/doesn't and I need to.

- It is important that I explore alternative approaches.

### I will NOT use AI when:

- I haven't tried to solve the problem on my own.

- I am writing an exam or taking an assessment.

- I am still learning fundamental concepts.

### I know I'm using AI fairly when:

- I can explain any code I push, without AI's help.

- I could solve a similar problem without the help of AI.

- I don't get scared of solving problem and feel more confident in my own understanding.


**Signature**: *Godbless Lucky Osu*

**Date**: *10th February 2026*


## Part E: Real-World Scenario Analysis

### "Explain how I'd implement a caching system." If I always relied on AI, can I answer?

I wouldn't be able to explain the design, because AI has been doing the bulk of the work.

### Production bug at 2 AM: AI is unavailable. Can I debug code I don't fully understand?

If I didn't study and understand the code before using it, I will not be able to fix it in time.

### New tech with little documentation: If I never learned to read docs and experiment, what happens?

I may find it hard using the new tech.

### Write a paragraph: How does using AI fairly now prepare I for these scenarios?

Using AI fairly prepares me for real-world challenges because then I'll be able to solve problems independently without overrelying on AI. It also helps me build my critical thinking ability which i believe is a very important attribute to have in a professional environment.

## Part F: Skills Assessment + Action Plan

## Rate myself (1–5) in each skill and plan improvements:

| Skill | Description | Rating | Improvement Plan |
|------|-------------|--------|------------------|
| Problem Decomposition | Breaking down problems logically | 4/5 | I will practice writing problem steps in plain English before coding; outline inputs, outputs, and edge cases first. |
| Systems Thinking | Understanding how components interact | 3/5 | Draw simple diagrams showing how functions, files, and data flow connect in small projects. |
| Critical Evaluation | Knowing when code is wrong or inefficient | 3/5 | Manually trace code execution with sample inputs and compare multiple solution approaches. |
| Debugging Mindset | Investigating unexpected behavior | 4/5 | Use print statements and step-by-step reasoning before searching for external help. |
| Conceptual Understanding (the "why") | Knowing WHY, not just HOW | 2/5 | Re-explain learned concepts in my own words and teach them to someone else or write summaries. |


## 3 specific actions this week to improve my lowest area without outsourcing thinking to AI.

- Rewrite explanations

After learning a new concept, I will write a short explanation in my own words as if teaching a beginner.

- Manual examples

I will take at least one piece of code per day and manually walk through it line by line using pen and paper to understand why it behaves the way it does.

- Concept-first coding

Before writing code, I will clearly state the concept being used (e.g., “this solution uses needs two pointers because…”) to ensure I understand the reasoning behind the approach.