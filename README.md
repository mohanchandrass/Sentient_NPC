# Sentient_NPC  
## Lightweight Offline Voice-Interactive NPC Dialogue Framework  
*A research-oriented, fully offline conversational AI system for immersive games*

---

## Project Motivation 

Modern games still rely on **static dialogue trees** or cloud-based AI services for NPC interaction.  
This project demonstrates that **domain-trained, lightweight Transformer models** can enable **real-time, voice-driven NPC conversations entirely offline**, achieving low latency, strong semantic coherence, and lore consistency.

**Sentient_NPC** bridges **AI research** and **game engineering**, making it relevant for:
- Applied ML / NLP roles
- Game AI & simulation research
- Edge AI & on-device inference
- Speech + language systems

---

## Key Contributions

- Designed a **fully offline STT → NLP → TTS pipeline**
- Built a **custom Transformer dialogue model (≈2.6M params)**
- Trained on **7,565 Skyrim-style NPC–Player dialogue pairs**
- Achieved **BERTScore-F1 ≈ 0.90** with sub-300 ms inference (excluding TTS playback)
- Released **full training notebook (`training.ipynb`)** for reproducibility

---

## System Architecture

```
Player Speech
     ↓
Offline Speech-to-Text (Vosk)
     ↓
Transformer-based Dialogue Model
     ↓
Offline Text-to-Speech (Silero)
     ↓
Spoken NPC Response
```

Entire pipeline runs **without internet access**.

---

## Model Overview

- Architecture: Encoder–Decoder Transformer
- Attention: Multi-head self + cross attention
- Training: Teacher forcing with masked loss
- Optimizer: AdamW + warmup cosine decay
- Precision: Mixed precision supported
- Inference: Greedy + Top-k sampling

**Model Size**: ~30 MB  
**Chatbot Latency**: ~245 ms  

---

## 📊 Experimental Results

### Quantitative Metrics

| Metric | Score |
|------|------|
| BLEU | 0.178 |
| ROUGE-L | 0.539 |
| METEOR | 0.424 |
| **BERTScore-F1** | **0.904** |

The compact domain-trained Transformer **outperforms fine-tuned GPT-Neo (125M)** on all metrics.

---

### 📈 Result Visualizations

> eport figures here:

```md
## Results Visualization

### Model Architecture
![Transformer Architecture](results/transformer_model.png)

### Attention Heatmap
![Attention Heatmap](results/attention_heatmap.png)

### Evaluation Metrics Comparison
![Metrics Comparison](results/metrics_table.png)
```

Place images inside a `results/` folder.

---

## 🔎 Explainable AI (XAI)

The project includes:
- Token-level probability inspection
- Attention heatmap visualization
- Decoder confidence analysis

These tools help interpret **why** the model generates a response — a strong plus for research and responsible AI.

---

## Training & Reproducibility

### Training Notebook

`training.ipynb` contains:
- Dataset preprocessing
- Vocabulary construction
- Transformer model definition
- Training loop + callbacks
- Metric computation (BLEU, ROUGE, METEOR, BERTScore)
- XAI experiments

### Quick Start (Colab)

```bash
pip install transformers datasets sacrebleu bert-score tensorflow
```

Open `training.ipynb` and run cells sequentially.

---

## Repository Structure

```
Sentient_NPC/
│
├── training.ipynb        # Full research & training pipeline
├── models/               # Saved model checkpoints
├── tokenizers/           # Serialized vocabularies
├── results/              # Plots & figures from report
├── stt/                  # Speech-to-Text (Vosk)
├── tts/                  # Text-to-Speech (Silero)
├── main.py               # End-to-end inference
├── requirements.txt
└── README.md
```

---

## Applications

- Voice-driven NPCs in RPGs
- Offline conversational agents
- Edge-device AI assistants
- Game AI research & prototyping
- Speech + NLP academic research

---

## Limitations

- Single-turn dialogue (no memory yet)
- Domain-specific (Skyrim-style)
- TTS playback dominates latency

---

## Future Work

- Multi-turn conversational memory
- NPC personality & emotion control
- Unity / Unreal Engine integration
- Reinforcement learning for adaptive dialogue
- Model compression for mobile & VR
- Multi-language NPC support

---

## Authors

- **Mohan Chandra S S**
- Mohith R  
- Nithish Gowda H N  

---

## License

Released for **academic and research purposes**.

---

> ⭐ *If this repository helped you or inspired your work, please consider starring it.*
