graph TD
    A[Backend Signal] -->|Buy/Sell Trigger| B(**Agent 1** - Signal Handler Agent)
    
    B --> C(**Agent 2** - Data Retrieval Agent)
    
    %% Data Sources with List
    C -->|Learn & Refine| FB[(Feedback Database)] 
    C --> D[(Vector Database)]
    D -->|"Market books<br/>Market Strategies<br/>Market research paper<br/>Past news data<br/>Past market live data"| H
    
    C --> E[(Market Sentiment)]
    E -->|"Market Live<br/>Live News"| H


    C --> G[(OHLCV Models)]
    
    %% Search Agent
    C --> L(**Agent 3** - Search Agent)
    L --> M[(Internet)]

    %% Analysis Loop
    G & M & FB --> H(**Agent 4** - Analysis Agent)

    H -->|Sentiment & Forecasts| I(**Agent 5** - Decision-Making Agent)
    I -->|Final Recommendation| J{Execute Trade?}

    %% Feedback Loop
    J -->|Yes/No| K(**Agent 6** - Feedback Agent)
    K -->|Learn & Refine| FB[(Feedback Database)] 
    
    
    %% Styling
    style A fill:#f98,stroke:#333,stroke-width:5px
    style I fill:#bbf,stroke:#333,stroke-width:2px
    style K fill:#bfb,stroke:#333,stroke-width:2px
    style FB fill:#fff2cc,stroke:#d6b656,stroke-width:2px
