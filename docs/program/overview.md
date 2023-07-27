## The Data Science ecosystem

Data Science is the art of using data to understand, predict, and solve real-world problems, making it an invaluable tool across all fields for informed decision-making and innovative solutions.

- **Domain and Fundamental knowledge:** Understanding and expertise in specific subject areas (domains) along with foundational knowledge necessary to comprehend and engage with various disciplines and concepts.
- **Computer Science:** The study of algorithms, data structures, and computational systems for solving problems and processing information using computers.
- **Math & statistics:** The discipline that deals with the analysis, interpretation, and manipulation of numerical data, patterns, and relationships, relying on mathematical principles and methodologies.

<img src="/ai-applied-education/assets/images/data-science-ecosystem.jpg" alt="data-science-ecosystem" width="450" style="display: block;margin-left: auto; margin-right: auto; width: 50%;"/>

## The data jobs/roles ecosystem

![data-roles-ecosystem](/ai-applied-education/assets/images/data-roles-ecosystem.jpg)

- **Business Analyst:** Utilizes data to determine project requirements and provides recommendations and reports to stakeholders, focusing on tactical aspects rather than strategic ones.
- **Data Architects and Data Engineers:** Data architects visualize framework requirements, while data engineers build the digital framework to create a solution.
- **Data Analyst:** Analyzes collected data to ensure usefulness and comprehensiveness, interpreting data with strong visualization skills for businesses.
- **Data Scientist:** Combines technical problem-solving skills with natural curiosity to develop ML models and detect patterns and relationships in copious amounts of data.
- **Machine Learning Engineer:** Integrates software engineering with machine modeling abilities, determining the appropriate model and data for ML applications.
- **Business Intelligence Engineer:** Creates unique data visualizations, defining metrics and charts beneficial for business decisions, playing a crucial role in specialized data science models.


## The Software ecosystem

Explain the AI ecosystem

``` mermaid
graph TD
    PC{Python\n cloud} -.->|connects| GC["✅ Google \n Collab"];
    G["☁ Google VM"] -->|has| PC;
    YC["💻 Your computer"] -->|has*| AP{Anaconda\n Python};
    YC -->|has*| PL{Python\n local};
    AP -.->|connects| APJN["✅ Jupyter \n notebook"];
    AP -.->|connects| APC["✅ Console:\n Anaconda\n promt"];
    AP -.->|connects| API[IDE:\n Spyder];
    PL -.->|connects| F[IDE:\n VSCode,\n Pycharm];
    PL -.->|connects| YCC["✅ Console:\n cmd,\n powershell"];
    GIT -.->|connects| YCB["✅ Console:\n Git Bash"];
    YC -->|has*| GIT["✅ GIT"];
    GT["☁ GITHUB"] -.->|connects| GIT;
```

### Glossary

- Google Collab
- Anaconda
- Python
- Jupyter notebook
- IDE
- GIT
- Github
- Console


## The ML ecosystem

Explain the ML ecosystem

``` mermaid
graph TD
    ML[ML models] -->|Labeled data| SML["✅ Supervised models"];
    ML -->|Unlabeled data| UML["✅ Unsupervised models"];
    ML -->|Time data| TS["Time series"];
    ML -->|Reward| RL["Reinforcement learning"];
    SML -->|Continuous var| MLR[Regression];
    SML -->|Categorical var| MLC[Classification];
    UML --> UMLC[Clustering];
    UML --> UMLDR[Dimensionality reduction];
    UML --> UMLA[Anomaly detection];
    UML --> UMLG[Generatives];
```