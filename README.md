Here’s a mid-size diagram with two clear phases and seven steps—big enough to show the detail, but small enough to stay readable. Paste this into any Mermaid-aware editor:

flowchart TD
  subgraph 1. Preprocessing
    A[Scan folder for PPT files] 
    B[Extract each slide’s text & images]
    C[Generate keywords per slide]
    D[Build lookup: “keyword → PPT command”]
  end

  subgraph 2. Runtime Control
    E[Listens for voice input]
    F[Convert speech to text]
    G[Match text → prebuilt command]
    H[Execute command on selected PPT]
    I[Provide visual/audible feedback]
    E --> F --> G --> H --> I --> E
  end

  A --> B --> C --> D --> E

Step-by-step:
	1.	Scan folder for PPT files
Locate all PowerPoints and assign them IDs (PPT1, PPT2, …).
	2.	Extract each slide’s text & images
Pull the raw content from every slide in each PPT.
	3.	Generate keywords per slide
Use simple NLP (or manual tags) to pick 3–5 keywords for each slide.
	4.	Build lookup: “keyword → PPT command”
Precompute commands—e.g. open PPT2, goto slide 5—and index them by keyword.

⸻

	5.	Listens for voice input
Idle until the presenter speaks a command.
	6.	Convert speech to text
Route audio through your speech-to-text engine.
	7.	Match text → prebuilt command
Look up the keywords/phrases in your command table (or via an LLM).
	8.	Execute command on selected PPT
Run the terminal or API call to change slides, open files, etc.
	9.	Provide visual/audible feedback
Confirm the action (e.g. “Going to slide five”) before returning to listening.