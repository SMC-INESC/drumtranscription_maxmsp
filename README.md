drumtranscription_maxmsp
==============================================================
An open-source streaming drum transcription system for MaxMSP
==============================================================

We implemented an audio drum transcription algorithm in MaxMSP, which can transcribe kick, snare, and hi-hat from live drum performances. The software takes live audio or files as input and triggers events for each drum type as output.

The  MaxMSP patches and the source code for some of the MaxMSP externals are distributed under GPL license.


========================
QUICK START
========================

In order to use this application, you will need to have the visual programming environment MaxMSP installed. The software can be used for free for a period of 30 days. We recommend using the latest version.

You can start using the software right away by loading the DEMO patches. The demos transcribe audio and offer simultaneous audio feedback if the resynthesis button is checked. Midi notes representing transcribed kick, snare or hi-hat can be sent to desired channels.  However, if you have some very basic MaxMSP knowledge, you can adapt the patches to your needs by modifying them.

The algorithm sends quasi-real-time bang messages for each new kick, snare and hi-hat event. 

The application is modular and provides separate patches for different versions. You can build your own drum transcription system. For instance, you can opt for a more reliable transcription for kick and snare, and for a faster, more real-time transcription for hi-hats. Please see the DETAILED DESCRIPTION for more info.


======================================
WHO CAN USE THIS SOFTWARE?
======================================

This software can be used by musicians, visual artists, and researchers. Musicians can control their music performance using the live transcription from the drums. Artists can generate visuals based on the drum events. Scientists can reproduce and compare any part of the research. Furthermore, they can use this system in designing better systems for machine listening or music interaction.

Some MaxMSP knowledge is required if you plan to make serious modifications to the patches.


======================================
TROUBLESHOOTING
======================================
The error messages are displayed in the MaxMSP window. The most common errors are related to external patches missing, or using a very old version of MaxMSP.

If you receive the "not found" error in the message window, then make sure that you are using the version which corresponds to your operating system, and that you are using the latest version of MaxMSP.


====================================
DETAILED DESCRIPTION
====================================

The research behind this system is documented in an ICASSP 2013 paper:
http://www.icassp2013.com/Papers/ViewPapers.asp?PaperNum=4116

The algorithm comprises three different stages: onset detection, feature computation and classification. We implemented patches several versions for each of the stages.
- onset detection - you can use a faster onset detector or the slower one with better resolution
- you can use the faster feature computation which takes just the first 56 ms, or you can use the "best" patch which overlaps 10 frames summing 136 ms of analysis
- you can choose between a trained KNN classifier or a sequential K-means classifier

In the src directory you can find the C source code for the MaxMSP externals. 

The overlapping sounds database can be downloaded from: 
http://www.mediafire.com/download.php?q8nl199bnz7g68n
OR
https://www.dropbox.com/s/6ykurx3lr9s0lj5/overlapping_sounds_db.zip

This work is supported by the ERDF – European Regional Development Fund through the COMPETE Programme (operational programme for competitiveness) and by National Funds through the FCT – Fundacao para a Ciencia e a Tecnologia (Portuguese Foundation for Science and Technology) within project Shake-it, Grant PTDC/EAT-MMU/ 112255/2009. Part of this research was supported by the CASA project with reference PTDC/EIA-CCO/111050/2009 (FCT), and by the MAT project funded by ON.2.


=============================
DEVELOPERS
=============================
If you plan to re-compile again the externals you would need to download the MaxMSP framework and add the src/osx or src/win directory in the examples subdirectory of the framework. You will need to change paths if you decide to build the externals from another path.


=============================
FUTURE WORK
=============================
We plan to implement an external which will take a buffer of audio samples and will separate the sound in two streams: harmonic and percussive. In this way, we can transcribe drums from polyphonic audio, and not only from audio comprising solely drum sounds. 


=============================
HELP
=============================

For any questions email miron.marius [at] gmail [dot] com .