# Automatic Tex-to-SPARQL for the GOLEM Knowledge Graph

Repository for the work "Natural Language Querying for Humanities Knowledge Graphs: A Case Study on the GOLEM Knowledge Graph". 

GOLEM KG is available on its [public SPARQL endpoint](http://graph.golemlab.eu:8890/sparql).


## Contents

- **dataset**  
  It contains the _template questions_, _instantiated questions_ and _paraphrased questions_ datasets, as described in the paper. Each dataset is released in TSV format. Each TSV has the following headers:
  - Language:
    The language of the natural language question.
  - Question:
    The natural language question.
  - SPARQL:
    The corresponding gold SPARQL query.
  
- **evaluation/results**  
  It contains the text-to-SPARQL processing output and evaluation data for each dataset in each experimental setting. As described in the paper, we tested deepseek-coder-v2 with a Zero-Shot (ZS), naive Few-Shot (nFS) and adapted Dynamic Few-Shot Learning (aDFSL) prompting approaches. In addition, we tested deepseek-r1:7b and llama3.1:70b with adapted Dynamic Few-Shot Learning (aDFSL) prompting approach.

  The columns in the TSV files corresponding to the runs are the same as per the datasets, plus:
  
  - Response:
    The response obtained by running the gold SPARQL query on [GOLEM KG's SPARQL endpoint](http://graph.golemlab.eu:8890/sparql)
  - lang_det:
    The automatic language detection output
  - Prompt:
    The prompt sent to the LLM
  - Generated_SPARQL:
    The generated SPARQL query
  - Generated_response:
    The output obtained by running the generated SPARQL query on [GOLEM KG's SPARQL endpoint](http://graph.golemlab.eu:8890/sparql)

- **evaluation/error_analysis**  
  Contains error analysis data.   The columns in the TSV files corresponding to the runs are the same as per the results, plus:
  - Error Type
  - Error Sub-type

