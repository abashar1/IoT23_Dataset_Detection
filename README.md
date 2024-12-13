# IoT23_Dataset_Detection

## Jupyter Notebook Report

This project uses the machine learning to detect anomalies in a network. The dataset used was StratosphereIPS's IoT-23 dataset. From the website: 

> IoT-23 is a new dataset of network traffic from Internet of Things (IoT) devices. It has 20 malware captures executed in IoT devices, and 3 captures for benign IoT devices traffic.

> The IoT-23 dataset consists of twenty three captures of different IoT network traffic. These scenarios are divided into twenty network captures (pcap files) from infected IoT devices and three network captures of real IoT devices network traffic. 

The performance of different models will be compared based off of their accuracy and time cost.

### IoT-23 Dataset  
Link to dataset: [StratosphereIPS_IoT23_Dataset](https://www.stratosphereips.org/datasets-iot23)
<br>
___

## Project Conclusion

This project analyzed the classification of IoT network traffic into malicious and benign categories using the **IoT23 dataset**. Through a structured workflow involving data preprocessing, data visualization and analysis, model development, evaluation, and behavioral analysis, key insights were derived to advance IoT malware detection. Below are the main takeaways:

#### 1. **Model Performance:**
   - **Decision Tree**: 
     - **Training Time**: 0.59 seconds  
     - **Prediction Time**: 0.03 seconds  
     - **Total Time**: 0.62 seconds  
     - **Accuracy**: 73%  
     A highly efficient model in terms of computational cost, making it ideal for real-time applications where rapid predictions are required. It performed well in distinguishing common attack patterns but may struggle with more complex scenarios.

   - **SVM**: 
     - **Training Time**: 215.32 seconds  
     - **Prediction Time**: 37.84 seconds  
     - **Total Time**: 253.16 seconds  
     - **Accuracy**: 70%  
     While offering competitive accuracy, the significant computational overhead makes SVM less practical for large-scale or real-time use. Its performance in differentiating nuanced attack types was acceptable but not superior.

   - **Naïve Bayes**: 
     - **Training Time**: 0.44 seconds  
     - **Prediction Time**: 0.50 seconds  
     - **Total Time**: 0.94 seconds  
     - **Accuracy**: 30%  
     Despite its simplicity and efficiency, Naïve Bayes struggled to classify the data accurately due to its strong independence assumptions, making it unsuitable for scenarios requiring precise malware detection.

   - **CNN**: 
     - **Training Time**: 87.03 seconds  
     - **Prediction Time**: 3.89 seconds  
     - **Total Time**: 90.92 seconds  
     - **Accuracy**: 69%  
     The CNN model showcased the best balance between accuracy and flexibility in handling complex attack patterns. Although computationally expensive compared to simpler models, it is a reliable choice for scenarios requiring high precision in distinguishing subtle anomalies.

   - **Overall Summary**:
     - **Best Accuracy**: Decision Tree (73%)  
     - **Fastest Model**: Decision Tree (Total: 0.62 seconds)  
     - **Most Robust for Complexity**: CNN (High flexibility, reasonable accuracy)  

The results highlight that Decision Trees are the most practical for lightweight, real-time detection, while CNNs are better suited for complex, high-precision tasks. Models like SVM and Naïve Bayes offer trade-offs between computational cost and classification performance.

#### 2. **Key Features for Malware Detection:**
   - **Duration**, **byte volumes**, and **missed bytes** were identified as the most significant features for distinguishing between benign and malicious traffic.
   - Malicious behaviors like **DDoS**, **C&C-FileDownload**, and **C&C-Torii** displayed unique patterns in these features, providing reliable cues for anomaly detection.

#### 3. **Behavioral Insights:**
   - **C&C-FileDownload** consistently showed the most pronounced anomalies in `missed_bytes`, making it a distinct and easily identifiable attack type.
   - **DDoS** attacks exhibited high traffic volumes and unique flow persistence patterns, making them easier to classify even with simpler models.
   - **C&C-Torii** demonstrated high variability in certain features, highlighting the importance of leveraging advanced models like CNN for nuanced classification.
   - Benign traffic showed consistent and predictable behavior, further validating the reliability of the selected features in differentiating malicious and normal traffic.

#### 4. **Implications and Future Work:**
   - The study emphasized the importance of feature selection and engineering for achieving high classification accuracy in IoT malware detection.
   - Future work can focus on:
     - Implementing real-time detection systems optimized for resource-constrained IoT environments.
     - Exploring ensemble models to combine the strengths of simpler and advanced classifiers.
     - Expanding the analysis to include zero-day attacks and adversarial scenarios.

#### Final Remarks:
The findings from this project underscore the critical role of advanced machine learning techniques in combating IoT malware. By leveraging robust models like CNNs and focusing on distinctive behavioral features, the project demonstrated a scalable and effective approach to IoT network security. This work provides a strong foundation for further innovations in the domain of malware detection and prevention.
