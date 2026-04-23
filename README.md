# Text Generation using Deep Neural Networks 🧠

> Advanced text generation models using LSTM and GRU neural networks

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Latest-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Models](#models)
- [Usage](#usage)
- [Datasets](#datasets)
- [Results](#results)
- [Contributing](#contributing)

---

## <a id="overview"></a>Overview

This project implements advanced text generation models using **Recurrent Neural Networks (RNNs)**. It demonstrates the application of two powerful RNN architectures:

- **LSTM** (Long Short-Term Memory) Networks
- **GRU** (Gated Recurrent Unit) Networks

These models are trained on poetry and text data to generate creative and contextually relevant text sequences.

---

## Features

<details>
<summary><b>✨ Advanced RNN Architectures</b></summary>

- **LSTM Networks**: Superior long-term dependency learning with sophisticated gating mechanisms
- **GRU Networks**: Simplified gating mechanism with reduced computational overhead
- **Bidirectional Processing**: Improved context understanding
- **Sequence-to-Sequence Learning**: Character or word-level text generation

</details>

<details>
<summary><b>📊 Comprehensive Datasets</b></summary>

- Poetry collection data (poems.csv)
- General training data (train.csv)
- Custom data loading and preprocessing
- Automatic tokenization and encoding

</details>

<details>
<summary><b>🛠️ Complete Pipeline</b></summary>

- Data preprocessing and normalization
- Model training with validation
- Text generation with temperature control
- Performance evaluation metrics

</details>

---

## <a id="project-structure"></a>Project Structure

```
📁 Text Generation using Deep Neural Networks/
│
├── 📓 LSTM_Text_Generation.ipynb          # LSTM-based text generation model
├── 📓 GRU_Text_Generation.ipynb           # GRU-based text generation model
├── 📓 Text Generation using GRU Networks.ipynb
│
├── 📊 Data Files
│   ├── poems.csv                          # Poetry dataset
│   ├── train.csv                          # Training dataset
│   └── data.csv                           # Additional data
│
├── 📝 requirements.txt                    # Python dependencies
├── 📖 README.md                           # This file
│
└── 📂 Output/                             # Generated models & results
    ├── trained_models/
    └── generated_text/
```

---

## <a id="installation"></a>Installation

<details>
<summary><b>Step 1: Clone or Download the Repository</b></summary>

```bash
git clone https://github.com/itsluckysharma01/Text-Generation-using-Deep-Neural-Networks.git
cd "Text Generation using Recurrent Long Short Term Memory Network"
```

</details>

<details>
<summary><b>Step 2: Create a Virtual Environment</b></summary>

```bash
# Using Python 3.7+
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

</details>

<details>
<summary><b>Step 3: Install Dependencies</b></summary>

```bash
pip install -r requirements.txt
```

**Required Packages:**

- `tensorflow` - Deep learning framework
- `numpy` - Numerical computing
- `pandas` - Data manipulation
- `matplotlib` - Data visualization

</details>

---

## <a id="models"></a>Models

### LSTM (Long Short-Term Memory)

<details>
<summary><b>Architecture Details</b></summary>

**Strengths:**

- ✅ Excellent for learning long-range dependencies
- ✅ Multiple gating mechanisms (input, output, forget)
- ✅ Robust gradient flow during backpropagation
- ✅ State-of-the-art performance on sequence tasks

**Parameters:**

- Input Shape: (sequence_length, vocabulary_size)
- Hidden Units: 128-256 (configurable)
- Dropout: 0.2-0.3 for regularization
- Output: Softmax probability distribution

**Training:**

- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Batch Size: 32-64
- Epochs: 50-100

</details>

### GRU (Gated Recurrent Unit)

<details>
<summary><b>Architecture Details</b></summary>

**Strengths:**

- ✅ Simpler than LSTM with fewer parameters
- ✅ Faster training time
- ✅ Similar performance to LSTM on many tasks
- ✅ Reduced computational overhead

**Parameters:**

- Input Shape: (sequence_length, vocabulary_size)
- Hidden Units: 128-256 (configurable)
- Dropout: 0.2-0.3 for regularization
- Output: Softmax probability distribution

**Training:**

- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Batch Size: 32-64
- Epochs: 50-100

</details>

---

## <a id="usage"></a>Usage

<details>
<summary><b>Running LSTM Text Generation</b></summary>

1. **Open the notebook:**

   ```
   LSTM_Text_Generation.ipynb
   ```

2. **Execute cells in order:**
   - Load and preprocess data
   - Build LSTM model
   - Train the model
   - Generate text

3. **Generate text with custom seeds:**
   ```python
   # Set starting text
   seed_text = "The night"
   # Model will predict next characters/words
   generated_text = model.generate(seed_text, length=100)
   print(generated_text)
   ```

</details>

<details>
<summary><b>Running GRU Text Generation</b></summary>

1. **Open the notebook:**

   ```
   GRU_Text_Generation.ipynb
   ```

2. **Execute cells in order:**
   - Load and preprocess data
   - Build GRU model
   - Train the model
   - Generate text

3. **Generate text with temperature control:**
   ```python
   # Lower temperature = more deterministic
   # Higher temperature = more creative
   generated_text = model.generate(seed_text, length=100, temperature=0.7)
   ```

</details>

<details>
<summary><b>Comparing LSTM vs GRU</b></summary>

Run both notebooks and compare:

- **Training time**: GRU typically faster
- **Model size**: GRU uses fewer parameters
- **Accuracy**: LSTM often slightly better
- **Text quality**: Similar overall, varies by dataset

</details>

---

## <a id="datasets"></a>Datasets

| Dataset           | File        | Purpose                 | Format               |
| ----------------- | ----------- | ----------------------- | -------------------- |
| Poetry Collection | `poems.csv` | Train on poetic text    | CSV with text column |
| Training Data     | `train.csv` | General text generation | CSV format           |
| Custom Data       | `data.csv`  | Additional training     | CSV format           |

**Data Preprocessing:**

- Remove special characters
- Convert to lowercase
- Tokenize into characters/words
- Create sequences with sliding window
- Normalize input ranges

---

## <a id="results"></a>Results

<details>
<summary><b>Expected Performance Metrics</b></summary>

**Training Metrics:**

- Loss convergence over epochs
- Validation accuracy improvement
- Character/word-level perplexity

**Text Generation Quality:**

- Coherent sentence generation
- Contextually relevant predictions
- Diversity in generated text (with temperature)

**Comparison:**

```
┌──────────────┬───────────┬──────────┐
│    Metric    │   LSTM    │   GRU    │
├──────────────┼───────────┼──────────┤
│ Training Time│   ~2hrs   │  ~1.5hrs │
│ Accuracy     │   85-90%  │  80-85%  │
│ Parameters   │   256K+   │   150K+  │
└──────────────┴───────────┴──────────┘
```

</details>

---

## <a id="contributing"></a>Contributing

We welcome contributions! Here's how:

<details>
<summary><b>Steps to Contribute</b></summary>

1. **Fork the repository**
2. **Create a feature branch:**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes** and commit:
   ```bash
   git commit -m "Add amazing feature"
   ```
4. **Push to branch:**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

</details>

<details>
<summary><b>Contribution Ideas</b></summary>

- 🎯 Add attention mechanisms
- 🔧 Implement bidirectional models
- 📈 Experiment with transformer architectures
- 🎨 Enhance text generation quality
- 📚 Add more datasets
- 🧪 Implement evaluation metrics
- 📖 Improve documentation

</details>

---

## 📞 Support & Questions

- **Issues**: Report bugs via GitHub Issues
- **Discussions**: Use GitHub Discussions for questions
- **Documentation**: See individual notebooks for detailed comments

---

## 📜 License

This project is licensed under the MIT License - see LICENSE file for details.

---

## 🙏 Acknowledgments

- TensorFlow/Keras documentation
- Deep Learning community
- Poetry dataset contributors

---

<div align="center">

**Made with ❤️ by the Deep Learning Community**

⭐ If this project helped you, please give it a star!

</div>
