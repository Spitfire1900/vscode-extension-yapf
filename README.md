# Vscode formatter extension support for python files using yapf

A formatter extension with support for python files and notebook cell. Feel free to open an issue to tell me what feature else do you need since it's a preview version.  
Note:  
* This extension is supported for all [actively supported versions](https://devguide.python.org/versions/#supported-versions) of the python language (i.e., python >= 3.8(EOL: 2024-10)).

## Quick Start
Setting the following can enable this formatter quickly.
```
  "[python]": {
    "editor.formatOnSaveMode": "file",
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "eeyore.yapf"
  }
```


## Usage
* Install `yapf` package from pip in following. This is optional but recommended way, else it will use the bundled `yapf=0.40.2`
```
pip install yapf
```
* Select this fotmatter `eeyore.yapf` by adding the following to your vscode settings 
```
  "[python]": {
    "editor.defaultFormatter": "eeyore.yapf"
  }
```
and change the following, the reason see [issue#13](https://github.com/EeyoreLee/vscode-extension-yapf/issues/13)
```
  "python.formatting.provider": "none"
```
* Enable format on save by adding the following
```
  "[python]": {
    "editor.formatOnSave": true
  }
```

## file mode & modifications mode
Choose the mode by the following
* Use file mode
```
  "[python]": {
    "editor.formatOnSaveMode": "file"
  }
```
* Use modifications mode
```
  "[python]": {
    "editor.formatOnSaveMode": "modifications"
  }
```

## Format for notebook
* Format on cell execution
```
  "notebook.formatOnCellExecution": true
```
* Format on save
```
  "notebook.formatOnSave.enabled": true
```

## Set your own yapf style
* Set style by the following vscode settings which is equal to `yapf --style '{based_on_style: pep8, indent_width: 2}'`
```
  "yapf.args": ["--style", "{based_on_style: pep8, indent_width: 2}"]
```
* Use a style file, like `.style.yapf`, `setup.cfg`, `pyproject.toml`, `~/.config/yapf/style`. For details, see [google/yapf](https://github.com/google/yapf)
