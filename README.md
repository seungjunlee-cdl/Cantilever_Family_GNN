# Cantilever_Family_GNN_with_intermediate

### Flow
![flow](https://user-images.githubusercontent.com/56711947/149752304-91036140-2b30-4a33-9503-1f31483317d0.jpg)  

### Data preprocessing
1. Save all the sequence of topology optimization  
2. Pick intermediate material density (Criteria -> Cumulative sum of material density change > 1st iteration material density change)  
3. Build dataset with each number of saved intermediate sequence  
![data preprocessign](https://user-images.githubusercontent.com/56711947/149754354-1318eb3a-70db-4fb4-b1ca-154943aabdda.jpg)

### Input & output node features
Input node features  
1. 1st iteration displacement of topology optimization  
2. 1st iteration stress of topology optimization  
3. Specific intermediate material density  

Output node features
1. Next sequence of input material density
![input and output](https://user-images.githubusercontent.com/56711947/149757542-1ec724e9-6b1e-4ba4-8a19-af8fc4816957.jpg)

### Model architecture
19 graph attention layer with batch normalization, dropout and L2 regularization  
Used residual connection in hidden node features  
![model](https://user-images.githubusercontent.com/56711947/149758267-ea8a01a1-defa-418c-8e96-bcc87105479c.jpg)

### Results
Recursive process is needed to get optimal topology prediction with trained model  
![recursive](https://user-images.githubusercontent.com/56711947/149759038-c2e0afbb-6b36-4391-97a3-d2192d9a5a0a.jpg)  
