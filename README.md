# pixi-vscode-imports

How to repro

1. Clone the repo
```
git clone git@github.com:trent-abc/pixi-vscode-imports.git
```

2. install pixi - https://pixi.prefix.dev/latest/installation/

3. Install pixi deps, and modify your python.defaultInterpreterPath
```
cd pixi-vscode-imports && pixi install
sed -i "s=/some-path="$(pwd)"=g" .vscode/settings.json
```

4. Open vscode, make sure Python and Pylance extensions are installed and view repro.py. 

Import "attrs" could not be resolvedPylancereportMissingImports

5. See that it's loading the wrong version of python in vscode view

view -> output -> Python

6. Command + Shift + P -> Select default python interpreter. Notice that
:gear: Use Python from python.defaultInterpreterPath setting is not selected by default, but instead a Global value of something else is used.

