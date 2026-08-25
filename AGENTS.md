# Data-Lab public repository contract

This repository exists only to make the audio preparation used by AI-Lab
transparent and reproducible. Keep its scope deliberately narrow.

- Public content may describe public datasets, deterministic selection,
  technical audio conversion and verifiable preparation steps.
- Never add downloaded audio, transcripts, generated manifests, databases,
  source inventories, operational configuration, private workflows or
  confidential data.
- The full Data-Lab service is versioned independently in the private `opts/`
  repository. Never stage `opts` or turn it into a submodule.
- Do not add credentials. A private Git repository is not a secret store.
- Do not make this repository a deployment dependency of AI-Lab. It documents
  how input data was prepared; AI-Lab owns inference independently.
