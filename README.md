
# 🎬 PhotonFlow — BeatGrid
### _Created by **Ayushman Banerjee**_

---

## 🌟 Overview

**PhotonFlow — BeatGrid** is a dynamic, audio-reactive visual enhancement engine that transforms any video into a rhythm‑synchronized motion grid.

It listens to your video's audio, detects beats, tracks movement, identifies visual features, and overlays:
- 🎵 Beat‑triggered animated squares  
- 🔗 Connection lines forming a reactive grid  
- 🧠 Motion‑aware node tracking  
- 🔎 ORB‑driven point discovery  
- 🎛️ Fully customizable visual behavior  

All written in pure **Python**, powered by **OpenCV**, **MoviePy**, and **Librosa**.

---

## ✨ Features

✅ Beat detection using `librosa`  
✅ Lucas–Kanade optical flow tracking  
✅ ORB feature‑based point spawning  
✅ Ambient/random node generation  
✅ Animated labelled squares  
✅ Grid‑style line connections  
✅ Adjustable jitter, lifetime, size, neighbors  
✅ Works on any `.mp4` video  
✅ Exports clean MP4 with sound

---

## 🚀 Getting Started

Install dependencies:

```bash
pip install -r requirements.txt
```

Basic usage:

```bash
python main.py -i myclip.mp4 -o output.mp4
```

You can place input videos in a folder like:

```
sample_data/myclip.mp4
```

and run:

```bash
python main.py -i sample_data/myclip.mp4 -o output.mp4
```

---

## ⚙️ Command Line Options

| Argument | Default | Description |
|---------|---------|-------------|
| `-i, --input` | sample video | Input video file |
| `-o, --output` | output_with_boxes.mp4 | Output video file |
| `--fps` | source fps | Override output FPS |
| `--life-frames` | 10 | Duration nodes stay alive |
| `--pts-per-beat` | 20 | Nodes spawned per beat |
| `--ambient-rate` | 5 | Random nodes/sec |
| `--jitter-px` | 0.5 | Organic jitter |
| `--min-size` | 15 | Min square size |
| `--max-size` | 40 | Max square size |
| `--neighbor-links` | 3 | Lines per node |
| `--orb-fast-threshold` | 20 | ORB sensitivity |
| `--bell-width` | 4 | Size randomness distribution |
| `--seed` | None | Reproducible randomness |
| `--log-level` | INFO | Verbosity (`DEBUG`, `INFO`, etc.) |

View full help:

```bash
python main.py -h
```

---

## 🧪 Example Visual Styles

### 🌙 Calm Minimal Mode
```bash
python main.py -i myclip.mp4 -o calm.mp4     --pts-per-beat 6 --life-frames 18     --neighbor-links 1 --jitter-px 0.25
```

### ⚡ High‑Energy Mode
```bash
python main.py -i myclip.mp4 -o hype.mp4     --pts-per-beat 28 --life-frames 8     --neighbor-links 4 --jitter-px 1.2     --min-size 12 --max-size 28
```

### 🎯 Feature‑Focused Mode
```bash
python main.py -i myclip.mp4 -o focus.mp4     --orb-fast-threshold 18 --ambient-rate 2.5
```

---

## 📂 Folder Structure

```
/
├── main.py
├── output.mp4
├── requirements.txt
├── LICENSE
└── README.md
```

---

## 🐛 Troubleshooting

**FFmpeg not found**  
Install FFmpeg and ensure it is on your PATH:  
```bash
ffmpeg -version
```

**Install errors for librosa/opencv**  
Upgrade pip:
```bash
python -m pip install --upgrade pip
```

**Visuals look too chaotic**  
Reduce:
- `--pts-per-beat`
- `--jitter-px`

Or increase:
- `--life-frames`

**Output feels slow/choppy**  
Try forcing:
```bash
--fps 30
```

---

## 📜 License
MIT License © 2025 **Ayushman Banerjee**

---

## 🙏 Credits
Designed, engineered, and documented by **Ayushman Banerjee**  
Part of the **PhotonFlow** cinematic effects suite.
