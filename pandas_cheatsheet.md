---


<h1 id="read-files">Read files</h1>
<h4 id="get-rid-of-unnamed-column-when-reading-dataset">Get rid of ‘Unnamed’ column when reading dataset</h4>
<p>Include <code>index_col=0</code> in the read_csv function:<br>
<code>df=pd.read_csv('data/namefile.csv', index_col=0)</code></p>
<h1 id="explore-data">Explore data</h1>
<h4 id="get-type-of-features">Get type of features</h4>
<p><code>df.dtypes</code></p>
<p><strong>Feature of type object:</strong><br>
If a feature is of type <strong>object</strong>, we can visualize the values and counts of its different levels using: <code>df['namefeature'].value_counts()</code><br>
We can transform the feature using <strong>one_hot_encoding</strong>:</p>
<h4 id="visualize-missing-data">Visualize missing data</h4>
<p>Install missingno using <code>pip install missingno</code>.<br>
Code:<br>
<code>import missingno as msno</code><br>
<code>msno.matrix(df)</code></p>
<h4 id="count-missing-data">Count missing data</h4>
<p>Missing data per features: <code>df.isna().sum(axis=0)</code><br>
Total number of missing data in the dataset: <code>df.isna().sum().sum()</code></p>
<h1 id="feature-engineering">Feature engineering</h1>
<h3 id="apply-applymap-and-map">Apply, applymap and map</h3>
<p><strong>Map:</strong>  It iterates over each element of a series.<br>
<code>df[‘column1’].map(lambda x: 10+x)</code>, this will add 10 to each element of column1.</p>
<p><strong>Apply:</strong>  As the name suggests, applies a function along any axis of the DataFrame.<br>
<code>df[[‘column1’,’column2’]].apply(sum)</code>, it will returns the sum of all the values of column1 and column2.</p>
<p><strong>ApplyMap:</strong>  This helps to apply a function to each element of dataframe.<br>
<code>func = lambda x: x+2</code><br>
<code>df.applymap(func)</code><br>
It will add 2 to each element of dataframe (all columns of dataframe must be numeric type)</p>
<h1 id="plots">Plots</h1>
<h4 id="print">Format prints</h4>
<p>https://mkaz.blog/code/python-string-format-cookbook/</p>



<h4 id="visualize-plots-in-jupyter-notebook">Visualize plots in Jupyter Notebook</h4>
<p><code>%matplotlib inline</code></p>
<h4 id="basic-plot-in-matplotlib">Basic plot in matplotlib</h4>
<p>We create the objects fig and axes by calling plt.subplots. We could also create a figure object with plt.figure and then add axes to it.<br>
The figure size help specifying the proportion of the figure. Dpi allows to change the size without changing modifying the proportions. The final size of the figure will be (figsize[0] <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mo>×</mo></mrow><annotation encoding="application/x-tex">\times</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.66666em; vertical-align: -0.08333em;"></span><span class="mord">×</span></span></span></span></span> dpi, figsize[1] <span class="katex--inline"><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mo>×</mo></mrow><annotation encoding="application/x-tex">\times</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height: 0.66666em; vertical-align: -0.08333em;"></span><span class="mord">×</span></span></span></span></span> dpi).</p>
<p><code>fig, axes = plt.subplots(figsize=(12,3),dpi = 80)</code></p>
<p><code>axes.plot(x, y, 'r')</code><br>
<code>axes.set_xlabel('x')</code><br>
<code>axes.set_ylabel('y')</code><br>
<code>axes.set_title('title');</code></p>
<h1 id="ml">ML</h1>
<h4 id="split-df-into-a-train-and-test-set">Split df into a train and test set</h4>
<p><code>from sklearn.model_selection import train_test_split</code><br>
<code>X=df.drop(['target'],axis=1)</code><br>
<code>y=df['target']</code><br>
<code>X_train, y_train, X_test, y_test=train_test_split(X,y,test_size=0.2, random_state=42)</code></p>
<h1 id="conda-env">Conda env</h1>
<p>Documentation available here :<br>
<a href="https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html">https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html</a></p>
<h3 id="conda-envs">Conda envs</h3>
<p><code>conda env list</code><br>
<code>conda activate myenv</code><br>
<code>conda deactivate</code></p>
<h3 id="ipython-kernels">Ipython kernels</h3>
<p>First activate the environment:<br>
<code>conda activate myenv</code><br>
If not installed in the env yet: <code>pip install ipykernel</code><br>
Create kernel:<br>
<code>python -m ipykernel install --user --name myenv --display-name "Python (myenv)"</code> (replace myenv twice)<br>
To remove the kernel:<br>
<code>jupyter kernelspec list</code><br>
<code>jupyter kernelspec uninstall name-kernel</code> (replace name-kernel)<br>
From a Jupyter notebook, click on New and choose the environment.</p>

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkxMzEyNTI3OF19
-->