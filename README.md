# Graph Neural Network Pooling by Edge Cut

## **Introduction**
This project explores a novel **Graph Neural Network (GNN)** pooling technique based on **edge cuts**, designed to enhance graph-based machine learning tasks such as graph classification and node classification.

Graph Neural Networks are a class of neural networks designed to work with structured data represented as graphs. They extend the concept of convolutional neural networks (CNNs) to non-Euclidean data. Pooling in GNNs helps reduce graph size while preserving important structural features, which is essential for hierarchical learning and classification tasks.

This work addresses the challenges of designing a pooling layer for irregular, unordered graph structures by proposing an **edge-based pooling layer**.

## **Objective**
To develop a GNN pooling layer that:
- Clusters nodes based on graph topology without needing a predefined number of clusters.
- Optimizes the **minCUT problem** to identify meaningful communities within graphs.
- Achieves competitive or superior performance compared to state-of-the-art methods in tasks like graph and node classification.

## **Methodology**

### **Pooling by Edge Cuts**
- **Edge Scoring**: Assigns importance scores to edges based on node features and their relationships.
- **Edge Cutting**: Removes edges with the lowest scores to separate the graph into connected components. Each component becomes a "super node" in the pooled graph.
- **Regularization**: Incorporates a term that minimizes the **Normalized Cut (Ncut)**, ensuring edges are removed consistently with the graph's topology.

##**Graph Neural Network Architecture**
The pooling layer was integrated into a GNN pipeline that performs:
1. **Graph Convolution**: Propagates information across nodes.
2. **Edge Scoring and Cutting**: Identifies less informative edges for removal.
3. **Super Node Creation**: Groups nodes into communities based on the remaining graph structure.

## **Applications**
### **Graph Classification**
- **Datasets**:
  - Bioinformatics datasets: PROTEINS, D&D.
  - Social network dataset: COLLAB.
- **Setup**:
  - 10-fold cross-validation with an 8:1:1 split (train, validation, test).
  - Comparison with state-of-the-art methods, including Gao & Ji (2019) and Ying et al. (2018).
- **Results**:
  - Competitive performance on COLLAB.
  - Outperforms Ying et al. (2018) on bioinformatics datasets.

### **Node Classification**
- **Datasets**:
  - Citation networks: Cora, Citeseer, and PubMed.
- **Setup**:
  - Split edges into training, validation, and test sets.
  - Evaluated using Graph U-Net architecture (Gao & Ji, 2019).
- **Results**:
  - Improved accuracy with the regularization term.



## **Key Features**
- **Edge-Based Pooling**:
  - Focuses on edges rather than nodes for clustering.
  - Avoids the need for predefined cluster sizes.
- **Regularization**:
  - Enhances consistency of edge scoring and removal.
  - Solves the **minCUT** problem effectively.
- **State-of-the-Art Performance**:
  - Competes with leading GNN methods across benchmark datasets.


## **Experimental Results**
### **Graph Classification Accuracy**  
| Dataset       | Our Model | Gao & Ji (2019) | Ying et al. (2018) |
|---------------|-----------|-----------------|--------------------|
| D&D           | 80.33%   | 82.43%          | 80.64%            |
| PROTEINS      | 76.42%   | 77.68%          | 76.25%            |
| COLLAB        | 77.23%   | 77.56%          | 75.48%            |

### **Node Classification Accuracy**  
| Dataset       | Without Regularization | With Regularization |
|---------------|------------------------|---------------------|
| Cora          | 81.9%                 | 82.3%              |
| Citeseer      | 69.8%                 | 70.9%              |
| PubMed        | 78.7%                 | 79.1%              |


## **Supplementary Material**
Presentation
The project presentation is included in this repository: Graph_Pooling_Edge_Cut.pptx.

Article
The research article is included in this repository: Graph_Pooling_Edge_Cut.pdf.


## **Conclusion**
This project introduced a novel edge-based pooling technique for graph neural networks that effectively clusters nodes by cutting edges with minimal importance. The method was benchmarked against state-of-the-art techniques, demonstrating its competitive performance and potential for solving graph-related machine-learning tasks.


## **Acknowledgments**
This project was conducted as part of engineering studies and reflects a collaborative effort to explore advanced topics in machine learning and graph analysis.


