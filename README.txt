Classical Reasoning Agent - README
==================================
Files
  reasoning_agent.ipynb  full implementation (parser, forward chaining, backward chaining, evaluation, submission writer)
  report.pdf             representation, algorithms, experiments, traces
  submission.csv         columns: id,label  (True/False)  -- see note below

How to run
  1. pip install pandas datasets          (datasets is only needed to download the public data)
  2. Put the private test file next to the notebook as test.csv (csv/json/jsonl with columns id, context, question;
     alternative column names such as premises/statement are auto-detected) or change TEST_PATH in the config cell.
  3. Run all cells. The notebook prints accuracy and total inference time per public dataset, then writes submission.csv.

Configuration (second cell)
  CLOSED_WORLD  'auto' (default) | True | False   - negation as failure vs explicit negation only
  HF_SOURCES    Hugging Face dataset ids used for development
  TEST_PATH     path of the private test file

Note: the submission.csv shipped here was generated from the built-in demo cases (the private test set is not available
to the author). Re-run the notebook on the real test file to regenerate it.
Implementation uses only the Python standard library for reasoning; no generative AI is used.
