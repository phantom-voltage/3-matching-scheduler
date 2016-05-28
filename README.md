## math_480_project
###Chaos Week Scheduling

###To Do:

* Peer Review Changes
 * Explain why three simultaneous classes were chosen (in detail)
 * Explain the example of 3.6 (Davis)
 * Explain edge case of teacher assignment
 * Dr. Ostroff introduction
 * Explain 3-matching
 * Explain the variables used in end of 3.1 (page 3)
 * Reorganize / reimplement simplifications section
 * Clean up references section, put in Acknowledgements
  * Mention in beginning of paper how our problem is different, more complex, and faster than 2015
 * Other notes from Peer Review (Ethan's in particular)
* Explain why certain solving methods for GLPK work better than others.
 * Branching Pseudo-Cost Heuristic
 * Backtracking by best prediction heuristic
 * Cuts by mixed integer rounding
 * Are these parameters better in general for IP? For large scale problems? Or something more specific?
* Implement changes from notes from Billey, disregarding erroneous comma placement
* Are we consistent with all terms?
 * Chaos Week vs. Week of Chaos vs. "Chaos Week" vs. "Week of Chaos"
 * IP vs. LP
 * MathILy vs. MathILy-Er
* Testing
 * Run the algorithm over multiple schedules to find an average solving speed
 * Identify what are potential problems in schedules that cause for longer solving times
 * About how long should we run it to get a better solution once a BFS is found?
 * Write a function to generate random data that would represent teacher preferences and student preferences
 * Create a table showing computation times and preference total achieved
 * Get a monopoly on Pokemon cards

###Notes:
* I switched over the first draft file to second draft file, it's a WIP with some of the formulas filled in
* I took the liberty of changing MathILy-Er to MathILy. I don't think we need to be that specific and I think it's more confusing in its full form.
* I am unable to recreate the sub-optimal solution for 2015 that closely resembles Jonah's schedule.
 * Even with inefficient solver parameters, I am getting the better solution which diverges from Jonah's schedule.
 * Do we need to reword the section that references this? Or will we add this later?
* If you change indentation or line spacing within github's editor
 * Use "\indent" for indentation
 * Use "\\\" at the end of a paragraph for a new line

