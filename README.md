# pubmed_fetcher
PubMed Pharma Paper Fetcher

 Author: Edula Vinitha  
 Madanapalle Institute of Technology and Science
 Project Description
The research papers are retrieved from PubMed using a Python-based command-line script that filters them to only include those with at least one non-academic author connected to a pharmaceutical or biotech company. Key metadata is included in the CSV file that is saved with the output.
 Problem Statement

 Fetch papers using the PubMed API.
Filter for papers with non-academic authors (pharma/biotech affiliation).
Output key details in a structured CSV file.
 Methodology
The program fetches PubMed articles via the Entrez API, then filters papers using a rule-based heuristic that identifies non-academic authors by excluding academic keywords (like "university", "college") and including commercial terms (like "pharma", "biotech"), extracts relevant metadata using regular expressions and structured parsing, and finally saves the results in CSV format via a command-line interface.
Query & Fetch
Uses [NCBI's PubMed API](https://www.ncbi.nlm.nih.gov/home/develop/api/) via Bio.Entrez.
Supports full PubMed query syntax. Fetches metadata including title, authors, date, and affiliations.
Filtering Heuristic

An author is considered non-academic if:
 Their affiliation does NOT include academic terms like:
  "university", "institute", "college", "school", etc.
Their affiliation includes company-related terms like:
  "pharma", "biotech", "inc", "ltd", "LLC".

  Project Structure
pubmed_project/
├── cli.py # Command-line interface
└── pubmed_fetcher/
├── init.py  # Marks package
└── fetcher.py # Core logic
