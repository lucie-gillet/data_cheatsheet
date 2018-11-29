---


---

<h1 id="read-files">Read files</h1>
<h4 id="get-rid-of-unnamed-column-when-reading-dataset">Get rid of ‘Unnamed’ column when reading dataset</h4>
<p>Include <code>index_col=0</code> in the read_csv function:<br>
<code>df=pd.read_csv('data/namefile.csv', index_col=0)</code></p>
<h1 id="explore-data">Explore data</h1>
<h4 id="visualize-missing-data">Visualize missing data</h4>
<p>Install missingno using <code>pip install missingno</code>.<br>
Code:<br>
<code>import missingno as msno</code><br>
<code>msno.matrix(df)</code></p>
<h4 id="count-missing-data">Count missing data</h4>
<p>Missing data per features: <code>df.isna().sum(axis=0)</code><br>
Total number of missing data in the dataset: <code>df.isna().sum().sum()</code></p>
<h1 id="plots">Plots</h1>
<h4 id="visualize-plots-in-jupyter-notebook">Visualize plots in Jupyter Notebook</h4>
<p><code>%matplotlib inline</code></p>

