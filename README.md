# Fake or Real: The Impostor Hunt in Texts

##  Competition Overview

This project is based on the **"Fake or Real: The Impostor Hunt in Texts"** Kaggle competition from [https://www.kaggle.com/competitions/fake-or-real-the-impostor-hunt/data](https://www.kaggle.com/competitions/fake-or-real-the-impostor-hunt/data).

###  Challenge Description
The competition focused on document authenticity classification, where participants had to determine which of two text documents was real and which was fake. This is a challenging NLP task that requires sophisticated text understanding and classification capabilities.

###  Competition Results
- **Final Ranking**: 155-160 out of 671 participants
- **Performance**: Close to top 20% mark
- **Competition Type**: Prize competition with prepared participants
  

###  Context & Achievement
While this result places us in the middle tier, it's important to note that:
- This was a **prize competition** with more serious, prepared participants
- The result is close to the top 20% threshold

For comparison, in the more popular "Titanic - Machine Learning from Disaster" competition, I achieved a result among the top 10%. However, the Titanic competition was significantly less challenging compared to this NLP task.

### Technical Approach

### Model Architecture
The solution implements an **Improved DistilBERT + TextRCNN** architecture:

- **DistilBERT**: Lightweight, distilled version maintaining 97% of BERT's performance
- **TextRCNN**: Enhanced architecture combining:
  - Bidirectional LSTM (3 layers) for sequential text processing
  - Multi-scale CNN (3x3, 5x5, 7x7 kernels) for local feature extraction
  - Multi-head attention (12 heads) for capturing complex relationships
  - Residual connections with layer normalization

###  Training Strategy
- **Progressive Unfreezing**: BERT frozen initially, unfrozen after 4 epochs
- **Advanced Optimization**: AdamW optimizer with cosine annealing scheduler
- **Early Stopping**: Patience-based stopping with validation monitoring


## Setup & Installation

### Prerequisites
- Python 3.8+
- 8GB+ RAM (recommended)
- GPU support (optional, but recommended for faster training)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Fake-or-Real-The-Impostor-Hunt-in-Texts-main
   ```

2. **Create virtual environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install torch torchvision torchaudio
   pip install transformers
   pip install pandas numpy scikit-learn
   pip install matplotlib seaborn jupyter
   pip install nltk textblob wordcloud
   ```

4. **Download data locally** 
   - Extract to `train/` and `test/` directories
   - Ensure `train.csv` is in the root directory
   - Dataset contains 1000+ articles




