# AI-Stretegy-builder
Here is the work flow

graph TD
    A[PDF Knowledge Base] -->|RAG Retrieval| B(Researcher Agent: DeepSeek-R1 32B)
    B -->|Generates Hypothesis| C[Coder Agent: DeepSeek-R1 32B]
    C -->|Generates Python Script| D{Backtest Engine}
    
    D -->|Failure: Code Error| C
    D -->|Success: Performance Data| E(Auditor Agent: DeepSeek-R1 32B)
    
    E -->|Analyze Reasoning| F{Decision Gate}
    
    F -->|Win Rate > 55%| G[Move to Active Ledger]
    F -->|Win Rate 40-55%| H[Refine & Retry Loop]
    F -->|Win Rate < 40%| I[Discard Bin & Blacklist]
    
    H -->|Modified Logic| C
    I -->|Negative Feedback| B

    %% --- NEW BULLETPROOFING WORKFLOW --- %%
    
    G --> J{Stress Test Engine: 100 Trades}
    J -->|50/100 Pass| K[Success Tier: Monitor]
    J -->|20/100 Neutral| L(Search Agent: Root Cause Analysis)
    J -->|30/100 Fail| L
    
    L --> M{Reason Identified?}
    
    M -->|No: Logic Mystery| N[Loss Safety Score: LOW]
    M -->|Yes: Market Regime Found| O[Loss Safety Score: HIGH]
    
    O --> P[Update Strategy Database: Logic + Edge Cases]
    N --> Q[Alert: Untrusted Edge Case]

    P --> A

    style G fill:#9f9,stroke:#333,stroke-width:2px
    style I fill:#f96,stroke:#333,stroke-width:2px
    style N fill:#ff4d4d,stroke:#333,stroke-width:2px
    style O fill:#4dff4d,stroke:#333,stroke-width:2px
