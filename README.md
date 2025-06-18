## 📊 Supervised Machine Learning Workflow

```mermaid
flowchart TD
    Env["Execution Environment (Jupyter + Python)"]:::env
    DataSources["Data Sources (CSV, MNIST, Wine, Synthetic)"]:::data
    Preprocess["Preprocessing & Feature Engineering"]:::process

    subgraph "Feature Selection"
        FS1["feature_selection.ipynb"]:::process
        FS2["feature_selection_practiceipynb.ipynb"]:::process
        FS3["Wrapper_methods_feature_Selection.ipynb"]:::process
        FS4["embedded_methods_feature_selection.ipynb"]:::process
    end

    subgraph "Dimensionality Reduction (PCA)"
        PCA1["Kernel_PCA.ipynb"]:::process
        PCA2["MNIST_PCA.ipynb"]:::process
        PCA3["Wine_data_PCA.ipynb"]:::process
    end

    subgraph "Regression Models"
        GD["myGdAlgorithms.ipynb"]:::process
        Poly1["polynomial_reg.ipynb"]:::process
        Poly2["polynomial_reg (1).ipynb"]:::process
        Ridge["Ridge_Regularization_(L2_norm)_.ipynb"]:::process
        Lasso["LASSO_regularization_(L1_norm)_.ipynb"]:::process
    end

    subgraph "Classification Models (KNN)"
        KNNEx["KNN_example.ipynb"]:::process
        KNNScratch["KNN_from_scratch.ipynb"]:::process
    end

    Eval["Evaluation & Visualization\n(plots, metrics)"]:::eval

    Env --> DataSources
    DataSources --> Preprocess
    Preprocess --> FS1
    Preprocess --> PCA1
    Preprocess --> GD
    Preprocess --> KNNEx

    FS1 --> Eval
    PCA1 --> Eval
    GD --> Eval
    KNNEx --> Eval

    click Env "https://github.com/namesakenberg/machine_learning/blob/main/README.md"
    click Preprocess "https://github.com/namesakenberg/machine_learning/blob/main/Checking_multicollinearity.ipynb"
    click FS1 "https://github.com/namesakenberg/machine_learning/blob/main/feature_selection.ipynb"
    click FS2 "https://github.com/namesakenberg/machine_learning/blob/main/feature_selection_practiceipynb.ipynb"
    click FS3 "https://github.com/namesakenberg/machine_learning/blob/main/Wrapper_methods_feature_Selection.ipynb"
    click FS4 "https://github.com/namesakenberg/machine_learning/blob/main/embedded_methods_feature_selection.ipynb"
    click PCA1 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/Kernel_PCA.ipynb"
    click PCA2 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/MNIST_PCA.ipynb"
    click PCA3 "https://github.com/namesakenberg/machine_learning/blob/main/PCA/Wine_data_PCA.ipynb"
    click GD "https://github.com/namesakenberg/machine_learning/blob/main/myGdAlgorithms.ipynb"
    click Poly1 "https://github.com/namesakenberg/machine_learning/blob/main/polynomial_reg.ipynb"
    click Poly2 "https://github.com/namesakenberg/machine_learning/blob/main/polynomial_reg (1).ipynb"
    click Ridge "https://github.com/namesakenberg/machine_learning/blob/main/Ridge_Regularization_(L2_norm)_.ipynb"
    click Lasso "https://github.com/namesakenberg/machine_learning/blob/main/LASSO_regularization_(L1_norm)_.ipynb"
    click KNNEx "https://github.com/namesakenberg/machine_learning/blob/main/KNN/KNN_example.ipynb"
    click KNNScratch "https://github.com/namesakenberg/machine_learning/blob/main/KNN/KNN_from_scratch.ipynb"

    classDef data fill:#D0E6FF,stroke:#000
    classDef process fill:#CFFFD0,stroke:#000
    classDef env fill:#E0E0E0,stroke:#000
    classDef eval fill:#FFF4C1,stroke:#000
