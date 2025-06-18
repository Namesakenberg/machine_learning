flowchart TD
    %% Stages and pipeline
    subgraph " "
    end

    %% Execution Environment
    Env["Execution Environment\n(Jupyter + Python)"]:::env
    DataSources["Data Sources"]:::env
    FE["Preprocessing & Feature Engineering"]:::pre
    subgraph "Feature Selection"
        FS1["Checking Multicollinearity"]:::pre
        FS2["Wrapper Methods"]:::pre
        FS3["Embedded Methods"]:::pre
    end
    subgraph "Dimensionality Reduction (PCA)"
        PCA1["Kernel PCA"]:::pre
        PCA2["MNIST PCA"]:::pre
        PCA3["Wine Data PCA"]:::pre
    end
    subgraph "Model Training"
        subgraph "Regression Models"
            Reg1["Linear Regression"]:::model
            Reg2["Polynomial Regression"]:::model
            Reg3["Ridge & Lasso"]:::model
        end
        subgraph "Classification Models"
            Clf1["K-Nearest Neighbors"]:::model
            Clf2["Support Vector Machines"]:::model
            Clf3["Naive Bayes"]:::model
            Clf4["Decision Trees"]:::model
            Clf5["Ensemble Methods"]:::model
        end
    end
    MS["Model Selection &\nHyperparameter Tuning"]:::model
    Eval["Evaluation & Visualization"]:::eval

    %% Flow
    Env -->|uses| DataSources
    DataSources -->|ingests data| FE
    FE -->|feature engineering| FS1
    FE -->|feature engineering| FS2
    FE -->|feature engineering| FS3
    FE -->|dim reduction| PCA1
    FE -->|dim reduction| PCA2
    FE -->|dim reduction| PCA3
    FS1 -->|features| Reg1
    FS2 -->|features| Reg2
    FS3 -->|features| Reg3
    PCA1 -->|components| Clf1
    PCA2 -->|components| Clf2
    PCA3 -->|components| Clf3
    FE -->|processed data| Clf4
    FE -->|processed data| Clf5
    Reg1 --> MS
    Reg2 --> MS
    Reg3 --> MS
    Clf1 --> MS
    Clf2 --> MS
    Clf3 --> MS
    Clf4 --> MS
    Clf5 --> MS
    MS -->|selects best model| Eval

    %% Click Events
    click Env "https://github.com/namesakenberg/machine_learning/blob/main/README.md"
    click PCA2 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/MNIST_PCA.ipynb"
    click PCA3 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/Wine_data_PCA.ipynb"
    click FS1 "https://github.com/namesakenberg/machine_learning/blob/main/Feature_Selection/Checking_multicollinearity.ipynb"
    click FS2 "https://github.com/namesakenberg/machine_learning/blob/main/Feature_Selection/Wrapper_methods_feature_Selection.ipynb"
    click FS3 "https://github.com/namesakenberg/machine_learning/blob/main/Feature_Selection/embedded_methods_feature_selection.ipynb"
    click PCA1 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/Kernel_PCA.ipynb"
    click MS "https://github.com/namesakenberg/machine_learning/tree/main/Model selection techniques/"
    click Reg1 "https://github.com/namesakenberg/machine_learning/blob/main/Linear_Regression/myGdAlgorithms.ipynb"
    click Reg2 "https://github.com/namesakenberg/machine_learning/blob/main/Linear_Regression/polynomial_reg.ipynb"
    click Clf1 "https://github.com/namesakenberg/machine_learning/blob/main/KNN/KNN_example.ipynb"
    click Clf2 "https://github.com/namesakenberg/machine_learning/blob/main/SVM/Hard_and_soft_margin_SVM.ipynb"
    click Clf3 "https://github.com/namesakenberg/machine_learning/blob/main/naive bayes/sentiment-analysis-imdb-naive-bayes.ipynb"
    click Clf4 "https://github.com/namesakenberg/machine_learning/blob/main/Decision Trees/Decision_trees_example.ipynb"
    click Clf5 "https://github.com/namesakenberg/machine_learning/blob/main/Ensemble learning/bagging/Bagging.ipynb"

    %% Styles
    classDef env fill:#DDDDDD,stroke:#888,stroke-width:1px,stroke-dasharray: 5 5,rx:8,ry:8;
    classDef pre fill:#C8E6C9,stroke:#2E7D32,stroke-width:2px;
    classDef model fill:#BBDEFB,stroke:#1565C0,stroke-width:2px;
    classDef eval fill:#FFF9C4,stroke:#F9A825,stroke-width:2px;
