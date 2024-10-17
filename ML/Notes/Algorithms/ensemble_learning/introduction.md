# Ensemble Learning

## What is Ensemble Learning?
Ensemble learning is a machine learning technique where multiple models, also known as "weak learners," are combined to solve a particular problem. The collective performance of these models often exceeds that of any single model, leveraging the "wisdom of the crowd" approach.

## Wisdom of the Crowd
The "wisdom of the crowd" concept suggests that aggregating multiple opinions or predictions tends to yield better results than relying on a single source. In machine learning, ensemble methods take advantage of this principle by combining the outputs of different models to achieve a more accurate and robust final prediction.

## Types of Ensemble Learning

### Diagram Explanation
Below is a diagram illustrating the four main types of ensemble learning techniques, showing whether they use the same algorithm with different training datasets, or different algorithms.
```mermaid
flowchart TD
    A[Ensemble Learning] --> B(Bagging)
    A --> C(Boosting)
    A --> D(Stacking)
    A --> E(Voting Ensemble)
    
    subgraph "Same Algorithm, Different Training Data" 
        style B fill:#6baed6,stroke:#1e3a8a,stroke-width:2px
        style C fill:#6baed6,stroke:#1e3a8a,stroke-width:2px
        B
        C
    end
    
    subgraph "Different Algorithms" 
        style D fill:#f9c74f,stroke:#b56800,stroke-width:2px
        style E fill:#f9c74f,stroke:#b56800,stroke-width:2px
        D
        E
    end

    B --> |Bootstrap Sampling| F{Multiple Training Datasets}
    C --> |Sequential Training| F
    D --> |Base Models| G{Different Algorithms}
    E --> |Voting| G

    B --> H[Random Forest]
    B --> I[Bagged Decision Trees]
    C --> J[AdaBoost]
    C --> K[Gradient Boosting]
    C --> L[XGBoost]
    C --> M[LightGBM]
    C --> N[CatBoost]
    D --> O[Custom Meta-Model]
    E --> P[Hard and Soft Voting]
    
    style H fill:#90be6d,stroke:#005f00,stroke-width:2px
    style I fill:#90be6d,stroke:#005f00,stroke-width:2px
    style J fill:#f94144,stroke:#a00000,stroke-width:2px
    style K fill:#f94144,stroke:#a00000,stroke-width:2px
    style L fill:#f94144,stroke:#a00000,stroke-width:2px
    style M fill:#f94144,stroke:#a00000,stroke-width:2px
    style N fill:#f94144,stroke:#a00000,stroke-width:2px
    style O fill:#577590,stroke:#0f4c75,stroke-width:2px
    style P fill:#577590,stroke:#0f4c75,stroke-width:2px
```
