
Visit the notebook at https://gtfierro.github.io/jupyterlite-demo/lab/index.html?fromURL=https://raw.githubusercontent.com/sonarsushant/California-House-Price-Prediction/refs/heads/master/housing.csv

- works well -- much faster than I remember. In my (limited) experimentation, it looks nearly indistinguishable from the full JupyterLab experience
- the jupyterlite template (what this is forked from) was very easy to use
- need to use this `fromURL` trick to load remote data into the notebook
    - [docs](https://jupyterlite.readthedocs.io/en/stable/howto/content/open-url-parameter.html)
    - this failed on a ~160MB file but works on the small < 1MB file above
        - Using [this](https://raw.githubusercontent.com/sonarsushant/California-House-Price-Prediction/refs/heads/master/housing.csv) dataset
- if you stick to the usual packages you will probably be fine, but adding additional (or unusual) packages requires some build steps:
    - https://jupyterlite.readthedocs.io/en/stable/howto/pyodide/packages.html
    - will need to do this ahead of time -- even though there is a "pip" provided, you will probably want to test the package works by building it into a custom pyodide distribution from the start
    - I was not able to get seaborn to work, but i'm not sure if this is my fault or if it's a limitation of the current pyodide build

