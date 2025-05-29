# Formula-1-Performance-Analytics
his project uses the [FastF1](https://theoehrly.github.io/Fast-F1/) Python library to analyze and visualize Formula 1 telemetry data. It provides insights into driver performance by retrieving and comparing real race session data, including speed profiles and lap times.

## 📘 Project Summary

The notebook `F1.ipynb` demonstrates:

- How to load and cache F1 session data (e.g., Australia 2023, Monza 2019)
- Retrieval of specific driver laps (e.g., Max Verstappen, Charles Leclerc)
- Visualization of telemetry data like speed vs time
- Comparison of fastest laps
- Basic data exploration using Pandas, Matplotlib, and Seaborn

## 📂 Repository Structure

```
f1-telemetry-analysis/
├── F1.ipynb               # Main analysis notebook
├── README.md              # Project documentation
├── cache/                 # Automatically created cache folder (after first run)
```

## 📊 Technologies Used

- **Python 3.8+**
- **FastF1** – F1 race data API & telemetry access
- **Pandas** – Data manipulation
- **Matplotlib / Seaborn** – Plotting and visualization
- **Jupyter Notebook** – Interactive code execution and display

## 📦 Installation

To install the required Python packages, run:

```bash
pip install fastf1 pandas matplotlib seaborn
```

## 🚀 How to Run

1. Clone the repository:

```bash
git clone https://github.com/yourusername/f1-telemetry-analysis.git
cd f1-telemetry-analysis
```

2. Open the Jupyter notebook:

```bash
jupyter notebook F1.ipynb
```

3. Inside the notebook, run all cells to:
   - Enable FastF1 cache
   - Load specific F1 sessions
   - Retrieve telemetry data
   - Generate plots (e.g., Speed vs Time)

## 💡 Example Visualizations

- Speed vs Time for Charles Leclerc’s fastest lap at Monza 2019
- All laps from Max Verstappen during the 2023 Australian Grand Prix
- Session summaries and driver comparisons

## 🛠 Sample Code Snippets

```python
import fastf1
fastf1.Cache.enable_cache('cache')
session = fastf1.get_session(2023, 'Australia', 'R')
session.load()
laps = session.laps.pick_driver('VER')
```

```python
from matplotlib import pyplot as plt
car_data = laps.pick_fastest().get_car_data()
plt.plot(car_data['Time'], car_data['Speed'])
plt.title("Speed vs Time")
plt.xlabel("Time")
plt.ylabel("Speed (Km/h)")
plt.show()
```

## 📁 Notes

- A `cache/` directory is automatically created to store downloaded session data.
- You must be connected to the internet for the first-time download of session data.
- No datasets are included in the repo as FastF1 fetches them live from official sources.

## 📝 License

This project is licensed under the [MIT License](LICENSE).

## 🙏 Acknowledgements

- [FastF1 by @theOehrly](https://github.com/theOehrly/Fast-F1)
- Formula 1 data is publicly available and accessed via official APIs.
