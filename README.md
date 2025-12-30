# 🏁 F1KYC: KnowYourChamps

<div align="center">

![f1KYC Banner](https://media.discordapp.net/attachments/758945965939359745/1455437785862504540/image.png?ex=6954b990&is=69536810&hm=2452367da3fcf2f2da495ec708b6e07051a7a725385dbe4cccfd808ecd80509f&=&format=webp&quality=lossless&width=1451&height=367)

**A Formula 1 championship prediction and simulation engine powered by real-world data.**

*Maybe reality might be different xD*

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![FastF1](https://img.shields.io/badge/Data-FastF1-red.svg)](https://docs.fastf1.dev/)
[![Status](https://img.shields.io/badge/Status-Ongoing-green.svg)]()
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

---

## 📌 What is KYC?

**KYC (KnowYourChamps)** is a Python-based analytics project that predicts:

- 🏆 **World Drivers' Championship (WDC)**
- 🏎️ **World Constructors' Championship (WCC)**

using:

- ✅ Real Formula 1 data
- ✅ Monte Carlo simulations
- ✅ Official FIA point systems
- ✅ Season-aware rules
- ✅ (Optional) live race updates

**The goal is to model how championships evolve, not just display standings.**

---

## 🏎️ Formula 1 — Explained Simply

> 📖 **New to F1?** Check out our detailed guide: [**How F1 Scores**](howf1scores.md)

### 🧍 Driver
A driver competes in races and earns points based on finishing position. Drivers compete for the **World Drivers' Championship (WDC)**.

👉 *Example: Max Verstappen*

### 🏎️ Constructor
A constructor (team) fields two drivers.
- Team points = sum of both drivers' points
- Competes for **World Constructors' Championship (WCC)**

👉 *Example: Red Bull Racing*

### 🏁 Race Weekend Types

| Type | Description |
|------|-------------|
| **Race** | Main event (25–1 points) |
| **Sprint** | Short race (8–1 points) |
| **Fastest Lap** | +1 point (removed from 2025) |

### 🧠 Championship Logic

- ✔ One race affects both WDC and WCC
- ✔ Sprint and Race handled separately
- ✔ Rules vary by season
- ✔ Simulation respects FIA scoring system

---

## 🔥 What KYC Does

### ✅ Current Features

- Build season state from real F1 data
- Simulate remaining races using Monte Carlo
- **Predict:**
  - WDC winner probability
  - WCC winner probability
- **Supports:**
  - Sprint weekends
  - Rule changes by season
  - Future-proof architecture

### 🧪 Simulation Engine

- Weighted randomness (based on current form)
- Thousands of season simulations
- Probabilistic outcome modeling
- No hardcoded results

---

## 🧰 Tech Stack

### 🧠 Core
- Python 3.10+
- Dataclasses
- OOP-based domain modeling

### 📊 Data Source
- [**FastF1**](https://docs.fastf1.dev/) → Official Formula 1 timing & standings

### 🧮 Computation
- NumPy
- Monte Carlo Simulation
- Probabilistic ranking

### 🧱 Architecture
- Modular design
- Clean separation of concerns
- No tight coupling
- Simulation-ready

---

## 📁 Project Structure

```
F1KYC/
│
├── src/
│   ├── models.py          # Core domain models
│   ├── simulation.py      # Monte Carlo engine
│   ├── data_fetching.py   # FastF1 integration
│   └── newwww.py          # Runner / entry point
│
├── cache/                 # FastF1 cache
├── howf1scores.md         # F1 scoring system explained
├── README.md              # This file
└── requirements.txt       # Dependencies
```

---

## ⚙️ How It Works

### Step 1 — Load Real Data

```python
season = build_season_state(2025)
```

### Step 2 — Run Simulations

```python
results = monte_carlo_championship(season, simulations=3000)
```

### Step 3 — Get Predictions

```
WDC:
VER → 71.2%
NOR → 18.4%
LEC → 7.1%

WCC:
Red Bull → 65.9%
McLaren → 29.3%
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10 or higher
- pip package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/biv720/kyc.git
   cd kyc
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the simulation**
   ```bash
   python src/newwww.py
   ```

### Example Usage

```python
from src.data_fetching import build_season_state
from src.simulation import monte_carlo_championship

# Load current season
season = build_season_state(2025)

# Run 5000 simulations
results = monte_carlo_championship(season, simulations=5000)

# View predictions
print(results)
```

---

## 🧠 Design Philosophy

| Principle | Description |
|-----------|-------------|
| ✔ **Domain-first modeling** | Models reflect real F1 structure |
| ✔ **No hardcoded logic** | Rules driven by season data |
| ✔ **Rules driven by season** | Adapts to FIA regulation changes |
| ✔ **Extendable for live data** | Ready for real-time integration |
| ✔ **Clean separation** | Data & logic are independent |

This project was built to scale into:
- 📡 Live race analysis
- 🎯 Strategy simulations
- 📊 Data visualization dashboards
- 🕰️ Historical season replay

---

## 🚀 Future Roadmap

### 🔜 Coming Next

- [ ] 🟢 **Live Race Mode** (real-time WDC/WCC updates)
- [ ] 📊 **Streamlit Dashboard** (interactive visualization)
- [ ] 🧪 **Unit test suite** (comprehensive testing)
- [ ] 🌍 **Multi-season comparison** (historical analysis)
- [ ] 🧠 **ML-based driver performance weighting** (intelligent predictions)
- [ ] 📈 **Strategy optimizer** (pit stop & tire strategy)
- [ ] 🎮 **"What-if" scenario simulator** (alternative outcomes)
- [ ] 🌐 **Web API** (REST endpoints for predictions)

---

## 📸 Screenshots

*Coming soon: Dashboard previews, simulation outputs, and prediction visualizations*

---

## 🤝 Contributing

Contributions are welcome! Whether it's bug fixes, new features, or documentation improvements.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## ⚠️ Disclaimer

This project is for **educational and analytical purposes only**. 

Formula 1 is unpredictable — weather, strategy, penalties, and chaos always apply.

> *Maybe reality might be different xD* 🏎️💨

The predictions are probabilistic models based on historical data and simulations, not guarantees of actual race outcomes.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Bivraj** — F1 Enthusiast | Data & Design

[![GitHub](https://img.shields.io/badge/GitHub-biv720-black?logo=github)](https://github.com/biv720)
[![Twitter](https://img.shields.io/badge/Twitter-@bivraj-1DA1F2?logo=twitter)](https://twitter.com/bivraj)

---

## 🔗 Resources

- [FastF1 Documentation](https://docs.fastf1.dev/)
- [FIA Formula 1 Regulations](https://www.fia.com/regulation/category/110)
- [Formula 1 Official Site](https://www.formula1.com/)

---

<div align="center">

**Built with 🏁 for F1 data nerds and championship dreamers**

[⭐ Star this repo](https://github.com/biv720/F1KYC_KnowYourChamp) | [🐛 Report Bug](https://github.com/biv720/F1KYC_KnowYourChamp/issues) | [✨ Request Feature](https://github.com/biv720/F1KYC_KnowYourChamp/issues)

</div>
