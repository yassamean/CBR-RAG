# CBR-RAG
README for
Electronic attachment on USB flash drive for master's thesis
"Towards Explainable Process Models: Answering Why-Questions in BPMN through Case-Based Reasoning"
by Yassamin Asgari / s8641599@stud.uni-frankfurt.de
submitted to Department of Informatics/Goethe-University Frankfurt
08th May 2026

####### Contents on electronic attachment #######

Master's thesis document as PDF

Folder "Analysis":
-- 4 Jupyter notebook files that work with the raw data file called data_CBR-RAG_2026-04-06_13-14_final; all boxplots, the scatterplot and the tables are made through the respective file, except for the tables for H4, which were created in SPSS.
-- Raw data file called data_CBR-RAG_2026-04-06_13-14_final
-- Summary/overview Excel file that SoSci generated automatically, called frequencies_CBR-RAG, which also includes manual analysis in Excel that I did for the qualitative analysis

Folder "Code":

-- 1 Jupyter Notebook "CBR-RAG" 
-- 1 Jupyter Notebook "Plain_LLM"

Folder "Data_set":

-- 5 BPMN models 

-- The folder "case_query" containing 6 different questions (.txt-files)

-- The folder "case_document" containing 6 different BPMN process model seralized in XML + questions-answer pairs  (.txt-files)

Folder "Experimental_output":

-- All generated textual process descriptions + cosine similarity scores differentiated by all questions (.txt-files)


# CBR-RAG — How to Run

Jupyter Notebook "CBR-RAG.ipynb" requires:
- Python 3.14.2 (other versions not tested)
- [Ollama](https://ollama.com) running locally on `http://localhost:11434` with the `llama3.1` model pulled
  
The"CBR-RAG.ipynb" includes the prompt template and pipleline, basically everythign to run it, expect for the bpmn for the pattern adaptation category
For the question type pattern adaptation category please copy paste the BPMN XML (without the dimension part) into the variable new_bpmn

## Dependencies
Install the required Python libraries:
```bash
pip install haystack-ai
pip install haystack-integrations[ollama]
```
For further details on these libraries, see:
- [haystack-ai (deepset)](https://docs.haystack.deepset.ai)
- [haystack-integrations — Ollama](https://haystack.deepset.ai/integrations/ollama)


## Folder Structure
The notebook expects the following folders in the same directory as `CBR-RAG.ipynb`:
case_query/        # Plain-text query examples used for embedding and retrieval
case_document/     # Matching XML/BPMN case documents loaded at inference time


## How to Run

1. Start Ollama locally and make sure the `llama3.1` model is available:
   ```bash
   ollama pull llama3.1
   ollama serve
   ```

2. Open and run `CBR-RAG.ipynb` from top to bottom. The notebook contains the full pipeline setup, prompt template, and inference logic. The inline comments explain the underlying logic of each component.


## Pattern Adaptation — BPMNs Not in the Case Base

For questions that require **pattern adaptation**, the target BPMN process must be provided manually, as the following processes are not yet indexed in the case base:

- `02_Departure_Baggage_Handover.bpmn`
- `03_Departure_Boarding_Gate_International.bpmn`
- `04_Arrival_Lost_Baggage.bpmn`

To use one of these, paste the BPMN XML content into the `new_bpmn` variable in the notebook. Only paste the content inside `<bpmn:process>...</bpmn:process>` — exclude the `BPMNDiagram` / `BPMNShape` dimension block at the end of the file.

If the target process is already in the case base, leave `new_bpmn` as an empty string.


####### How-to run Plain-LLM #######
Only tested with Python 3.14.2
Jupyter Notebook "Plain_LLM.ipynb" requires ...?
BPMN XML (without the dimension part) needs to be pasted for every bpmn process model in the propmt after the part "BPMN model "Example" serialised in XML:".

Dependencies: 

Comments + description in thesis PDF should enable you to understand its underlying logic


To open provided BPMN models as .bpmn-files you need a modelling tool
This thesis worked with Camunda Modeler: https://camunda.com/de/platform/modeler/
