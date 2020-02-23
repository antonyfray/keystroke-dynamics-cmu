Working on this problem: https://www.cs.cmu.edu/~keystroke/.
Supporting paper: http://www.cs.cmu.edu/~keystroke/KillourhyMaxion09.pdf

Data comes from 51 subjects typing ".tie5Roanl" 400 times across multiple sessions.

Our goal is to develop a model which has a minimal equal error rate. 

(Diagram of minimal equal error rate https://api.intechopen.com/media/chapter/66135/media/F2.png).

Questions that immediately need answering:
- What type of problem is this (classification or regression)?
- Has anyone attempted this problem before?
    - If so, how did they approach it? 
        - Which detectors / feature sets / models did they use?
        - What was successful about their approach? 
        - What were their limitations?
- What do the features in the dataset represent?
- Which do we prioritise - false positives or false negatives (aka in this context: false-alarm rates and miss rates).
    - From the literature (and common sense to be honest), we should prioritise lowering miss rates (it's better to lock out a user, than have a threat access the system).

These were largely answered through reading the aforementioned paper, and doing some background reading and research.

The aforementioned paper also detailed a method by which different detectors could be compared on the same dataset. So to evaluate how our 'new' model performs against its competitors, it makes sense to first implement a pre-existing model, then our new model, and compare performance under the same conditions.

Note: The paper implemented the techniques using R (which I've not used before). Implementation in Python _should_ be the same, but there may be some underlying differences in R/Python's mathematics libraries

-----
Order in which the notebooks were devised (and the logical order in which to read them):
- exploratoryAnalysis.ipynb
- manhattan.ipynb
- manhattanNoDD.ipynb
- manhattanNoUD.ipynb
- manhattanNoH.ipynb
- manhattanFiltered.ipynb
- manhattanFilteredNoUD.ipynb
- comparedDetectors.ipynb
