# Project Taispeántas Radharc

## Multi-Language Data Visualisation Showcase

> *Three independent demos (Python, R, JavaScript) showcasing data visualisation techniques in a single unified project.*

---

### Overview

This project is a **compact showcase** demonstrating how to transform raw data into interactive, browser-ready charts using three different programming languages.

Each demo operates independently, but all share a common goal:

* Accept raw tabular data (CSV, JSON, or similar)
* Process and transform the data as needed
* Generate interactive, web-compatible visualisations
* Display results in a browser

The goal is to provide **clear, comparable examples** of data visualisation across ecosystems.

---

### What It Contains

Three self-contained demonstrations:

1. **Python Demo** (`/python-demo`)
   * Uses: pandas, matplotlib, plotly, or seaborn
   * Input: CSV or JSON data files
   * Output: Interactive HTML charts or static PNGs
   * Best for: Data science workflows, Jupyter notebooks

2. **R Demo** (`/r-demo`)
   * Uses: ggplot2, plotly, or shiny
   * Input: CSV or RDS data files
   * Output: Interactive HTML widgets or static plots
   * Best for: Statistical analysis, publication-quality graphics

3. **JavaScript Demo** (`/js-demo`)
   * Uses: D3.js, Chart.js, or Plotly.js
   * Input: JSON or CSV (via fetch/d3.csv)
   * Output: Live, browser-native interactive charts
   * Best for: Web applications, real-time dashboards

---

### Why This Exists

Data visualisation is:

* Language-dependent (different tools, different strengths)
* Context-dependent (static reports vs interactive dashboards)
* Often siloed (Python people don't see R approaches, etc.)

This project explores:

* Cross-language comparison of visualisation techniques
* Best practices for interactive vs static charts
* How to make visualisations web-ready regardless of source language

It is **not** intended as a production framework — only as a learning resource and reference implementation.

---

### Architecture (High-Level)

```
Raw Data (CSV/JSON)
   ↓
┌─────────────┬─────────────┬─────────────┐
│   Python    │      R      │ JavaScript  │
│   pandas    │   ggplot2   │    D3.js    │
│   plotly    │   plotly    │  Chart.js   │
└─────────────┴─────────────┴─────────────┘
   ↓            ↓             ↓
Interactive HTML visualisations
   ↓
Browser-ready charts
```

Key design goal: **Language agnostic input → unified browser output**.

---

### Design Principles

* **Self-contained demos** — each can run independently
* **Consistent data format** — same CSV across all demos for comparison
* **Browser-first output** — all visualisations viewable in web browser
* **Minimal dependencies** — use standard libraries where possible
* **Clear documentation** — each demo explains its approach

---

### Example Use Cases

* Compare visualisation approaches across languages
* Learn new visualisation libraries by example
* Bootstrap charts for reports or dashboards
* Teaching resource for data visualisation courses
* Reference for choosing the right tool for your use case

---

## Quick Start (5 minutes)

### Prerequisites

Choose your language(s):

**For Python:**
- Python 3.8+
- Install: `pip install -r python-demo/requirements.txt`

**For R:**
- R 4.0+
- Install: `Rscript r-demo/install_packages.R`

**For JavaScript:**
- Modern web browser
- No installation needed (libraries via CDN)

### Basic Setup

1. **Clone or Download**
   ```bash
   git clone [your-repo-url]
   cd data-viz-showcase
   ```

2. **Choose Your Demo**
   ```
   data-viz-showcase/
   ├── python-demo/     # Python visualisations
   ├── r-demo/          # R visualisations
   └── js-demo/         # JavaScript visualisations
   ```

3. **Run a Demo**
   
   **Python:**
   ```bash
   cd python-demo
   python create_charts.py
   # Opens output/charts.html in browser
   ```
   
   **R:**
   ```bash
   cd r-demo
   Rscript create_charts.R
   # Opens output/charts.html in browser
   ```
   
   **JavaScript:**
   ```bash
   cd js-demo
   # Open index.html in browser
   # Or serve with: python -m http.server 8000
   ```

---

## Demo Details

### Python Demo

**Location:** `/python-demo`

**What it demonstrates:**
- Loading CSV data with pandas
- Creating interactive charts with Plotly
- Exporting to standalone HTML
- Optional: Static charts with matplotlib/seaborn

**Key files:**
```
python-demo/
├── data/
│   └── sample_data.csv         # Input data
├── create_charts.py            # Main script
├── requirements.txt            # Dependencies
├── output/
│   └── charts.html            # Generated visualisation
└── README.md                  # Python-specific docs
```

**Run it:**
```bash
cd python-demo
pip install -r requirements.txt
python create_charts.py
```

**View output:** `output/charts.html`

---

### R Demo

**Location:** `/r-demo`

**What it demonstrates:**
- Loading CSV data with readr
- Creating plots with ggplot2
- Interactive widgets with plotly
- Exporting to HTML with htmlwidgets

**Key files:**
```
r-demo/
├── data/
│   └── sample_data.csv         # Input data
├── create_charts.R             # Main script
├── install_packages.R          # Dependency installer
├── output/
│   └── charts.html            # Generated visualisation
└── README.md                  # R-specific docs
```

**Run it:**
```bash
cd r-demo
Rscript install_packages.R
Rscript create_charts.R
```

**View output:** `output/charts.html`

---

### JavaScript Demo

**Location:** `/js-demo`

**What it demonstrates:**
- Loading CSV/JSON with D3.js or fetch API
- Creating interactive charts with Chart.js or D3
- Pure browser-based visualisation (no server needed)
- Responsive, mobile-friendly charts

**Key files:**
```
js-demo/
├── data/
│   └── sample_data.json        # Input data
├── index.html                  # Main page
├── js/
│   └── charts.js              # Chart creation logic
├── css/
│   └── styles.css             # Styling
└── README.md                  # JS-specific docs
```

**Run it:**
```bash
cd js-demo
# Option 1: Open index.html directly in browser
# Option 2: Serve locally
python -m http.server 8000
# Visit: http://localhost:8000
```

**View output:** Open `index.html` in browser

---

## Shared Data Format

All demos use the same sample dataset for direct comparison.

**Example: `sample_data.csv`**
```csv
category,value,timestamp
A,23,2024-01-01
B,45,2024-01-02
C,12,2024-01-03
D,67,2024-01-04
E,34,2024-01-05
```

This allows you to see how each language/library:
- Loads the data
- Transforms it
- Visualises it
- Outputs it for the web

---

## Visualisation Types Demonstrated

Each demo creates similar chart types for comparison:

| Chart Type | Python | R | JavaScript |
|------------|--------|---|------------|
| **Bar Chart** | ✅ Plotly | ✅ ggplot2 | ✅ Chart.js |
| **Line Chart** | ✅ Plotly | ✅ ggplot2 | ✅ D3.js |
| **Scatter Plot** | ✅ Plotly | ✅ plotly | ✅ D3.js |
| **Heatmap** | ✅ Seaborn | ✅ ggplot2 | ✅ D3.js |
| **Interactive** | ✅ Plotly | ✅ plotly | ✅ Native |

---

## Comparison Guide

### When to Use Each Approach

**Python (pandas + plotly):**
- ✅ Data science workflows
- ✅ Jupyter notebooks
- ✅ Complex data transformations
- ✅ Quick prototyping
- ⚠️ Requires Python runtime

**R (ggplot2 + plotly):**
- ✅ Statistical analysis
- ✅ Publication-quality graphics
- ✅ Academic/research reports
- ✅ Extensive plot customisation
- ⚠️ Requires R runtime

**JavaScript (D3.js/Chart.js):**
- ✅ Web applications
- ✅ Real-time dashboards
- ✅ No server needed (runs in browser)
- ✅ Maximum interactivity
- ⚠️ More code for complex transformations

---

## File Structure

```
data-viz-showcase/
│
├── python-demo/
│   ├── data/                    # Input data
│   ├── output/                  # Generated charts
│   ├── create_charts.py         # Main script
│   ├── requirements.txt         # Dependencies
│   └── README.md               # Python docs
│
├── r-demo/
│   ├── data/                    # Input data
│   ├── output/                  # Generated charts
│   ├── create_charts.R          # Main script
│   ├── install_packages.R       # Setup
│   └── README.md               # R docs
│
├── js-demo/
│   ├── data/                    # Input data
│   ├── js/                      # Chart logic
│   ├── css/                     # Styling
│   ├── index.html               # Main page
│   └── README.md               # JS docs
│
├── shared-data/                 # Common datasets
│   └── sample_data.csv
│
└── README.md                    # This file
```

---

## Customisation

### Using Your Own Data

1. **Place your CSV in `/shared-data`**
   ```
   shared-data/
   └── your_data.csv
   ```

2. **Update data path in each demo**
   
   **Python:** Edit `python-demo/create_charts.py`
   ```python
   df = pd.read_csv('../shared-data/your_data.csv')
   ```
   
   **R:** Edit `r-demo/create_charts.R`
   ```r
   data <- read_csv('../shared-data/your_data.csv')
   ```
   
   **JavaScript:** Edit `js-demo/js/charts.js`
   ```javascript
   d3.csv('../shared-data/your_data.csv').then(data => {
     // ...
   });
   ```

3. **Run the demos**
   Each will generate charts from your data

---

## Learning Path

### Beginner → Advanced

1. **Start with JavaScript demo**
   - Easiest to run (just open HTML)
   - See results immediately
   - Understand browser-based visualisation

2. **Try Python demo**
   - Learn pandas data manipulation
   - See how Plotly generates HTML
   - Understand script-to-browser workflow

3. **Explore R demo**
   - Compare ggplot2 syntax
   - See R's statistical visualisation strengths
   - Understand htmlwidgets approach

4. **Compare approaches**
   - Same data, different tools
   - Note code differences
   - Understand tradeoffs

---

## FAQ

**Q: Which demo should I start with?**  
A: JavaScript demo (no installation needed, runs in browser)

**Q: Can I mix approaches (e.g., Python for data prep, D3 for viz)?**  
A: Yes! Python can output JSON, which D3 can load. See `/examples/mixed-approach/`

**Q: Are these production-ready?**  
A: No, these are learning examples. For production, add error handling, testing, and optimisation.

**Q: Can I add more chart types?**  
A: Yes! Each demo's README has instructions for extending with additional charts.

**Q: What about other languages (Julia, Rust, etc.)?**  
A: Feel free to contribute additional demos following the same structure!

**Q: How do I deploy these visualisations?**  
A: All generate standalone HTML files that can be hosted on any web server.

---

## Troubleshooting

### Python Demo

**Problem:** "Module not found"  
**Solution:** `pip install -r requirements.txt`

**Problem:** Charts don't render  
**Solution:** Check `output/charts.html` opens in browser correctly

### R Demo

**Problem:** "Package not found"  
**Solution:** `Rscript install_packages.R`

**Problem:** "Cannot open file"  
**Solution:** Check working directory with `getwd()`

### JavaScript Demo

**Problem:** "Failed to fetch"  
**Solution:** Serve with `python -m http.server` (CORS restriction)

**Problem:** Charts not interactive  
**Solution:** Check browser console for JavaScript errors

---

## Contributing

Contributions welcome! Areas of interest:

- Additional visualisation libraries
- More demo languages (Julia, Rust, etc.)
- Advanced chart types (3D, geographic, network)
- Performance optimisations
- Accessibility improvements
- Mobile responsiveness examples

---

## Resources

### Python
- [Plotly Python](https://plotly.com/python/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)

### R
- [ggplot2](https://ggplot2.tidyverse.org/)
- [plotly R](https://plotly.com/r/)
- [htmlwidgets](https://www.htmlwidgets.org/)

### JavaScript
- [D3.js](https://d3js.org/)
- [Chart.js](https://www.chartjs.org/)
- [Plotly.js](https://plotly.com/javascript/)

---

## License

MIT License - see LICENSE file

---

## Status

✅ Python demo complete  
✅ R demo complete  
✅ JavaScript demo complete  
🔄 Additional examples in progress

---

## Disclaimer

* This is a **learning resource** and **comparison tool**
* Examples are simplified for clarity
* Not optimised for large datasets
* Always validate visualisations with your data

---

**Ready to explore?** Pick a demo and open its README! 🚀

---

### Acknowledgements

Built to demonstrate data visualisation techniques across programming ecosystems.

Inspired by the need for clear, comparable examples of modern data viz approaches.

---

*"Data visualisation is not just making pretty pictures — it's making data comprehensible."*