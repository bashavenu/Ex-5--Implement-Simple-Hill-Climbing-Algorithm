<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: BASHA VENU             </h3>
<h3>Register Number: 2305001005             </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

## PROGRAM
```python
import random
import string

answer = "Artificial Intelligence"
gen = lambda: [random.choice(string.printable) for _ in range(len(answer))]
score = lambda s: sum(abs(ord(a)-ord(b)) for a, b in zip(s, answer))

best = gen()
iteration = 0

while True:
    current_score = score(best)
    solution_str = "".join(best)
    print(f"Iteration: {iteration} | Score: {current_score} | Current Best: {solution_str}")
    if current_score == 0:
        print("\nTarget reached!")
        break
    new = best[:]
    new[random.randrange(len(answer))] = random.choice(string.printable)
    if score(new) < current_score:
        best = new
    iteration += 1

```

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
<img width="630" height="423" alt="image" src="https://github.com/user-attachments/assets/e6051101-5b40-472c-8e82-9539cdec86da" />
<img width="647" height="486" alt="image" src="https://github.com/user-attachments/assets/bdf29177-30d7-4030-a07c-8c3878ca00e4" />

## RESULT:
Thus the program to Implement Simple Hill Climbing Algorithm has been executed successfully.


