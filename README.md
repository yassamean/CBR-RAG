# CBR-RAG
README for
Electronic attachment on USB flash drive for master's thesis
"Towards Explainable Process Models: Answering Why-Questions in BPMN through Case-Based Reasoning"
by Yassamin Asgari / s8641599@stud.uni-frankfurt.de
submitted to Department of Informatics/Goethe-University Frankfurt
08th May 2026

####### Contents on electronic attachment #######

Master's thesis document as PDF

Folder "Analysis": (UPDATE THIS)

-- Mainly Overview_Results_Analysis.xlsx, it includes:

  ---> Overview on model characteristics and descriptive statistics

  ---> Raw results from each experiment

  ---> Aggregated results from each experiment
-- All Python scripts used to create box plots and scatter plots

-- All constructed .csv-files for the analysis

Folder "Code":

-- 1 Jupyter Notebook "CBR-RAG" 
-- 1 Jupyter Notebook "Plain_LLM"

Folder "Data_set":

-- 5 BPMN models (mainly from Miriam Herold and Mirjam Minor (2020) as well as this website ( ) in .bpmn format

-- The folder "case_query" containing 7 different questions (.txt-files)

-- The folder "case document" containing 7 different BPMN process model seralizes in XML + questions-answer pairs  (.txt-files)

Folder "Experimental_output":

-- All generated textual process descriptions differentiated by all questions (.txt-files)



####### How-to run CBR-RAG ####### (UPDATE THIS)

Only tested with Python 3.14.2
Jupyter Notebook "CBR-RAG.ipynb" requires ...?
The"CBR-RAG.ipynb" includes the prompt template and pipleline, basically everythign to run it, expect for the bpmn for the pattern adaptation category
For the question type pattern adaptation category please copy paste the BPMN XML (without the dimension part) into the variable new_bpmn

Dependencies: none? Ollama Generator runterladen? Frag Tolga
library: see this URL for information on how to install this library:
Comments should enable you to understand its underlying logic

# Only paste the BPMN XML code (without the dimension part) here for the question category pattern adaptation. So in the cases, where the bpmn is not already in the case base.
#The following bpmns are not in the case base: 03_Departure_Boarding_Gate_International.bpmn, 04_Arrival_Lost_Bagggage.bpmn, 02_Departure_Baggage_Handover.bpmn

####### How-to run Plain-LLM #######
Only tested with Python 3.14.2
Jupyter Notebook "Plain_LLM.ipynb" requires ...?
BPMN XML (without the dimension part) needs to be pasted for every bpmn process model in the propmt after the part "BPMN model "Example" serialised in XML:".

Dependencies: none? Ollama Generator runterladen? Frag Tolga
library: see this URL for information on how to install this library: 
Comments + description in thesis PDF should enable you to understand its underlying logic


To open provided BPMN models as .bpmn-files you need a modelling tool
This thesis worked with Camunda Modeler: https://camunda.com/de/platform/modeler/
