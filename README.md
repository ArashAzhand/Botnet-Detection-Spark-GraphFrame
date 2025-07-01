# Botnet Detection Using Spark GraphFrames on CTU-13 Dataset

## Overview

This project analyzes network traffic data from the [CTU-13 dataset](https://mcfp.felk.cvut.cz/publicDatasets/CTU-Malware-Capture-Botnet-42/detailed-bidirectional-flow-labels/) (Scenario 42 - Neris Botnet) using Apache Spark and GraphFrames. The goal is to detect botnet activity by modeling network flows as a large-scale graph, extracting graph features, and applying machine learning classification to identify suspicious nodes and connections.

## Environment Setup

- Apache Spark with GraphFrames package
- Python with PySpark
- Docker (optional) to run a ready-to-use Spark + Jupyter environment
- Jupyter Notebook for interactive development

## Dataset

The CTU-13 dataset provides detailed bidirectional network flow summaries, including source/destination IPs, ports, protocols, and labels (Botnet, Normal, Background).

## Methodology

1. **Data Preprocessing**: Simplified the label column to three main classes: Botnet, Normal, and Background.
2. **Graph Construction**: Built a network graph with IP addresses as vertices and network flows as edges.
3. **Graph Analytics**: Calculated vertex-level features such as degree and PageRank to characterize the importance and connectivity of each IP.
4. **Feature Engineering**: Joined graph metrics back to flow data to create a feature set for classification.
5. **Classification**: Trained a Random Forest model to classify flows into Botnet, Normal, or Background classes.
6. **Evaluation**: Assessed the model performance using F1-score and classification report to handle imbalanced data.

## Results

The model achieved strong classification performance, particularly in distinguishing botnet traffic, demonstrating the effectiveness of graph-based features combined with Spark’s scalable processing.

![image](https://github.com/user-attachments/assets/a18276f1-8fd7-487a-a05c-1371811e26c6)


## Usage

1. Clone this repository.
2. Run the Jupyter notebook in an environment with Spark and GraphFrames installed.
3. Follow the notebook to reproduce the analysis and classification results.

## Notes

- Due to the dataset size and graph complexity, computations can be intensive but are efficiently handled by Spark’s distributed architecture.
- Docker images used to run the environment can be found [here](jupyter/pyspark-notebook) (if you provide your image).

## Conclusion

Spark GraphFrames provides a powerful platform for large-scale graph analysis in cybersecurity, enabling efficient botnet detection on real-world network traffic data.
