
### Examples of Meta MMLU Prompts

Source: https://huggingface.co/datasets/meta-llama/Llama-3.2-1B-evals/viewer/Llama-3.2-1B-evals__mmlu__details?row=10

```
The population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?
A. 5 thousands
B. 5 hundreds
C. 5 tens
D. 5 ones
Answer: A

Olivia used the rule "Add 11" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?
A. The 10th number in the pattern will be an even number.
B. The number pattern will never have two even numbers next to each other.
C. The next two numbers in the pattern will be an even number then an odd number.
D. If the number pattern started with an odd number then the pattern would have only odd numbers in it.
Answer: B

A total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?
A. Add 5 to 30 to find 35 teams.
B. Divide 30 by 5 to find 6 teams.
C. Multiply 30 and 5 to find 150 teams.
D. Subtract 5 from 30 to find 25 teams.
Answer: B

A store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?
A. 749
B. 2,675
C. 2,945
D. 4,250
Answer: B

Which expression is equivalent to 5 x 9?
A. (5 x 4) x (6 x 5)
B. (5 x 5) + (5 x 4)
C. (5 x 5) + (5 x 9)
D. (5 x 9) x (6 x 9)
Answer: B

Two whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?
A. 6 and 10
B. 5 and 12
C. 10 and 12
D. 12 and 15
Answer: A
```

```
The following are multiple choice questions (with answers) about global facts.

Which of the following pairs of statements are both true (as of 2019)?
A. People tend to be optimistic about their own future and the future of their nation or the world.
B. People tend to be optimistic about their own future but pessimistic about the future of their nation or the world.
C. People tend to be pessimistic about their own future but optimistic about the future of their nation or the world.
D. People tend to be pessimistic about their own future and the future of their nation or the world.
Answer: B

As of 2019, about what percentage of Americans agree that the state is run for the benefit of all the people?
A. 31%
B. 46%
C. 61%
D. 76%
Answer: B

As of 2015, since 1990 forests have ____ in Europe and have ____ in Africa and the Americas.
A. increased, increased
B. increased, decreased
C. decreased, increased
D. decreased, decreased
Answer: B

As of 2019, about what percentage of Russians say it is very important to have free media in our country without government/state censorship?
A. 38%
B. 53%
C. 68%
D. 83%
Answer: A

As of 2017, how many of the world’s 1-year-old children today have been vaccinated against some disease? *
A. 80%
B. 60%
C. 40%
D. 20%
Answer: A

As of 2017, what percentage of Americans live in urban areas?
A. 62%
B. 72%
C. 82%
D. 92%
Answer: A
```

This is the template used:

```jinja
functools.partial(<function jinja_format at 0x7f909c2f1480>, 'The following are multiple choice questions (with answers) about {{ subject }}.

{% for x in few_shot -%}
{{ x["question"] }}
A. {{ x["choices"]["A"] }}
B. {{ x["choices"]["B"] }}
C. {{ x["choices"]["C"] }}
D. {{ x["choices"]["D"] }}
Answer: {{ x["answer"] }}

{% endfor -%}
{{ question }}
A. {{ choices["A"] }}
B. {{ choices["B"] }}
C. {{ choices["C"] }}
D. {{ choices["D"] }}
Answer: {{ choice_text }}', subject='elementary mathematics')
```

### Examples of lm-eval-harness MMLU prompts

```
The following are multiple choice questions (with answers) about abstract algebra.
Find all c in Z_3 such that Z_3[x]/(x^2 + c) is a field.
A. 0
B. 1
C. 2
D. 3
Answer: B

Statement 1 | If aH is an element of a factor group, then |aH| divides |a|. Statement 2 | If H and K are subgroups of G then HK is a subgroup of G.
A. True, True
B. False, False
C. True, False
D. False, True
Answer: B

Statement 1 | Every element of a group generates a cyclic subgroup of the group. Statement 2 | The symmetric group S_10 has 10 elements.
A. True, True
B. False, False
C. True, False
D. False, True
Answer: C

Statement 1| Every function from a finite set onto itself must be one to one. Statement 2 | Every subgroup of an abelian group is abelian.
A. True, True
B. False, False
C. True, False
D. False, True
Answer: A

Find the characteristic of the ring 2Z.
A. 0
B. 3
C. 12
D. 30
Answer: A

Find the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].
A. 2x^2 + 5
B. 6x^2 + 4x + 6
C. 0
D. x^2 + 1
Answer:
```

```
```