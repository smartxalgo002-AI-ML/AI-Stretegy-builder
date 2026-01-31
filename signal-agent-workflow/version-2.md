```mermaid
graph TD
    A[Backend Signal] -->|Buy/Sell Trigger| B{{Python Script - Signal Handler}}
    
    %% Script Feeds Model
    B -->|OHLCV, Tick, Options, Market Depth| G{OHLCV Models}
    
    %% Specific Context Transfer
    B -->|Timestamp, Symbol, Strategy, Price| C(**Agent 1** - Data Retrieval Agent)
    
    %% Agent 1 Expanded Sources (Previously Agent 2)
    DB1[(Strategy DB)] --> C
    DB2[(News Vector DB)] --> C
    DB3[(Financial DB)] --> C
    DB4[(Corporate Action DB)] --> C
    G -->|Market Trend| C

    %% Agent 2 Central Intelligence
    C -->|Retrieved Context| D(**Agent 2** - Intelligence Retriever)
    E[(Market Sentiment)] --> D
    F[(Book Database)] --> D

    %% Agent 3 & Internet
    D -->|Aggregated Intel Searchs| L(**Agent 3** - Search Agent)
    M[(Internet)] --> L
    L -->|Real-time Research| H(**Agent 4** - Analysis Agent)
    D -->|Aggregated Intel| H

    %% Final Decision Path
    H -->|Analysis Report| I(**Agent 5** - Decision-Making Agent)
    I -->|Final Recommendation| J{Execute Trade?}

    %% Feedback Loop
    J -->|Yes/No| K(**Agent 6** - Feedback Agent)
    K -->|Learn & Refine| FB[(Feedback Database)]
    FB -.-> D

    %% Styling
    style B fill:#f9f,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5
    style I fill:#bbf,stroke:#333,stroke-width:2px
    style K fill:#bfb,stroke:#333,stroke-width:2px
    style FB fill:#fff2cc,stroke:#d6b656,stroke-width:2px
    style G fill:#def,stroke:#333,stroke-width:2px
```
