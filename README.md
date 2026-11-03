# diffegyenletek
latex jegyzet az ELTE IK PTI Differenciálegyenletek tárgy előadásáról


# Visual Studio Code-ban tasks.json gyors buildeléshez:

```
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build LaTeX",
      "type": "process",
      "command": "/usr/bin/latexmk",
      "args": [
        "-pdf",
        "-pdflatex=/usr/bin/pdflatex %O %S",
        "-output-directory=build",
        "-interaction=nonstopmode",
        "-halt-on-error",
        "diffegyenletek.tex"
      ],
      "options": {
        "cwd": "${workspaceFolder}"
      },
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "presentation": {
        "reveal": "always",
        "panel": "shared",
        "clear": true
      },
      "problemMatcher": []
    }
  ]
}
```
