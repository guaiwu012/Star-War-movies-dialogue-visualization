# 🌌 Star Wars Dialogue Visualization Dashboard

An **interactive data visualization app** built with **Python, Dash, and Cytoscape**, visualizing the **conversation networks**, **character sentiments**, and **speaking frequencies** across the *Star Wars Original Trilogy* (Episodes IV–VI).

这是一款基于 **Python + Dash + Cytoscape** 的交互式数据可视化应用，用于展示《星球大战》原始三部曲中角色间的对话关系、情绪变化以及台词数量分布。

---

## 🚀 Features | 功能特点

✅ **Dynamic Dialogue Network**
- Each node represents a **character**.
- Each edge represents a **conversation connection**.
- **Edge thickness** corresponds to the **number of dialogues**.
- **Node border colors** reflect character **factions** (阵营颜色从 `nodes.csv` 读取)。
- **Character names** only appear when hovering for clarity.

✅ **Interactive Controls**
- Dropdown menu allows switching between:
  - “All (Trilogy)”
  - Individual movies (`Star Wars`, `The Empire Strikes Back`, `Return of the Jedi`)
- When a movie is selected, the graph and bar chart update instantly.

✅ **Character Sentiment Analysis**
- Click any character node to view:
  - **Sentiment pie chart** (positive / neutral / negative)
  - **Rolling sentiment timeline** (emotion trends by dialogue order)

✅ **Line Count Statistics**
- Bottom bar chart shows **top 20 characters by number of lines** for the selected movie.

✅ **Faction Legend**
- Top-right legend shows each **faction color mapping** and edge meaning.

---

## 🗂 Directory Structure | 目录结构

proj/
├─ assets/
│ ├─ avatars/ # Character avatar images (.png)
│ └─ style.css # (Optional) custom CSS for future design
│
├─ starwars_core/
│ ├─ sw_lines.csv # Character dialogue lines (used for sentiment & counts)
│ ├─ sw_movies.csv # Movie titles & metadata (used for dropdown)
│
├─ starwars_filtered/
│ ├─ edges_total.csv # Conversation edges (weights = dialogue counts)
│ ├─ edges_time.csv # (Optional) time-based edges (for future animation)
│ ├─ nodes.csv # Node attributes (character, faction, avatar)
│
├─ process.ipynb # Main notebook (run this to start the Dash app)
├─ requirements.txt # Python environment dependencies
└─ README.md # Project documentation (this file)


---

## ⚙️ Setup & Run | 环境配置与运行

### 1️⃣ Create and activate a virtual environment
```bash
conda create -n starwars-net python=3.11
conda activate starwars-net

### 2️⃣ Install dependencies
```bash
pip install -r requirements.txt

### 3️⃣ Launch the dashboard

Open process.ipynb in VS Code or Jupyter Notebook, then run all cells.
The console will display a local address, e.g.: Running at http://127.0.0.1:8050
Click or open this link in your browser.

## Data Sources | 数据来源
Cornell Movie Dialogs Corpus – base script & conversation data.

Filtered data (starwars_filtered/ & starwars_core/) were preprocessed for clarity and consistency.

Factions are read from nodes.csv (uploaded version).

Movie titles are read from starwars_core/sw_movies.csv
