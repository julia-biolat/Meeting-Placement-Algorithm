# Meeting-Placement-Algorithm
An algorithm that determines a meeting by arranging a large number of people appropriately, taking into account age, gender, drinking likes and dislikes, group leader, group wishes, desired activities, MBTI, etc.

I used simulated annealing as a small-scale algorithm.
Simulated annealing is a probabilistic method widely used in optimization problems. It's a way to randomly select the initial solution, change the year little by little, and find the best solution. Each step creates a new year that has made some changes from the current year, and adopts the year if it is better than the current year. Even if the new year is worse than the current year, we can adopt the year with a certain probability, but this probability gradually decreases over time.

The key idea of simulated annealing is to make it easier to accept bad harm at the beginning, but gradually harder to accept such harm over time. This allows you to explore various solutions in the navigation space, increasing your chances of finding a global optimal solution without being trapped in the local optimal solution.

Configuring Algorithms
Initial_assignment
Handle missing students (missing_students)
Evaluate_assignment
Optimization algorithm (simulated_annealing)

1. Initial assignment: initial_assignment
Initialize the batch column, check the total number of students by n = len(df), and make a calculation to form a group of 6 or 7 people. After that, we actually put the students in the group using the group_assign array.

Sets the global variable through global raw_data_global, and assigns the source data received as a factor.

2. Evaluation function: evaluate_assignment
Evaluate the effectiveness of the batch. Calculates scores using multiple criteria.
When the basic conditions are met, the final score is derived by calculating the leader preference, drinking preference, etc.
Returns 0 if not satisfied.
3. Optimization algorithm: simulated_annealing
Current_solution stores the current year and current_score stores evaluation scores for it.
Look around the loop for the solution until the temperature T falls below a certain level.

4. Handling missing students: handle_missing_students
If you find a missing student, place him in the appropriate group according to the conditions with the priorities I set
1. Like and dislike drinking
2. gender ratio consideration
3. Age preference base
4. Activity Preference Base
5. 5. MBTI

When the code is executed, the final assignment result is stored in a DataFrame called 'final_assignment'. This result is optimized through an evaluation function.
