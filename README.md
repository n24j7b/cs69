java c
Project   1:   Martingale (Report) 
Instructions for Project 1: Martingale 
Revision History
This assignment   is subject to change up   until 3 weeks   before   the   due   date.   We   do   not   anticipate   changes; any changes will be   logged   in this   section.
1.   Published - Start   of Term
2.   [082524] -   Added recommendation to set a   starting   seed.
3.   [082624] -   Added clarification that   .txt and   .html files are   optional
4.   [082724] -   Revised "all work should be your own" to   "all   work   must   be   your   own"   to   align   that   statement with course and   Institute policy.
1. Overview
In this course, you are building a simplified AI-based trading   system. This   system   is   constructed   over the   course of 8   projects, where each   project you complete is a   step   towards   building   an   intricate   system   that   synthesizes your knowledge of machine learning with   practical algorithmic trading   strategies.   For detailed context and an overview of how each   piece   fits   into   the   broader   system,   please   refer   to   the
Machine Learning for Trading Project page 
(https://gatech.instructure.com/courses/411838/pages/machine-learning-for-trading-project) .
In this project, you will write software that will perform   probabilistic   experiments   involving   an American Roulette wheel   .(https://en.wikipedia.org/wiki/Roulette) . The   project   will   help   provide   you   with   some    initial feel for risk,   probability, and “betting.” Purchasing a   stock   is,   after   all,   a   bet   that   the   stock will increase (or,   in some cases, decrease)   in value. You will submit the   code   for   the   project   to   Gradescope   SUBMISSION. You will also submit to Canvas a report   that   discusses your   experimental   findings.
1.1 Learning Objectives 
The specific learning objectives for this assignment are focused on   the   following   areas:
· Mathematical Tools: Developing an understanding of common probabilistic   and   statistical tools associated with machine learning, including expectations, standard deviations, sampling, minimum values, maximum values, and convergence.
· Research:   Experience researching additional material (conceptual   and   programming) to   ensure   the   successful completion of the assignment.
· Programming  Academic Writing:   Each assignment will build upon one   another. The techniques      around experimentation, graphs,   interpretation (and so on) will   play   important   roles   in this   and   future   projects.
· Course Conduct:   Developing and testing code locally   in the   local   Conda   ml4t   environment,
submitting it for pre-validation in the   Gradescope TESTING   environment,   and   submitting   it for   grading   in the Gradescope SUBMISSION environment.
2. About the Project 
In this   project, you will   build a Simple Gambling Simulator.   Specifically, you   will   revise   the   code   in   the martingale.py file to simulate   1000 successive bets on the outcomes   (i.e.,   spins)   of the American   roulette   wheel using the betting scheme outlined   in the   pseudo-code   below.   Each   series   of   1000   successive   bets   is called an “episode.” You should test for the results of the   betting   events   by   making   successive   calls   to      the get_spin_result(win_prob) function.   Note that you will have to update the win_prob   parameter according to the correct probability of winning. You can figure that   out   by thinking   about   how   roulette   works (see Wikipedia   link   below). 
In this   project, you will evaluate   Professor Balch’s actual betting   strategy   at   roulette   when   he   goes   to   Las   Vegas.
Here   is the pseudocode of the strategy:
episode_winnings = $0 
while episode_winnings < $80: 
won = False 
bet_amount = $1 
while not won 
wager bet_amount on black 
won = result of roulette wheel spin 
if won == True: 
episode_winnings = episode_winnings + bet_amount 
else: 
episode_winnings = episode_winnings - bet_amount 
bet_amount = bet_amount * 2 
Additional details   regarding   how   roulette   betting works:   Betting on   black (or red)   is considered   an   “even money”   bet. That   means that   if you   bet   N chips and win, you   keep your N chips,   and   you   win   another   N            chips.   If you   bet   N chips and you lose, then those   N chips   are   lost.   The   odds   of winning or   losing   depend   on betting at an American wheel or a   European wheel.   For this project, we will   be   assuming   an American   wheel. You can learn more about   roulette and   betting   here: https://en.wikipedia.org/wiki/Roulette. 
3. Your Implementation
You will develop an implementation leveraging the   pseudocode   above that   conducts   several experiments. Conduct the following experiments, then write your report.   Before the   deadline,   make sure   to pre-validate your submission using Gradescope TESTING.   Once you   are   satisfied with   the   results locally and in Gradescope TESTING, submit the   code to   Gradescope   SUBMISSION.   Only   code submitted to Gradescope   SUBMISSION will be graded.   If you submit your   code   to   Gradescope TESTING and have not also submitted your   code   to   Gradescope   SUBMISSION,   you   will   receive   a   zero   (0). 
3.1 Getting Started 
You will   be given a starter framework to   make   it easier to   get started   on   the   project   and   focus   on   the   concepts involved. This   framework assumes you have already   set   up   the ML4T Development 
Environment (https://gatech.instructure.com/courses/411838/pages/ml4t-development-environment-setup) . The framework for Project   1 can be obtained from   the Martingale_2024Fall.zip 
(https://gatech.instructure.com/courses/411838/files/53096803?wrap=1)  
(https://gatech.instructure.com/courses/411838/files/53096803/download?download_frd=1)file   on   Canvas   or Dropbox (https://www.dropbox.com/scl/fi/2qisdfrikezwsm7yaws6w/martingale_2024Fall.zip? 
rlkey=xl4zcpde5o2bkqmpz60e1qyc8st=g31fzvvbdl=1) .   Extract   its   contents   into   the   base   directory   (e.g.,   ML4T_2023Fall, although “ML4T_2021Summer” is shown in the   image   below).   This   will   add   a   new   ” martingale ” folder to the   directory structure.
Within the martingale folder is a   single file: martingale.py 
You will modify the martingale.py file t代 写Project 1: MartingalePython
代做程序编程语言o implement   the   necessary   functionality   for this   assignment.   The            existing code   in the   martingale.py file   may contain   ideas for functions and   methods that could   be   used   in   your implementations. This file must remain and   run from   within   the   martingale   directory   using   the following command:
PYTHONPATH= . ./: . python martingale.py 
3.2 Experiment 1 – Explore the strategy and create some charts 
In this experiment, you will develop code that performs   experiments   using   Professor   Balch’s   original betting strategy. You will run some experiments to determine   how well the   betting   strategy works.   The approach we are going to take   is called   Monte Carlo simulation.   The   idea   is   to   run   a   simulator   repeatedly   with randomized   inputs and assess the results   in   aggregate. Your   implementation will   produce the following charts (i.e., figures):
· Figure 1:   Run your simple simulator   10 episodes and track the winnings, starting from   0   each   time.Plot all   10 episodes on one chart   using   Matplotlib functions. The   horizontal   (X)   axis   must   range from   0 to 300,the vertical (Y) axis must   range from –256   to   +100.   We will   not   be   surprised   if some   of the      plotlines   are   not   visible   because   they   exceed   the   vertical   or   horizontal   scales.
· Figure 2:   Run your simple simulator   1000 episodes.   (Remember that   1000 successive   bets   are   one      episode.)   Plot the   mean value of winnings for each spin round using   the   same   axis   bounds   as   Figure 1.   For example, you should take the   mean of the first spin of all   1000   episodes. Add an   additional   line   above and below the   mean, at mean   plus   standard   deviation,   and   mean   minus   standard   deviation   of the winnings at each   point. 
· Figure 3:   Use the same data you used for   Figure   2   but   plot   the   median   instead   of the   mean. Add an   additional line above and below the   median to   represent   the   median   plus   standard   deviation   and median minus standard deviation of the winnings at each   point.
For all the above figures and experiments, if the target   of $80 winnings   is   reached,   stop   betting,   and allow the $80 value (or whatever value greater than $80 you   have obtained)   to   persist   from   spin   to   spin   (e.g., fill the data forward with a value of $80 or the value greater than   $80   you   have   obtained). 
The charts created by the experiments   must   be   included   in your   report,   along with your   supporting analysis and discussion.   All charts must be   properly   titled,   have   appropriate   axis   labels,   use   consistent   axis   ranges, and   have legends.
3.3 Experiment 2 – A more realistic gambling simulator 
You   may   have   noticed that the original strategy   performed   in experiment   1 works well,   maybe better than   you expected. One reason for this is   that we were   allowing   the   gambler   to   use   an   unlimited   bankroll.   In   this experiment, we   retain the upper limit of $80   in winning   retained   but   make things   more   realistic   by giving the gambler a $256 bankroll. This will   require a   modification   to   the   original   strategy   since   if   he   or she   runs out of money: bzzt, that’s   it.   Repeat the experiments,   as   above, with   this   new   condition.   Note   that once the   player has lost all their   money   (i.e.,   episode_winnings   reach   -256),   stop   betting   and fill   that   number (-256) forward.   An   important corner case to handle   is the   situation where   the   next   bet   should   be   $N,   but you only   have $M (where   M  
· Figure 4:   Run your realistic simulator   1000 episodes and track the winnings,   starting   from   0   each
time.   Plot the mean value   of winnings for each spin using the   same   axis   bounds   as   Figure   1.Add   an additional line above and below the   mean   at   mean   plus   standard   deviation   and   mean   minus   standard   deviation of the winnings at each   point.
· Figure 5:   Use the same data you used for   Figure   4   but   plot   the   median   instead   of the   mean. Add an   additional line above and below the   median to   represent   the   median   plus   standard   deviation   and median minus standard deviation of the winnings at each   point.
The charts created by the experiments will   be   included   in your   report,   along with your   supporting   analysis and discussion.   All charts must be   properly   titled,   have   appropriate   axis   labels,   use consistent axis   ranges, and   have legends. You should use   Python’s   Matplotlib   library.
3.4 Technical Requirements 
The following technical requirements apply to this assignment:
1. The martingale.py file must   implement this API specification 
(https://gatech.instructure.com/courses/411838/pages/api-specifications) .
2. All winnings   must   be tracked   by storing them   in a   NumPy array. You   might call that   array winnings
where winnings[0] should be set to 0   (just   before the first   spin).   The   entry   in winnings[1]   should   reflect   the total winnings after the first spin and   so   on.
3.   Use the   population standard deviation. The standard deviation is   plotted   as   two   lines,   the   upper   standard deviation (e.g., mean +stdev) and   the   lower   standard   deviation   (e.g.,   mean –stdev).
4. You   may   set   a   specific   random   seed   for   this   assignment.   If   a   specific   random   seedisused,   it   can
only   be called once, and   it   must   use your GT   ID as the   numeric   value.   To   promote   the   reproducibility   of results on different machines, we strongly   recommend setting   a   starting   seed,
5. The implementation may optionally write text, statistics,   and/or tables   to   a   single   file   named
p1_results.txt or p1_results.html. These files can be   created   by   each   student   so that   they   do   not   need   to write output to the terminal (or screen). The   use of such files   is   entirely   optional   (i.e.,   left   to   each student).   If used, this file (or both files) should   be   created   in the   same   folder   as   the   .py   file   being   run.
6. You   must   implement the author() and study_group() APIs.









         
加QQ：99515681  WX：codinghelp
