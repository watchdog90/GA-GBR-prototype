# GA-GBR Prototype 🏆🚀

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://g8anpj4pcwkjacgbsg5fhd.streamlit.app/)

A Gradient Boosting Regression model enhanced with Genetic Algorithm optimization for accurate property price prediction, featuring SHAP explainability and bootstrap confidence analysis.

## 🌐 Live Demo

Access the deployed application: https://g8anpj4pcwkjacgbsg5fhd.streamlit.app/

## 📊 Optimal Model Configuration

**Note on Reproducibility**: The GA search stage is an offline, compute-intensive procedure subject to institutional IP constraints. To ensure practical reproducibility, we release the frozen GA outputs (feature mask and hyperparameters) and the trained GBR pipeline. This allows anyone to train and evaluation the GA-GBR model, make predictions, and SHAP explanations with confidence interval reported in the paper without rerunning the GA.

**Based on extensive testing, the following hyperparameters provide the best performance:**

### Model Hyperparameters

- **Loss Function**: `huber` (robust to outliers)
- **Number of Boosting Trees**: `200`
- **Learning Rate**: `0.20`
- **Maximum Depth of Trees**: `5`
- **Minimum Samples in Leaf**: `3`

### Bootstrap Analysis Settings

- **Bootstrap Iterations**: `1000`
- **Confidence Level**: `0.95` (95%)
- **Enable Bootstrap Analysis for SHAP**: ✅

### Performance Metrics to Display

- ✅ MAE (Mean Absolute Error)
- ✅ MSE (Mean Squared Error)
- ✅ RMSE (Root Mean Squared Error)
- ✅ R² (Coefficient of Determination)
- ✅ MAPE (Mean Absolute Percentage Error)

## 🚀 Quick Start Guide

### Step 1: Access the Application

1. Navigate to https://g8anpj4pcwkjacgbsg5fhd.streamlit.app/
2. Wait for the app to load (may take 30-60 seconds on first launch)

### Step 2: Configure Model Parameters

1. In the sidebar

   , set the following parameters:

   - Loss function → Select **`huber`**
   - Number of boosting trees → Set to **`200`**
   - Learning rate → Slide to **`0.20`**
   - Maximum depth of trees → Set to **`5`**
   - Minimum samples in leaf → Set to **`3`**

### Step 3: Enable Bootstrap Analysis

1. Check ✅ **"Perform Bootstrap Analysis for SHAP"**
2. Set Number of Bootstrap Iterations to **`1000`**
3. Set Confidence Level to **`0.95`**

### Step 4: Select Metrics

1. Ensure all metrics are selected:
   - MAE, MSE, RMSE, R², MAPE

### Step 5: Train the Model

1. Click the **"Train and Show Metrics"** button
2. Wait for training completion (approximately 30-60 seconds)
3. Review the performance metrics displayed

### Step 6: Analyze Results

1. **Performance Metrics**: Check R², MAE, RMSE values
2. **SHAP Analysis**: Review feature importance plots
3. **Bootstrap Confidence**: Examine confidence intervals for predictions

### Step 7: Make Predictions

1. Scroll to the **"Make Predictions"** section
2. Enter property features in the input fields
3. Click **"Make Prediction"** to get the estimated price

## 🏢 Example Prediction: High-Rise Property

Try this real example with a luxury high-rise apartment:

### Property Details

Enter these values in the prediction form:

| Feature                 | Value       | Description                 |
| ----------------------- | ----------- | --------------------------- |
| **Lng**                 | `116.44233` | Longitude                   |
| **Lat**                 | `40.055139` | Latitude                    |
| **tradeTime**           | `20160911`  | Trade date                  |
| **DOM**                 | `26`        | Days on market              |
| **followers**           | `8`         | Number of followers         |
| **square**              | `199`       | Area in sqm                 |
| **livingRoom**          | `3`         | Living rooms                |
| **drawingRoom**         | `2`         | Bedrooms                    |
| **kitchen**             | `1`         | Kitchen                     |
| **bathRoom**            | `2`         | Bathrooms                   |
| **floor**               | `27`        | Floor level (high-rise)     |
| **buildingType**        | `4`         | Building type code          |
| **constructionTime**    | `2016`      | Year built                  |
| **renovationCondition** | `4`         | Renovation status           |
| **buildingStructure**   | `6`         | Structure type              |
| **ladderRatio**         | `1`         | Units per elevator          |
| **elevator**            | `1`         | Has elevator (Yes)          |
| **fiveYearsProperty**   | `0`         | Less than 5 years ownership |
| **subway**              | `1`         | Near subway (Yes)           |
| **district**            | `7`         | District code               |
| **communityAverage**    | `81544`     | Community avg price         |

### Expected Result

- **Predicted Price**: ~¥14,118,822
- **Actual Price**: ¥14,300,000
- **Accuracy**: ~98.7%

This high-rise property demonstrates the model's accuracy for luxury apartments with premium features (27th floor, elevator, subway access).

## 📈 Expected Performance Metrics

With the recommended configuration, you should expect:

| Metric   | Expected Range    | Interpretation           |
| -------- | ----------------- | ------------------------ |
| **R²**   | 0.85 - 0.92       | Excellent model fit      |
| **MAE**  | ¥15,000 - ¥25,000 | Average prediction error |
| **RMSE** | ¥20,000 - ¥35,000 | Root mean squared error  |
| **MAPE** | 5% - 10%          | Percentage error         |

## 🎯 Key Features

### 1. **GA-GBR model**

- GA optimized Ensemble learning method
- Handles non-linear relationships
- Robust to outliers with Huber loss

### 2. **SHAP Explainability**

- Feature importance visualization
- Individual prediction explanations
- Global model interpretability

### 3. **Bootstrap Confidence Analysis**

- Uncertainty quantification
- Confidence intervals for predictions
- Statistical significance testing

### 4. **Interactive Web Interface**

- Real-time model training
- Dynamic parameter adjustment
- Instant predictions

## 📊 Dataset Information

The model is trained on a comprehensive housing dataset with features including:

- **Location**: Longitude, Latitude, District
- **Property Details**: Square meters, Number of rooms, Floor level
- **Building Info**: Type, Structure, Construction year
- **Market Data**: Days on market, Community average price
- **Amenities**: Elevator, Subway proximity, Renovation condition

## 🔍 Troubleshooting

### Common Issues and Solutions

| Issue                  | Solution                                               |
| ---------------------- | ------------------------------------------------------ |
| App loads slowly       | First launch takes time to wake up (3-5 mins); subsequent loads are faster   |
| Model not found        | Click "Train and Show Metrics" to create a new model   |
| Prediction error       | Ensure all input fields are filled with valid values   |
| SHAP plots not showing | Enable bootstrap analysis and retrain                  |
| Input validation       | Use the example high-rise property values as reference |

## 📝 Usage Tips

1. **Optimal Training Time**: With 200 trees and 1000 bootstrap iterations, training takes ~45-60 seconds
2. **Feature Importance**: Focus on top 5 features shown in SHAP plots for data quality
3. **Prediction Accuracy**: Best results with complete, accurate input data
4. **Model Persistence**: Trained models are saved automatically for future use
5. **Test with Example**: Use the high-rise property example to verify model performance
6. **High-Value Properties**: Model performs exceptionally well for luxury properties (>¥10M)

5. 

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://claude.ai/chat/LICENSE) file for details.

------

⭐ **Star this repository if you find it helpful!**


🔗 **Live Application**: https://g8anpj4pcwkjacgbsg5fhd.streamlit.app/

