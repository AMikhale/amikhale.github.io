# 15-418 Project: Sudoku Solver Parallelization 
<a href="https://amikhale.github.io/proposal"> Proposal </a> <br>
<a href="https://amikhale.github.io/milestone"> Milestone Report </a>


<h2> Schedule </h2>
Key: <b>bold = completed</b>, <i>italics = in progress</i>
<br><br>
<table>
  <tr>
    <th>Dates</th>
    <th>Goals</th>
  </tr>
  <tr>
    <td>02/27 - 04/02</td>
    <td><b>•	Discuss project concept with Professor Jia<br>
      •	Submit proposal<br></b>
</td>
  </tr>
  <tr>
    <td>04/03 - 04/09
</td>
    <td><b>•	Research existing sequential algorithms<br>
      •	Begin working on the implementation<br></b>
</td>
  </tr>
    <tr>
    <td>04/10 - 04/16

</td>
    <td><b>•	Finish correct sequential implementation<br>
•	Devise a way to approach parallelization with OpenMP<br></b>

</td>
  </tr>
    <tr>
    <td>04/17 - 04/20

</td>
    <td>
<b>•	Submit project milestone report<br></b>
<i>•	Finish correct parallel implementation: locking stack to avoid segfaults, correctly placing barriers to ensure a thread does not exit prematurely (Alex)<br>
•	Finish the development of a test suite consisting of 16 x 16 sudoku boards of various difficulties to meaningfully measure the performance of the parallelization (Thomas)</i><br>
•	As a part of the above, repurpose the timing code from previous assignments to be able to accurately time the algorithm’s performance (Thomas)  <br>


</td>
  </tr>
    <tr>
    <td>04/21 - 04/23

</td>
    <td>•	Continue implementing various heuristics (for eliminating the options for each cell instead of defaulting to backtracking) to improve the general speedup of the algorithm, both parallel and sequential (Alex)</br>
•	Investigate the possibility for incorporating CUDA, either within one board, for checking multiple elements at once, or for solving multiple boards at once (Thomas)</br>

</td>
  </tr>
    <tr>
    <td>04/24 - 04/27

</td>
    <td>•	Assuming we decide to use CUDA, actually incorporate it into our implementation in the appropriate way (Thomas) </br>
•	Analyze bottlenecks that do not depend on heuristics (e.g., memory accesses and locality) and attempt to improve performance by optimizing them (Alex)</br>


</td>
  </tr>
    </tr>
    <tr>
    <td>04/28 - 04/30

</td>
    <td>•	Perform analyses using the previously developed test suite: speedup over sequential/one-thread implementation, speedup vs. the number of OpenMP threads, the effect of CUDA, etc. (Both)</br>

</td>
  </tr>
    </tr>
    <tr>
    <td>05/01 - 05/01

</td>
    <td>•	Final pass over the code, fixing any issues (e.g. style) or last-minute bugs (Either) </br>
•	Work on and submit the final report (Both, division of labor to be determined closer to the time)</br>
•	Work on and present the posters at the poster session (ditto)</br>


</td>
  </tr>
</table> 
