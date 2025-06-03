Here is a `README.md` file for your project, written to be informative and professional:

---

# 🎧 Signal Denoising with Random Forest, CNN, and Adaptive Ensemble

This project demonstrates a hybrid approach to denoising 1D sinusoidal signals corrupted with Gaussian noise using **Machine Learning** techniques. We leverage both **Random Forest Regression** and a **Convolutional Neural Network (CNN)**, and further enhance performance via an **adaptive ensemble** method based on per-sample error weighting.

---

## 📌 Project Overview

### Objective

To denoise a synthetic sinusoidal signal contaminated with white noise using machine learning methods and compare their effectiveness both individually and in combination.

### Key Components

* **Signal Generation**: A 50 Hz sine wave is created and corrupted with Gaussian noise.
* **Denoising Models**:

  * **Random Forest Regressor**: A classical ensemble learning method optimized using Optuna.
  * **CNN (1D Convolutional Neural Network)**: Designed to capture temporal patterns in noisy signal windows. Optimized using Optuna with parameters like number of filters and learning rate.
* **Adaptive Ensemble**: Combines the predictions of RF and CNN dynamically based on their respective prediction errors for each sample.
* **Performance Metric**: Signal-to-Noise Ratio (SNR) is used to evaluate the quality of denoising.

---

## 🛠️ Methods and Technologies

* **Python**, **NumPy**, **Matplotlib** for data manipulation and visualization.
* **Scikit-learn** for traditional ML models and data splitting.
* **PyTorch** for deep learning-based denoising.
* **Optuna** for efficient hyperparameter optimization of both RF and CNN models.

---

## 🚀 How It Works

1. **Windowing**: The noisy signal is split into overlapping windows of 256 samples with a stride of 128.
2. **Model Training**:

   * Random Forest and CNN are trained on these windowed segments.
   * Hyperparameters are optimized using Optuna to minimize Mean Squared Error (MSE) on a test split.
3. **Reconstruction**:

   * The full denoised signal is reconstructed by averaging overlapping predicted windows.
4. **Adaptive Ensemble**:

   * For each time point, the model (RF or CNN) with lower absolute error gets a higher weight in the final prediction.

---

## 📊 Results and Outputs

The performance of each model is evaluated using SNR:

```
SNR RF: 4.95 dB, SNR CNN: 7.06 dB, SNR Adaptive Ensemble: 6.53 dB
```

### Visualization Outputs

1. **Denoising Comparison (`denoising_comparison_optimized.png`)**
   Displays clean, noisy, RF-denoised, CNN-denoised, and ensemble-denoised signals on the full time series.

2. **Zoomed Signal View (`zoomed_signal_segment.png`)**
   Highlights a short time slice to visually inspect fine-grained differences between models.

3. **Error Comparison (`error_comparison.png`)**
   Shows the absolute error of each method over time, illustrating where each model performs better or worse.

These figures demonstrate:

* **Random Forest** performs well but lacks temporal modeling.
* **CNN** captures structure better due to local convolutional filters.
* **Adaptive Ensemble** expected to consistently outperforms either model by exploiting their complementary strengths, but failed :).

---


## ✅ Conclusion

The results show that the CNN achieved the best denoising performance with an SNR of 7.06 dB, outperforming the Random Forest model, which reached 4.95 dB. This suggests the CNN's superior ability to capture local temporal features. The Adaptive Ensemble combined both models based on their prediction errors and achieved an SNR of 6.53 dB—lower than the CNN alone, but significantly better than the Random Forest. This indicates that while adaptive weighting improves over weaker models, it may not always surpass the best individual model when one is clearly dominant in capturing signal characteristics.
