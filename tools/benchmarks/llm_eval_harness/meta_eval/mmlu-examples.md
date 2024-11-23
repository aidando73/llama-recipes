
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

```json
{
  "doc_id": 4,
  "doc": {
    "question": "Find the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].",
    "subject": "abstract_algebra",
    "choices": [
      "2x^2 + 5",
      "6x^2 + 4x + 6",
      "0",
      "x^2 + 1"
    ],
    "answer": 1
  },
  "target": 1,
  "arguments": {
    "gen_args_0": {
      "arg_0": "The following are multiple choice questions (with answers) about abstract algebra.\nFind all c in Z_3 such that Z_3[x]/(x^2 + c) is a field.\nA. 0\nB. 1\nC. 2\nD. 3\nAnswer: B\n\nStatement 1 | If aH is an element of a factor group, then |aH| divides |a|. Statement 2 | If H and K are subgroups of G then HK is a subgroup of G.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: B\n\nStatement 1 | Every element of a group generates a cyclic subgroup of the group. Statement 2 | The symmetric group S_10 has 10 elements.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: C\n\nStatement 1| Every function from a finite set onto itself must be one to one. Statement 2 | Every subgroup of an abelian group is abelian.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: A\n\nFind the characteristic of the ring 2Z.\nA. 0\nB. 3\nC. 12\nD. 30\nAnswer: A\n\nFind the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].\nA. 2x^2 + 5\nB. 6x^2 + 4x + 6\nC. 0\nD. x^2 + 1\nAnswer:",
      "arg_1": " A"
    },
    "gen_args_1": {
      "arg_0": "The following are multiple choice questions (with answers) about abstract algebra.\nFind all c in Z_3 such that Z_3[x]/(x^2 + c) is a field.\nA. 0\nB. 1\nC. 2\nD. 3\nAnswer: B\n\nStatement 1 | If aH is an element of a factor group, then |aH| divides |a|. Statement 2 | If H and K are subgroups of G then HK is a subgroup of G.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: B\n\nStatement 1 | Every element of a group generates a cyclic subgroup of the group. Statement 2 | The symmetric group S_10 has 10 elements.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: C\n\nStatement 1| Every function from a finite set onto itself must be one to one. Statement 2 | Every subgroup of an abelian group is abelian.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: A\n\nFind the characteristic of the ring 2Z.\nA. 0\nB. 3\nC. 12\nD. 30\nAnswer: A\n\nFind the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].\nA. 2x^2 + 5\nB. 6x^2 + 4x + 6\nC. 0\nD. x^2 + 1\nAnswer:",
      "arg_1": " B"
    },
    "gen_args_2": {
      "arg_0": "The following are multiple choice questions (with answers) about abstract algebra.\nFind all c in Z_3 such that Z_3[x]/(x^2 + c) is a field.\nA. 0\nB. 1\nC. 2\nD. 3\nAnswer: B\n\nStatement 1 | If aH is an element of a factor group, then |aH| divides |a|. Statement 2 | If H and K are subgroups of G then HK is a subgroup of G.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: B\n\nStatement 1 | Every element of a group generates a cyclic subgroup of the group. Statement 2 | The symmetric group S_10 has 10 elements.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: C\n\nStatement 1| Every function from a finite set onto itself must be one to one. Statement 2 | Every subgroup of an abelian group is abelian.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: A\n\nFind the characteristic of the ring 2Z.\nA. 0\nB. 3\nC. 12\nD. 30\nAnswer: A\n\nFind the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].\nA. 2x^2 + 5\nB. 6x^2 + 4x + 6\nC. 0\nD. x^2 + 1\nAnswer:",
      "arg_1": " C"
    },
    "gen_args_3": {
      "arg_0": "The following are multiple choice questions (with answers) about abstract algebra.\nFind all c in Z_3 such that Z_3[x]/(x^2 + c) is a field.\nA. 0\nB. 1\nC. 2\nD. 3\nAnswer: B\n\nStatement 1 | If aH is an element of a factor group, then |aH| divides |a|. Statement 2 | If H and K are subgroups of G then HK is a subgroup of G.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: B\n\nStatement 1 | Every element of a group generates a cyclic subgroup of the group. Statement 2 | The symmetric group S_10 has 10 elements.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: C\n\nStatement 1| Every function from a finite set onto itself must be one to one. Statement 2 | Every subgroup of an abelian group is abelian.\nA. True, True\nB. False, False\nC. True, False\nD. False, True\nAnswer: A\n\nFind the characteristic of the ring 2Z.\nA. 0\nB. 3\nC. 12\nD. 30\nAnswer: A\n\nFind the product of the given polynomials in the given polynomial ring. f(x) = 4x - 5, g(x) = 2x^2 - 4x + 2 in Z_8[x].\nA. 2x^2 + 5\nB. 6x^2 + 4x + 6\nC. 0\nD. x^2 + 1\nAnswer:",
      "arg_1": " D"
    }
  },
  "resps": [
    [
      [
        "-0.886738657951355",
        "True"
      ]
    ],
    [
      [
        "-1.136738657951355",
        "False"
      ]
    ],
    [
      [
        "-1.636738657951355",
        "False"
      ]
    ],
    [
      [
        "-2.6367387771606445",
        "False"
      ]
    ]
  ],
  "filtered_resps": [
    [
      "-0.886738657951355",
      "True"
    ],
    [
      "-1.136738657951355",
      "False"
    ],
    [
      "-1.636738657951355",
      "False"
    ],
    [
      "-2.6367387771606445",
      "False"
    ]
  ],
  "doc_hash": "6052136314d811e87b28615c67e27b8bd4c0d96c342921da4d866866b90d4fe2",
  "prompt_hash": "28739ab12b408f5458799b33138b3c2bd9c16e355cd601819cee85c1b3cdb6bc",
  "target_hash": "6b86b273ff34fce19d6b804eff5a3f5747ada4eaa22f1d49c01e52ddb7875b4b",
  "acc": 0
}
```


### Staging docs:

```json
{
  "doc_id": 0,
  "doc": {
    "input_question": "Two whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?",
    "input_correct_responses": [
      "Answer: C"
    ],
    "input_final_prompts": [
      "The following are multiple choice questions (with answers) about elementary mathematics.\n\nThe population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?\nA. 5 thousands\nB. 5 hundreds\nC. 5 tens\nD. 5 ones\nAnswer: A\n\nOlivia used the rule \"Add 11\" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?\nA. The 10th number in the pattern will be an even number.\nB. The number pattern will never have two even numbers next to each other.\nC. The next two numbers in the pattern will be an even number then an odd number.\nD. If the number pattern started with an odd number then the pattern would have only odd numbers in it.\nAnswer: B\n\nA total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?\nA. Add 5 to 30 to find 35 teams.\nB. Divide 30 by 5 to find 6 teams.\nC. Multiply 30 and 5 to find 150 teams.\nD. Subtract 5 from 30 to find 25 teams.\nAnswer: B\n\nA store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?\nA. 749\nB. 2,675\nC. 2,945\nD. 4,250\nAnswer: B\n\nWhich expression is equivalent to 5 x 9?\nA. (5 x 4) x (6 x 5)\nB. (5 x 5) + (5 x 4)\nC. (5 x 5) + (5 x 9)\nD. (5 x 9) x (6 x 9)\nAnswer: B\n\nTwo whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?\nA. 6 and 10\nB. 5 and 12\nC. 10 and 12\nD. 12 and 15\nAnswer: A",
      "The following are multiple choice questions (with answers) about elementary mathematics.\n\nThe population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?\nA. 5 thousands\nB. 5 hundreds\nC. 5 tens\nD. 5 ones\nAnswer: A\n\nOlivia used the rule \"Add 11\" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?\nA. The 10th number in the pattern will be an even number.\nB. The number pattern will never have two even numbers next to each other.\nC. The next two numbers in the pattern will be an even number then an odd number.\nD. If the number pattern started with an odd number then the pattern would have only odd numbers in it.\nAnswer: B\n\nA total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?\nA. Add 5 to 30 to find 35 teams.\nB. Divide 30 by 5 to find 6 teams.\nC. Multiply 30 and 5 to find 150 teams.\nD. Subtract 5 from 30 to find 25 teams.\nAnswer: B\n\nA store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?\nA. 749\nB. 2,675\nC. 2,945\nD. 4,250\nAnswer: B\n\nWhich expression is equivalent to 5 x 9?\nA. (5 x 4) x (6 x 5)\nB. (5 x 5) + (5 x 4)\nC. (5 x 5) + (5 x 9)\nD. (5 x 9) x (6 x 9)\nAnswer: B\n\nTwo whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?\nA. 6 and 10\nB. 5 and 12\nC. 10 and 12\nD. 12 and 15\nAnswer: B",
      "The following are multiple choice questions (with answers) about elementary mathematics.\n\nThe population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?\nA. 5 thousands\nB. 5 hundreds\nC. 5 tens\nD. 5 ones\nAnswer: A\n\nOlivia used the rule \"Add 11\" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?\nA. The 10th number in the pattern will be an even number.\nB. The number pattern will never have two even numbers next to each other.\nC. The next two numbers in the pattern will be an even number then an odd number.\nD. If the number pattern started with an odd number then the pattern would have only odd numbers in it.\nAnswer: B\n\nA total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?\nA. Add 5 to 30 to find 35 teams.\nB. Divide 30 by 5 to find 6 teams.\nC. Multiply 30 and 5 to find 150 teams.\nD. Subtract 5 from 30 to find 25 teams.\nAnswer: B\n\nA store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?\nA. 749\nB. 2,675\nC. 2,945\nD. 4,250\nAnswer: B\n\nWhich expression is equivalent to 5 x 9?\nA. (5 x 4) x (6 x 5)\nB. (5 x 5) + (5 x 4)\nC. (5 x 5) + (5 x 9)\nD. (5 x 9) x (6 x 9)\nAnswer: B\n\nTwo whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?\nA. 6 and 10\nB. 5 and 12\nC. 10 and 12\nD. 12 and 15\nAnswer: C",
      "The following are multiple choice questions (with answers) about elementary mathematics.\n\nThe population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?\nA. 5 thousands\nB. 5 hundreds\nC. 5 tens\nD. 5 ones\nAnswer: A\n\nOlivia used the rule \"Add 11\" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?\nA. The 10th number in the pattern will be an even number.\nB. The number pattern will never have two even numbers next to each other.\nC. The next two numbers in the pattern will be an even number then an odd number.\nD. If the number pattern started with an odd number then the pattern would have only odd numbers in it.\nAnswer: B\n\nA total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?\nA. Add 5 to 30 to find 35 teams.\nB. Divide 30 by 5 to find 6 teams.\nC. Multiply 30 and 5 to find 150 teams.\nD. Subtract 5 from 30 to find 25 teams.\nAnswer: B\n\nA store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?\nA. 749\nB. 2,675\nC. 2,945\nD. 4,250\nAnswer: B\n\nWhich expression is equivalent to 5 x 9?\nA. (5 x 4) x (6 x 5)\nB. (5 x 5) + (5 x 4)\nC. (5 x 5) + (5 x 9)\nD. (5 x 9) x (6 x 9)\nAnswer: B\n\nTwo whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?\nA. 6 and 10\nB. 5 and 12\nC. 10 and 12\nD. 12 and 15\nAnswer: D"
    ],
    "previously_is_correct": false,
    "input_question_hash": "2f9f3789c31bccfee18249d4e2b191cf856e5b1ef05272817f7703c85f7bca7f",
    "input_choice_list": {
      "A": "6 and 10",
      "B": "5 and 12",
      "C": "10 and 12",
      "D": "12 and 15"
    },
    "output_prediction_text": null,
    "problem": "Two whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?",
    "gold": "Answer: C"
  },
  "target": "Answer: C",
  "arguments": {
    "gen_args_0": {
      "arg_0": "The following are multiple choice questions (with answers) about elementary mathematics.\n\nThe population of the city where Michelle was born is 145,826. What is the value of the 5 in the number 145,826?\nA. 5 thousands\nB. 5 hundreds\nC. 5 tens\nD. 5 ones\nAnswer: A\n\nOlivia used the rule \"Add 11\" to create the number pattern shown below. 10, 21, 32, 43, 54 Which statement about the number pattern is true?\nA. The 10th number in the pattern will be an even number.\nB. The number pattern will never have two even numbers next to each other.\nC. The next two numbers in the pattern will be an even number then an odd number.\nD. If the number pattern started with an odd number then the pattern would have only odd numbers in it.\nAnswer: B\n\nA total of 30 players will play basketball at a park. There will be exactly 5 players on each team. Which statement correctly explains how to find the number of teams needed?\nA. Add 5 to 30 to find 35 teams.\nB. Divide 30 by 5 to find 6 teams.\nC. Multiply 30 and 5 to find 150 teams.\nD. Subtract 5 from 30 to find 25 teams.\nAnswer: B\n\nA store sells 107 different colors of paint. They have 25 cans of each color in storage. The number of cans of paint the store has in storage can be found using the expression below. 107 × 25. How many cans of paint does the store have in storage?\nA. 749\nB. 2,675\nC. 2,945\nD. 4,250\nAnswer: B\n\nWhich expression is equivalent to 5 x 9?\nA. (5 x 4) x (6 x 5)\nB. (5 x 5) + (5 x 4)\nC. (5 x 5) + (5 x 9)\nD. (5 x 9) x (6 x 9)\nAnswer: B\n\nTwo whole numbers have a least common multiple of 60. Each number is less than or equal to 12. The greatest common factor of the two numbersis 2. What are the two numbers?\nA. 6 and 10\nB. 5 and 12\nC. 10 and 12\nD. 12 and 15\nAnswer: A",
      "arg_1": {
        "until": [
          "\n\n"
        ],
        "do_sample": false
      }
    }
  },
  "resps": [
    [
      ""
    ]
  ],
  "filtered_resps": [
    ""
  ],
  "doc_hash": "d2b21971187e5652227e6aa3a86fa3cf214666ec18d41120ea08af61faec07f0",
  "prompt_hash": "bb52e753d4b0c56238b45c86754ac44331c6c538b2e337151c5073c498907a2f",
  "target_hash": "c3233452262de1ea96377c1a198f764e3a9b6e00e06b84e0eb926d27def12b57",
  "exact_match": 0
}
```