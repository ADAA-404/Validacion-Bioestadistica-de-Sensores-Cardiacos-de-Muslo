[Versión en Español](README.md)

# Biostatistical Validation of Thigh Cardiac Sensors 🦵🫀
This biostatistics and data science project presents a comprehensive pipeline for validating a heart rate measurement device based on thigh sensors. Through rigorous concordance analysis, it evaluates whether this experimental method can be a viable substitute for the clinical electrocardiogram (ECG), considered the “gold standard.”    

The primary objective is to demonstrate the reliability and consistency of heart rate measurements from the thigh sensor compared to those from a reference ECG device. This analysis is essential for the validation of wearable health technologies.    

## Data Source 💾

This dataset is publicly available for research. Details are described in the following citations. Important, please include this citation if you plan to use this database:

> Silva, A. S., Plácido da Silva, H., Correia, M., Gonçalves da Costa, A. C., & Laranjo, S. (2025). tOLIet: Single-lead Thigh-based Electrocardiography Using Polimeric Dry Electrodes (version 1.0.0). PhysioNet. RRID:SCR_007345. https://doi.org/10.13026/v66k-sk82

> Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P. C., Mark, R., ... & Stanley, H. E. (2000). PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation [Online]. 101 (23), pp. e215–e220. RRID:SCR_007345.

## Technologies Used 🐍
-   Pandas & NumPy: For loading, cleaning, transforming, and analyzing data. These were used to handle complex data structures and perform efficient numerical calculations.  
-   xmltodict: For correctly reading and converting XML files containing reference data into a manageable dictionary format.  
-   BioSPPy: Library specialized in physiological signal processing. It was used for heartbeat detection (rpeaks) and the extraction of key biomarkers, such as heart rate.  
-   Matplotlib & Seaborn: For the visualization of results, including the Bland-Altman plot, which is central to concordance analysis.   

## Installation Considerations ⚙️

To set up and run this project, you need the following Python libraries. It is recommended to use a virtual environment (conda or venv) to manage dependencies.     

bash  
    ```
    pip install pandas numpy matplotlib seaborn xmltodict biosppy
    ```  

## Note ⚠️
Although this type of data is managed in Excel, the format in which it is distributed does not allow everything to be clear at first glance, so a strategy (included in the script) must be considered in order to process it according to the data that is available and what is missing. Efficiency and care in starting the project is crucial so that you can carry out the necessary tests and applications.   

## Usage Example 📎

The analysis pipeline was built to process data from both devices, extract heart rate biomarkers, and finally compare their concordance, with the necessary explicit steps in the .py file.   

Reliability of the Thigh Sensor Signal: by measuring the processing success rate, we were able to extract the heart rate from the thigh sensor in 96.55% of patients. In the remaining 3.45%, the signal was too weak or noisy, which prevented the detection of heartbeats; and we could be looking at a limitation in the reliability of the sensor.   

![Tasa de éxito de procesamiento](Images/fiabilidad_sensor_muslo.png)

Biostatistical Concordance Analysis: This was performed on patients where processing was successful, and we can interpret the results using two key calculations:  
-   Bland-Altman plot: The plot revealed a significant lack of agreement between the two methods. A positive bias was identified with a mean difference of +9.19 BPM, indicating that the thigh sensor tends to overestimate heart rate. The very wide agreement limits (±43.87 BPM) show that the difference between the two measurements can be dramatically large.  
-   Lin's Concordance Coefficient (CCC). The numerical value of the concordance was extremely low, confirming the lack of agreement (0.0392). A value so close to zero indicates that the measurements of the two devices are not interchangeable at first glance, suggesting further testing and data for evaluation.  

![Matriz de Confusión del Modelo Optimizado](Images/confusion_matrix_opt.png)

![Importancia de las Características](Images/feature_importance_balanced.png)

We can say that although the thigh sensor can record a signal in most cases, it is not a viable or reliable substitute for a clinical ECG device in measuring heart rate. The lack of reliability of the processing and, more importantly, the poor agreement of the measurements only point to the importance of continuing this type of study in order to achieve an improvement that can be applied in clinical practice.  

## Contributions 🖨️

If you're interested in contributing to this project or using it independently, consider:
-   Forking the repository.
-   Creating a new branch (git checkout -b feature/your-feature).
-   Making your changes and committing them (git commit -am 'Add new feature').
-   Pushing your changes to the branch (git push origin feature/your-feature).
-   Opening a 'Pull Request'.

## License 📜

This project is under the MIT License. Refer to the LICENSE file (if applicable) for more details.
