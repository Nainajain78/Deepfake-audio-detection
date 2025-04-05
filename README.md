# Deepfake-audio-detection

#Objectives 
1. Capable of identifying AI-generated human speech.  
2. Real-time or near real-time performance for deployment.  
3. Ability to analyze real, spontaneous conversations.

 **Approach 1 – Wav2Vec 2.0**  
**Key Technical Innovation:**  
Wav2Vec 2.0 uses self-supervised learning to extract powerful representations directly from raw audio. It uses contrastive loss to learn contextualized features without needing labeled data.

**Performance Metrics:**  
Achieves over 95% Area Under the Curve (AUC) on the ASVspoof 2019 LA dataset.

**Why Promising:**  
- Learns rich, speaker- and context-aware representations.  
- Performs well without requiring handcrafted features.  
- Effective across various spoofing techniques, even unknown ones.

**Potential Limitations:**  
- High computational cost for training and inference.  
- Requires fine-tuning on domain-specific data like real conversations.



**Approach 2 – CNN-based Models (RawNet, LCNN)**  
**Key Technical Innovation:**  
These models use deep convolutional neural networks trained directly on audio spectrograms or raw waveforms to classify between real and fake speech signals.

**Performance Metrics:**  
Equal Error Rate (EER) in the range of 1.5% to 3% on ASVspoof 2019 LA challenge.

**Why Promising:**  
- Highly efficient during inference; ideal for real-time detection.  
- Lightweight models can be deployed on mobile or edge devices.  
- Strong performance on known spoofing techniques.

**Potential Limitations:**  
- May not generalize well to new or unknown spoof types.  
- Requires augmentation techniques to improve robustness.

**Approach 3 – SpecRNet (CNN + RNN Hybrid)**  
**Key Technical Innovation:**  
SpecRNet integrates convolutional layers for spatial/spectral features with recurrent layers (LSTMs) to model temporal dependencies and speech dynamics in spectrograms.

**Performance Metrics:**  
Demonstrated AUC greater than 94% across multiple spoofing attacks and datasets.

**Why Promising:**  
- Captures both local audio features and long-term dependencies.  
- Effective for natural, flowing speech and real conversations.  
- Suitable for longer audio sequences and conversational detection.

**Potential Limitations:**  
- Recurrent layers make it computationally slower.  
- Requires preprocessing of audio into fixed-length segments.


