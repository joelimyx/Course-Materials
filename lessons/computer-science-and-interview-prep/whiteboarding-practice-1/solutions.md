---
title: Whiteboard Practice
type: Morning exercise
duration: "1:00"
creator:
    name: Charlie Drews
    city: NYC
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Whiteboard Practice

## Exercise

Team up in groups of 2 or 3 and take turns working on the following problems. Pretend you are in an interview setting:
- Keep talking!
- Ask questions (to the instructors, or to your teammates)
- Consider starting with an example, showing the expected outputs for sample inputs
- Consider writing pseudocode before Java to make your steps clear to both you and the interviewer

#### Requirements

Take turns working through these problems on the whiteboard. It's OK if you don't finish them all; make as much progress as you can.

1. `centeredAverage`: Return the "centered" average of an array of ints, which we'll say is the mean average of the values, except ignoring the largest and smallest values in the array. If there are multiple copies of the smallest value, ignore just one copy, and likewise for the largest value. Use int division to produce the final average. You may assume that the array is length 3 or more.

	One possible solution:

	```java
	public int centeredAverage(int[] nums) {
		int smallest = Integer.MAX_VALUE;
		int largest = Integer.MIN_VALUE;
		int sum = 0;

		for (int num : nums) {
			if (num < smallest) {
				smallest = num;
			}
			if (num > largest) {
				largest = num;
			}
			sum += num;
		}

		sum = sum - largest - smallest;
		return sum / (nums.length - 2);
	}
	```

2. `repeatSeparator`: Given two strings, word and a separator sep, return a big string made of count occurrences of the word, separated by the separator string. For example, `repeatSeparator("Word", "X", 3)` returns "WordXWordXWord".

	One possible solution:

	```java
	public String repeatSeparator(String word, String sep, int count) {
		if (count == 0) {
			return "";
		}
	  
		StringBuilder sb = new StringBuilder();
		for (int i = 1; i < count; i++) {
			sb.append(word + sep);
		}
		sb.append(word);

		return sb.toString();
	}
	```

3. `makeBricks`: We want to make a row of bricks that is `goal` inches long. We have a number of small bricks (1 inch each) and big bricks (5 inches each). Return true if it is possible to make the goal by choosing from the given bricks. This is a little harder than it looks and can be done without any loops.

	One possible solution:

	```java
	public int makeBricks(int small, int big, int goal) {
      int bigUsed = goal / 5;
      if (bigUsed > big) {
          bigUsed = big;
      }
      
      int smallNeeded = goal - (bigUsed * 5);
      return smallNeeded <= small;
	}
	```

#### Deliverable

No deliverable - just practice working through problems out loud on a whiteboard
