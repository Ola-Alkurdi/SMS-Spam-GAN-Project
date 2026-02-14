📩 SMS Spam Detection with GAN-based Data Augmentation
📌 Project Overview

This project addresses the class imbalance problem in the SMS Spam Collection Dataset using Generative Adversarial Networks (GANs).

The dataset contains significantly more ham messages than spam messages, which can cause classification bias.
To solve this, we generated synthetic spam samples using:

✅ Vanilla GAN

✅ Conditional GAN (CGAN)

We then evaluated the performance of an MLP classifier under three different scenarios.

📊 Dataset Information

Dataset: SMS Spam Collection

Total Messages: 5,572

Ham: 4,825

Spam: 747

The dataset is clearly imbalanced, with spam representing a small minority of the data.

🧠 GAN Architectures
1️⃣ Vanilla GAN

Generator: 2 Dense layers (64 units + sigmoid)

Discriminator: 2 Dense layers (64 units + sigmoid)

Loss: Binary Crossentropy

Optimizer: Adam

The generator produces synthetic spam messages from a noise vector.

2️⃣ Conditional GAN (CGAN)

Generator: 2 Dense layers (128 units + sigmoid)

Discriminator: 2 Dense layers (128 units + sigmoid)

Conditioned on class label

CGAN improves generation quality by incorporating label information.

⚙️ Training Setup
Hyperparameter	Value
Batch Size	32
Learning Rate	0.0002
Epochs	1000
Optimizer	Adam
Loss Function	Binary Crossentropy

Text data was converted into TF-IDF feature representations before training.

🧪 Experimental Scenarios

We trained an MLP classifier under three conditions:

Original Imbalanced Dataset

Dataset Balanced using Vanilla GAN

Dataset Balanced using Conditional GAN

Evaluation metrics:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

📈 Results
Scenario	Accuracy	Precision	Recall	F1
Original Imbalanced	0.9910	0.9929	0.9396	0.9655
Vanilla GAN Balanced	1.0000	1.0000	1.0000	1.0000
CGAN Balanced	1.0000	1.0000	1.0000	1.0000
🔎 Key Observation

The original dataset had lower recall (93.96%), meaning some spam messages were misclassified.

After GAN-based augmentation, the classifier achieved perfect performance across all metrics.

🧩 Conclusion

GANs are effective tools for handling imbalanced classification problems.

Both Vanilla GAN and CGAN significantly improved classifier performance.

Synthetic spam samples enhanced dataset balance and learning quality.

🚀 Future Work

Experiment with WGAN or LSGAN

Use more advanced classifiers

Evaluate on real-world spam datasets

🛠 Technologies Used

Python

TensorFlow / Keras

Scikit-learn

TF-IDF

MLP Classifier
