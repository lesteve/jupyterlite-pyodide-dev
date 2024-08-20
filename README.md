[![lite-badge]][lite]

[lite]: https://lesteve.github.io/jupyterlite-pyodide-dev
[lite-badge]: https://jupyterlite.rtfd.io/en/latest/_static/badge-launch.svg

https://lesteve.github.io/jupyterlite-pyodide-dev

A JupyterLite using Pyodide development version as a more user-friendly
alternative to https://pyodide.org/en/latest/console.html.

The trick is to set pyodideUrl in [jupyter-lite.json](./jupyter-lite.json) as
indicated in the JupyterLite [doc](https://jupyterlite.readthedocs.io/en/latest/howto/pyodide/pyodide.html).

# How to update this repo

```bash
mamba create -n jupyterlite jupyterlite jupyterlite-pyodide-kernel jupyter_server jupyterlab_server
# Seems more reliable than jupyter lite build --force somehow ...
# otherwise pyodideUrl can disappear from _output/jupyter-lite.json ...
rm .jupyterlite.doit.db _output -rf
jupyter lite build --contents files
```

To double-check:
```
python -m http.server -d _output
```

and go to https://localhost:8000/index.html
