## The Data Science ecosystem

Explain Data Science


## The data jobs ecosystem

The data jobs ecosystem


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