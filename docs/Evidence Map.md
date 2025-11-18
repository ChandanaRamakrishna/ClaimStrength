#Evidence Map

flowchart LR
    %% Claim nodes (color = strength)
    C1(["🟢 Claim 1: GPT-4 as tutor"]):::strong
    C2(["🟢 Claim 2: AI generates feedback"]):::strong
    C3(["🟢 Claim 3: Bloom-aligned MCQs"]):::strong
    C4(["🟢 Claim 4: Predicts performance"]):::strong
    C5(["🟡 Claim 5: Creativity homogenization"]):::moderate
    C6(["🟢 Claim 6: Digital divide risk"]):::strong

    %% Source nodes (number them if multiple per claim)
    S11["arXiv (2024)"]:::src
    S21["DeepLearning.ai (2024)"]:::src
    S31["PMC (2024)"]:::src
    S41["SSRN (2023)"]:::src
    S51["Science.org (2024)"]:::src
    S52["Nature (2024)"]:::src
    S61["Inspera (2023)"]:::src

    %% Edges: claims <-> sources (edge labels show snippet count)
    C1 ---|3 cites| S11
    C2 ---|2 cites| S21
    C3 ---|2 cites| S31
    C4 ---|2 cites| S41
    C5 ---|2 cites| S51
    C5 ---|1 cite|  S52
    C6 ---|2 cites| S61

    %% Grouping
    subgraph Positive_Impact
      C1 --> C2 --> C3 --> C4
    end
    subgraph Ethics_&_Equity
      C5 --> C6
    end

    classDef strong fill:#b8f3c6,stroke:#156a2f,stroke-width:2px,color:#0b3d1d;
    classDef moderate fill:#ffe7b0,stroke:#a86e00,stroke-width:2px,color:#4a3000;
    classDef src fill:#e8f0fe,stroke:#1a73e8,color:#0b3d1d;

    %% Legend (fake nodes)
    L1(["🟢 Strong"]):::strong
    L2(["🟡 Moderate"]):::moderate
    L1 -. legend .- L2
