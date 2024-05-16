# PatchTST-Re-Implementation

## Introduction

The paper titled "A Time Series is Worth 64 Words: Long-term Forecasting with Transformers" by Yuqi Nie, Nam H. Nguyen, Phanwadee Sinthong, and Jayant Kalagnanam, presented a novel approach for long-term time series forecasting using transformers with patching. This re-implementation effort aims to replicate the results presented in the paper and provide insights into the performance and challenges encountered during the process.

### Main Methods

- **Channel-independence**: The assumption that channels (features) are independent of each other is leveraged. Channels are separated and individually passed through the transformer backbone, and the outputs are concatenated.
- **Patching**: The input sequence is divided into small patches, similar to 1D convolution. Hyperparameters such as patch size, stride, and padding are utilized.

### Main Contribution

The main contribution of the paper includes:

- Outperforming other transformer-based models and popular non-transformer-based methods on supervised, self-supervised, and unsupervised time series forecasting tasks.
- Exhibiting the potential to be the base model for future work of Transformer-based forecasting.

## Chosen Result

### Datasets

We used the ETTH1, Weather and ILI datasets for supervised training, sourced from `data/Etth1.csv`, `data/weather.csv` and `data/Illness.csv`, respectively. These datasets have already been preprocessed and are publicly accessible.

### Evaluation Metrics

We evaluate our re-implemented models using testing Mean Squared Error (MSE) and Mean Absolute Error (MAE) losses, similar to the evaluation metrics used in the paper. The absolute difference between our losses and the paper’s losses will be calculated for comparison.

## Model Architecture

According to the architecture stated in the paper, we use a transformer encoder, instance norm, patching, position embedding, and MLP layers. Our implementation follows the Transformer Backbone architecture as described in the paper, respecting channel-independence. The Transformer Encoder is mostly vanilla with a few modifications, including Reversible Instance Normalization (RevIN), BatchNorm instead of LayerNorm in Multi-head Attention, and GELU instead of RELU in the feed-forward layer. Many dropout layers are used for regularization.

### Instructions for Running the Code

1. Clone the repository.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Download the datasets mentioned in the paper and place them in the specified directories.
4. Run the training script with appropriate arguments to train the models.
5. Evaluate the trained models using the provided evaluation script.

### Computational Resources

## Results and Analysis

### Re-implementation Results

### Discrepancies and Challenges


### Analysis


## Conclusion and Future Work

### Key Takeaways

### Future Directions

## References
