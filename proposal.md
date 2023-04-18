<h1>Project Proposal</h1>
<b>Title:</b> Sudoku Solver Parallelization

<b>Summary:</b> Our group intends to implement a parallelized Sudoku Puzzle solver by leveraging OpenMP and collect performance statistics for comparison with our sequential (single-thread) baseline. We will also investigate the potential for the use of parallelization using the CUDA platform, for example as it pertains to concurrently solving multiple boards.

<b>Background:</b>
The standard game of Sudoku consists of a N2 x N2 grid of cells (traditionally 9 x 9), organized into N2 N x N groups (grid squares). Each of the cells can contain a number between 1-N2, and the board starts partially filled in. The objective of the puzzle is to fill in all the remaining cells, with each cell’s number being unique to its row, column, and N x N subgroup. Many different algorithms and implementation approaches for systematically solving arbitrary (solvable) grids have been well documented. 
As each cell has N2 different possibilities, and the area of the board scales in N2, the different permutations in the problem space grows astronomically with board size. Consequently, this problem naturally demands parallelism. To achieve a greater resolution on the effects and behavior of this parallelism, we intend to test our approaches on a 16 x 16 board rather than a more standard 9 x 9, as well as potentially collect the performance data on bigger sizes. Our group intends to investigate a few algorithmic approaches to the solver, focusing on their different opportunities for parallelism.
Sudoku is an NP-complete problem, which automatically places some bounds on the theoretical performance we can achieve. However, we still hope to get good performance by taking advantage of the speedup achieved by parallelism, as well as figuring out clever approaches to generating potential solutions beyond just brute force. Sudoku is a famous puzzle with a wealth of information about good strategies and methods of eliminating potential guesses for numbers, so we hope to utilize this existing knowledge base in our approach.
  
<b>The Challenge:</b> 
The first challenge is to assess the existing sequential Sudoku solver algorithms and determine which has the greatest potential to benefit from parallelism. This would involve investigating the algorithms for sections that can run concurrently using the OpenMP framework, or even make use of CUDA. Ultimately, we intend to settle on one algorithm to parallelize for our final solution, but if we find that there may be some merit in comparing the performance of a couple, we may take that route instead. In any case, we believe that this will be a good use of the skills we gained throughout this class, since to implement a good parallel solution, we first need to recognize what exactly makes any given algorithm suitable for parallelization. 
The main challenge of this problem, however, is actually applying parallelism to manage the staggering size of the problem space. Each cell affects all others in its row, column, and subgroup, the number of cells scales exponentially with the size of the Sudoku grid, and filling in any cell branches the current solution into a completely unique and still large subset of future permutations. The N x N subgroup or row and column interdependence introduces an inherent avenue for data locality, but since any cell can potentially affect another across the board through a chain of indirect influences, there are thread communication overhead dangers to be avoided. We will need to determine how to efficiently and correctly communicate the necessary data between workers, and which data is necessary in the first place. 
We’ll also have to figure out how to assign data to the workers given the algorithm we will select, which may be challenging given the magnitude of the problem. We hope to look into distributed worker queues and job stealing to improve the performance closer to the end of the project season, as per Professor Jia’s advice. Overall, we believe this project is a good application of the concepts we have learned this semester, and we look forward to the challenge. 

<b>Resources: </b>
For the background research on the project, we will use public domain information about Sudoku solvers. For example, we plan to look into research papers on various sequential Sudoku algorithms (for example backtracking or reducing to other NP-complete problems, such as graph coloring), as well as potentially even blog posts or tutorials explaining strategies used by human players. 
At this point, we intend to start the codebase from scratch, although this may be subject to change if we settle on a specific well-documented sequential algorithm to start on, in which case we may investigate existing open-source implementations. We will be working primarily on the Gates Hall Cluster machines, though as a stretch goal, we may try evaluating our code on the PSC machines as well. 

  <b>Goals and Deliverables:</b>
 <i>Goals (Plan to Achieve):</i>
- Sequential Version of the Sudoku Solver that is correct and reasonable.  
- Parallel Version of the Sudoku Solver using OpenMP for a 4x speedup over the reference sequential solution on a 16 x 16 grid.  
- Test Suite for benchmarking compatible with both implementations.
- A final report about the performance of our algorithm and how much we have been able to improve it via parallelization. 

 <i>Hope to Achieve:</i>
- Parallel Version of the 16 x 16 Sudoku Solver with a 8x speedup. 
- Solve 4, 8 Sudoku boards concurrently using CUDA on NVIDIA GPUs. 
- Using PSC Bridges-2 Regular Memory machines for our evaluation.  

<b>Platform Choice: </b>
We will be primarily running our code on the Gates Hall Cluster machines to use OpenMP and CUDA on their NVIDIA GPUs. This is the most convenient way to debug and try out various implementation approaches while giving us all the resources we need. 
