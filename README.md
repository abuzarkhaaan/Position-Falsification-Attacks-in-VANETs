# Run Guide

This guide explains how to run the dataset profiling and split-generation pipeline.

## What this script does

The script performs the following tasks:

1. Loads the source CSV dataset.
2. Automatically detects important columns such as:
   - sender or node identifier
   - timestamp or time step
   - attack/category label
   - binary malicious or benign label
   - scenario-related identifiers
3. Infers a binary malicious label if one is not already cleanly available.
4. Builds a normalized category field for malicious families.
5. Constructs scenario identifiers from available metadata.
6. Generates a scenario-aware train, validation, and test split.
7. Computes window counts using a fixed window size and stride.
8. Produces summary CSV outputs.
9. Saves metadata as JSON.
10. Exports a figure in both PNG and PDF formats.

## Expected input

The script expects a CSV dataset at:

```python
DATA_PATH = "/kaggle/input/datasets/ivarprudnikov/veremi-extension-data-1-21-gb/mixalldata_clean.csv"
