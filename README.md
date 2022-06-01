# 2015_W11-model
Code for 'W11' model published in Rustichini &amp; Padoa-Schioppa, J Neurophys, 2015

The folders includes several scripts and functions. The main script is W11EC_JNP2015, which runs an entire session. This script is an evolution of that written by Wong and Wang (2006), with some modifications. The script takes several inputs, including 
- the session parameters (number of trials, value ranges, etc.), defined in sessionParams
- the function that simulates the activity of offer value cells, defined in get_nuOV
At the end of the script, there is a preliminary analysis of the results obtained for the session, for which the script calls the function get_tuning.m. This analysis is done here because once it is done we can throw away the detailed trajectories for each trial. In the end, the script saves the session summary, in the data file sessionSum_JNP2015.dat. 

If you want to run multiple sessions and save the results, you can easily do so by changing the file suffix (line 14 in W11EC_JNP2015). To introduce choice hysteresis, see lines 109-110.

The remaining scripts are for data analysis. The main one is plot_sessionSummary_bycell, which is called from the Matlab prompt with plot_sessionSummary_bycell('JNP2015') or equivalent. This script calls several other functions (plot_choicepattern_W11, tuningplot_W11_downsample) and eventually generates 3 figures for the 3 groups of cells. 

The other scripts include:
	- plot_CJ_easysplit, which performs predictive activity analysis on chosen juice cells
	- plot_CV_chX, which performs the analysis on the overshooting of chosen value cells
	- plot_hysteresis1, which does the "behavioral" analysis of choice hysteresis
