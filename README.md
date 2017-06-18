## Chaos Week Scheduling

### Introduction

This project was part of the University of Washington's Math 480 Special Topics class with Professor Sarah Billey. The project involved working with community partners to solve problems with mathematical modeling. We worked with Dr. Jonah Ostroff at the University of Washington to help automate scheduling for his Summer mathematics program.

Below are snippets pulled from our report. Please read the document to see the formulas we used to design the LP.

We created the scheduler in Sage. You can test out the scheduler with the sage worksheet. This is found in the general_form_scheduler.sws.


### Abstract
MathILy-Er is an academic mathematics summer program in Oregon. Every summer in between regularly scheduled classes is an impromptu week-long set of classes decided by student interests. MathILy-Er needs a way to quickly create an assignment of students and teachers to classes, and classes to time slots, so that are no scheduling conflicts. The organizer of this event, and our community partner, is Dr. Jonah Ostroff at the University of Washington.

### Approach
The end result must contain all integer values, for example, we cannot assign a student to half of a class. Thus the problem is an integer programming (IP) problem, and we'll use an LP solution as a basis for our IP problem. To approach this problem we chose to implement the GNU Linear Programming Kit (GLPK) to solve the IP, as it is free to use with no license requirements or other restrictions.

Because there is no data yet for student preferences of 2016, we used randomized data fitting within the constraints and estimations of Dr. Ostroff. This is done to show the feasibility of using this approach for data sets larger than the 2015 data. While our approach is built on the requirements of MathILy-Er's Week of Chaos, our algorithm has been generalized to accept a variable amount for the scheduling requirements. This allows this method of scheduling to extend beyond just MathILy-Er's Week of Chaos.

### Sample Results

#### Teacher Assignment
For a total of five teachers, each had an eligibility score to teach the classes. It was assumed that there was an even distribution of classes each teacher could instruct. Note that when a cell is colored green it corresponds to that teacher being scheduled to teach that class. It's important to note, that not only was no teacher assigned to aclass he or she could not teach, but the most eligible teacher was assigned in all cases. This satisfies the constraint of each class being instructed by an eligible teacher.

![Table 1](/images/table1.png)


#### Student Assignment

![Table 2](/images/table2.png)

![Table 3](/images/table3.png)

This table shows class assignment among the preference ratings for the given classes. Note that this is in accordance to the overrides shown above. The classes students were assigned are predominantly their highest rated classes.


#### Time Slots
Organizing the data by classes, with their respective teachers and students is the end result that Dr. Ostroff and the MathILy-Er staff would need for "the Week of Chaos." Note that in each time slot, a student is only assigned to one class, and likewise with teachers. This satisfies the constraint of scheduling.

![Table 4](/images/table4.png)

#### Student Satisfaction

To verify that students were assigned classes that they rated the highest, the average rating of their preferences was compared to the preference of their assigned classes. The difference from their average rating and actual assignment shows that no student was unfairly penalized in the assignment. Student A has the lowest preference of assigned classes due to abundant overrides given.

Another test was computed to compare the assignment. Using the same set of data, the IP was solved with a modified objective function. Instead, only teacher eligibility was maximized. The total of net satisfaction in this case was -1.466 compared to the original 23.332.

![Table 5](/images/table5.png)


### To Do:

* Peer Review Changes
 * Explain why three simultaneous classes were chosen (in detail)
 * Explain the example of 3.6 (Davis)
 * Explain edge case of teacher assignment
 * Explain 3-matching
 * Explain the variables used in end of 3.1 (page 3)
 * Reorganize / reimplement simplifications section
 * Clean up references section, put in Acknowledgements
* Explain why certain solving methods for GLPK work better than others.
 * Branching Pseudo-Cost Heuristic
 * Backtracking by best prediction heuristic
 * Cuts by mixed integer rounding
 * Are these parameters better in general for IP? For large scale problems? Or something more specific?
* Implement changes from notes from Billey, disregarding erroneous comma placement
* Are we consistent with all terms?
 * Run the algorithm over multiple schedules to find an average solving speed
 * Identify what are potential problems in schedules that cause for longer solving times
 * About how long should we run it to get a better solution once a BFS is found?
 * Write a function to generate random data that would represent teacher preferences and student preferences
 * Create a table showing computation times and preference total achieved

### Notes:
 * Even with inefficient solver parameters, I am getting the better solution which diverges from Jonah's schedule.

