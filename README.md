# Voice Conditioning TTS

Silk-inspired expressive TTS prototype using speaker conditioning and prompt-based emotion control.

---

## 1. Objective

The goal of this work was to explore how expressive and conversational speech can be generated using pretrained voice models, inspired by Silk's approach to human-like AI voice systems. Instead of training a model from scratch, the focus was on rapid experimentation using lightweight techniques to understand:

- Voice adaptation
- Emotional expression
- Conversational tone
- Code-switching (Hinglish)

---

## 2. Model Choice

For this experiment, **Coqui TTS (XTTS v2)** was used.

**Reason for choosing this model:**

- Supports voice cloning from very small audio samples
- Works without heavy training or fine-tuning
- Multilingual support (useful for Hinglish)
- Easy to experiment with in a short time

This made it suitable for quick prototyping and testing ideas, which aligns with the goal of fast iteration.

---

## 3. Approach

Instead of full fine-tuning, the following techniques were used:

### 3.1 Speaker Conditioning

Provided short audio clips (2–3 minutes total), each representing a distinct tone:

| Clip | Tone |
|------|------|
| 1 | Calm |
| 2 | Excited |
| 3 | Whisper |
| 4 | Hinglish |

The model uses these clips as reference inputs to adapt its output voice.

### 3.2 Prompt-Based Control

Emotion was simulated using:

- Punctuation (`!!!`, `...`)
- Conversational phrasing
- Informal expressions (e.g., *"bro"*, *"yaar"*)

### 3.3 Experiments Conducted

1. **Emotion-based generation** — Different audio samples → different tone
2. **Text-based variation** — Same voice → different emotional prompts
3. **Code-switching test** — Hinglish input → evaluate output behavior

---

## 4. Experimental Results

Overall, the results were inconsistent and often poor, especially for expressive speech.

### 4.1 Calm Speech

- Output was relatively stable
- Speech sounded understandable
- Tone was slightly flat

> Calm speech aligns more closely with how models are trained (neutral datasets).

### 4.2 Excited Speech

- Output lacked real energy
- Sometimes sounded unnatural or exaggerated

Emotion like excitement requires training-time supervision and better prosody modeling. Prompt-based control alone was insufficient.

### 4.3 Whisper / Soft Tone

- Model failed to produce a true whisper effect
- Output remained similar to normal speech

> Whispering is a voice characteristic, not just a text variation. It requires specific training data and acoustic modeling.

### 4.4 Hinglish / Code-Switching

- Output was inconsistent
- Pronunciation issues observed
- Flow between languages felt unnatural

Current TTS models are not optimized for mixed-language inputs and are trained mostly on single-language datasets.

### 4.5 Voice Similarity

- Voice resemblance was partial but not strong
- Better results were observed with cleaner audio and neutral tone samples

**Limiting factors:**
- Very small dataset (2–3 minutes)
- No fine-tuning
- Accent mismatch with training data

---

## 5. Key Insights

From these experiments:

- **Speaker conditioning** is useful for quick adaptation, but limited in quality
- **Emotion** cannot be effectively controlled using text alone
- **Expressive speech** requires training-time modeling, not just inference tricks
- **Code-switching** remains a challenging open problem in TTS
- **Realistic conversational speech** involves timing, pauses, and tone variation — not just text input

---

## 6. Conclusion

This work highlights the gap between current TTS systems and truly expressive, human-like speech. While the outputs were not high-quality, the experiments helped in understanding:

- Limitations of current models
- Importance of data and training strategies
- Challenges in building conversational voice systems
