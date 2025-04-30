# OS_projerct-Antony2008
# 💻 Sentiment Prediction with RAM Swapping Simulation

This project combines machine learning (sentiment analysis) with a simulated RAM management system inspired by operating system memory swapping techniques. Each user input (a movie review) is treated as a process that consumes memory. When RAM fills up, the system automatically swaps out old processes using FIFO or LRU policies.

---

## 🎯 Objective

- Simulate OS memory behavior using a real-world task: sentiment prediction.
- Use process swapping techniques (FIFO & LRU) to manage limited RAM.
- Visualize and log how reviews (processes) are loaded, swapped, and predicted.

---

## 🧠 Features

- Predicts if a movie review is positive or negative.
- Each review acts as a simulated process with memory size based on text length.
- RAM limit triggers swap-out when memory is full.
- Supports FIFO and LRU swapping policies.
- Visual pie chart shows real-time RAM usage.
- All events are logged to `prediction_log.txt`.
- User interaction via a text input widget in Google Colab.

---

## 🛠 Technologies Used

- Python (Colab)
- scikit-learn (TF-IDF, Logistic Regression)
- Matplotlib (pie chart visualization)
- ipywidgets (user input)
- Custom-built RAM simulator and process classes

---

## 🔁 How It Works

1. The ML model is trained on IMDB movie reviews (positive/negative).
2. A user types a review into the input widget.
3. The system simulates loading it into RAM as a "process".
4. If memory is full, an old process is swapped out based on FIFO or LRU.
5. The review is processed, sentiment is predicted, and memory is visualized.

---

## 📁 Log File: `prediction_log.txt`

Each entry includes:

- Process ID
- Process size (based on text length)
- Memory usage before/after
- Swapped or loaded event
- Sentiment prediction result

Example:

```
Loaded: PID=1, Size=257, RAM used=257/2048
Swapped out: PID=1, Size=257, RAM used=510/2048
PID: 2, Text size: 400, Sentiment: positive
```

---

## 🧪 Swap Policies

| Policy | Description |
|--------|-------------|
| FIFO   | Evicts the oldest process first (First-In, First-Out). |
| LRU    | Evicts the least recently used process based on timestamp. |

Change this in the simulator:
```python
sim = RamSimulator(max_ram=2048, policy="LRU")
```

---

## 🛠 Customization

| Setting             | Description                                |
|---------------------|--------------------------------------------|
| `max_ram`           | Max simulated RAM (e.g., 1024, 2048)        |
| `max_predictions`   | Number of allowed predictions before stop   |
| `policy`            | Set to "FIFO" or "LRU"                      |

---

## 📚 Educational Relevance

This project is ideal for teaching or demonstrating:
- Core OS memory management (RAM pressure, swapping)
- Process management and scheduling
- Applied machine learning
- Resource constraints in real-world applications (e.g., mobile, embedded AI)

---

## ✅ Example Output (Screenshot or Chart)

![RAM Pie Chart Example](link_to_image_if_applicable)

---

## 👨‍💻 Authors

- Built in Google Colab as an OS + ML integrated demo.
- Inspired by real-world OS memory paging and educational visualizations.
