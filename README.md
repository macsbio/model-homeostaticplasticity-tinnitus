# Modelling Homeostatic Plasticity in the Auditory Cortex Results in Neural Signatures of Tinnitus

<b> Authors: </b> Hannah Schultheiss, Isma Zulfiqar, Michelle Moerel

In the <b>TinnitusProject_MatlabFiles</b> folder, you will find three sub-folders, 12 matlab scripts (.m) and 2 matlab files (.mat).

There are auditory cortex (AC) models for 3 different conditions: <b>healthy, hearing loss (HL), and homeostatic plasticity (HSP)</b>. These scripts simulate neuronal responses using the Wilson Cowan Cortical Model (WCCM, Zulfiqar et al., 2020). 

For each of these models, 3 ‘sub-models’ exist: 

1.	 <b>AC_ModelHealthy, AC_ModelHL and AC_ModelHSP</b> compute the model responses in response to white Gaussian noise (white_noise.mat). The AC_ModelHSP file contains the code for the step-wise updating of the synaptic weights and loads meanCh_Healthy.mat, containing the mean firing rate of the healthy model.

2.	 <b>AC_ModelHealthy_spont, AC_ModelHL_spont and AC_ModelHSP_spont</b> compute model responses in the presence of added spontaneous activity (random input added to the output of the LIN). For AC_ModelHSP_spont, the synaptic weights computed by 'AC_ModelHSP' need to be loaded. The synaptic weights that were already computed can also be found in the results folder (synWeights_HSP_updateP/ synWeights_HSP_noUpdateP).

3.	<b>AC_ModelHealthy_FTC, AC_ModelHL_FTC and AC_ModelHSP_FTC</b> are used when running the runModelFTCs.m code. The model function accept a carrier frequency as input and computes the excitatory response in response to the pure tone stimulus.

<b>runModelFullFTCs_extendedRange.m</b> is a modified script for constructing FTCs. It allows for denser sampling close to the BF and coarser sampling at non-preferred frequencies.

The <b>LookupTable_Construction.m</b> file was used to generate the two/three-dimensional 
solution space for the synaptic weights that do not cause hyperactivity. The 
look-up tables can be found in the folders 'Look-Up Tables no updated input models'
and ‘Look-Up Tables updated input models’.

The <b>Results</b> folder contains 18 matlab (.mat) files and one subfolder.

The subfolder <b>Extended updateP – 60 HL</b> contains the results for 60% HL models when allowing for larger update (/alpha) values.

-<b> fft_analysis_spont_noUpdateP</b>: 3x3 table containing the oscillation frequencies over space of models with spontaneous activity in the absence of an input sound. Rows contain the different HL ranges (10,20,40) and columns the HL severity (40, 60, 80%)

- <b>FTCs_extendedRange_HLrange_...</b>: 98x97 vectors containing the responses to pure tones used to construct the FTCs for healthy, HL and both HSP implementations. Rows correspond to model unit and columns to the pure tone. 'responsesAxis' contains the frequencies of the tones used to construct the FTCs.

- <b>spont_responses_...</b>: 98x1 vector containing the model responses for each model 
channel in the presence of spontaneous activity without an input sound

- <b>spontWGN_responses_...</b>: 98x1 vector containin the model responses for each model
channel in the presence of spontaneous activty with a white Gaussian noise used as
an input sound

- <b>synWeights_HSP_...</b>: The synaptic weights obtained from the step-wise updating of 
the HSP implementation

- <b>wgn_responses_...</b>: 98x1 matrix containing model responses for each channel in response
to white Gaussian noise 

Contact info: michelle.moerel@maastrichtuniversity.nl 
