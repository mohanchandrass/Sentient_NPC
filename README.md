# Sentient_NPC  
### Lightweight Offline Voice-Interactive NPC Dialogue Framework

---

## Overview

**Sentient_NPC** is a fully offline, real-time **voice-interactive NPC dialogue system** designed to enhance immersion in open-world and role-playing games.  
The framework allows players to communicate with NPCs using natural speech and receive coherent, lore-consistent spoken responses without relying on any cloud-based services.

The system integrates:
- Offline **Speech-to-Text (STT)** using Vosk  
- A **Transformer-based dialogue generation model** trained on Skyrim-style NPC–player conversations  
- Offline **Text-to-Speech (TTS)** using Silero  

This project demonstrates that **compact, domain-trained Transformer models** can outperform larger pretrained language models in low-latency, game-specific dialogue tasks.

---

## Key Features

- Fully **offline** inference (no internet dependency)
- Real-time **voice-driven NPC interaction**
- Lightweight Transformer model (~30 MB)
- Domain-specific training for lore consistency
- Modular and extensible architecture
- Suitable for on-device and edge deployment
- Low-latency response generation

---

## System Architecture

```
Player Speech
     ↓
Offline Speech-to-Text (Vosk)
     ↓
Transformer-based NPC Dialogue Model
     ↓
Offline Text-to-Speech (Silero)
     ↓
NPC Spoken Response
```

---

## Installation

```bash
git clone https://github.com/mohanchandrass/Sentient_NPC.git
cd Sentient_NPC
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

## Usage

```bash
python main.py
```

---

## Authors

- Mohan Chandra S S  
- Mohith R  
- Nithish Gowda H N  


---

## License

Academic and research use only.
