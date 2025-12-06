# Scientific-Research-Trends

## Run & Reproduce

- **Prereqs**: Python 3.10+, git, `pip`, and enough RAM/disk for the arXiv metadata JSON (~7GB compressed, ~15GB loaded).
- **Install deps**:
	```bash
	python -m venv .venv
	source .venv/bin/activate
	pip install --upgrade pip
	pip install numpy pandas matplotlib seaborn scikit-learn networkx pyvis
	```
- **Get data**: Download `arxiv-metadata-oai-snapshot.json` (Kaggle arXiv metadata) and place it at `data/arxiv-metadata-oai-snapshot.json`.
- **Adjust path**: In `project.ipynb`, set the load path in the first data cell to your local file, e.g.:
	```python
	chunks = pd.read_json("data/arxiv-metadata-oai-snapshot.json", lines=True, chunksize=100000)
	```
- **Run notebook**: Start Jupyter and run all cells:
	```bash
	jupyter lab
	# open project.ipynb and Run All
	```
- **Outputs**: Plots render inline; interactive HTML files are written next to the notebook:
	- `coauthor_network.html`
	- `category_cooccurrence.html`
- **Repro tips**: If memory is constrained, lower `chunksize` when reading JSON or sample fewer docs before LDA (`N = min(len(docs), 20000)`).