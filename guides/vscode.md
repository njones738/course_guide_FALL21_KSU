---
layout: default
nav_order: 'A'
parent: User Guides
---

# VScode for Data Science

Visual Studio Code (VScode) is taking over the open source code editing space.  Even Rstudio is [providing VScode in their production environments](https://blog.rstudio.com/2021/06/02/rstudio-workbench-vscode-sessions/).  [This 2019 Stack Overflow survey](https://insights.stackoverflow.com/survey/2019#technology-_-most-popular-development-environments) pegs its usage at a 50% market share. It is fantastic for data science programming in Python and competes with Rstudio for programming in R.


## Installation

## The layout

VS Code comes with a [simple and intuitive layout](https://code.visualstudio.com/docs/getstarted/userinterface) that maximizes the space provided for the editor while leaving ample room to browse and access the full context of your folder or project. The UI is divided into five areas:

- **Editor** - The main area to edit your files. You can open as many editors as you like side by side vertically and horizontally.
- **Side Bar** - Contains different views like the Explorer to assist you while working on your project.
- **Status Bar** - Information about the opened project and the files you edit.
- **Activity Bar** - Located on the far left-hand side, this lets you switch between views and gives you additional context-specific indicators, like the number of outgoing changes when Git is enabled.
- **Panels** - You can display different panels below the editor region for output or debug information, errors and warnings, or an integrated terminal. Panel can also be moved to the right for more vertical space. Each time you start VS Code, it opens up in the same state it was in when you last closed it. The folder, layout, and opened files are preserved.

![](https://byuidatascience.github.io/python4ds/diagrams/vscode-console.png)

## Interactive Python

An open-source project called [Jupyter](http://jupyter-notebook.readthedocs.io/en/latest/) is the standard method for interactive Python use for data science or scientific computing. However, there are [some issues](https://towardsdatascience.com/5-reasons-why-jupyter-notebooks-suck-4dc201e27086) with its use in a development environment. VS Code has provided a way for us to have the best of Python and Jupyter Notebooks with their [Python Interactive Window](https://code.visualstudio.com/docs/python/jupyter-support-py).

You will need to install the [jupyter python package](https://jupyter.readthedocs.io/en/latest/install.html) using `pip` for the interactive Python window to work.  The code chunk below will install 

```python
import sys
!{sys.executable} -m pip install jupyter pandas altair altair_saver numpy plotnine scikit-learn
```

Using the VS Code functionality, you will work with a standard `.py` file instead of the `.ipynb` extension typically used with jupyter notebooks. The Python extension in VS Code will recognize `# %%` as a cell or chunk of python code and add notebook options to ‘Run Cell’ as well as other actions. You can see the code example bellow with the image of the view in VS Code as an example. [Microsoft’s documentation](https://code.visualstudio.com/docs/python/jupyter-support-py) goes into more detail (https://code.visualstudio.com/docs/python/jupyter-support-py).

```
# %%
msg = "Hello World"
print(msg)

# %%
msg = "Hello again"
print(msg)
```

![](https://byuidatascience.github.io/python4ds/screenshots/vscode-code-cells-01.png)

### Settings adjustments

To make the interactive window use more functional you can `ctrl + ,` (`cmd + ,` on a mac) to open the settings. From there you can alter a few defaults.

- Search _‘Send Selection to Interactive Window’_ and make sure the box is checked. Now you will be able to use `shift + return` to send a selected chunk of code or an entire cell.
- Search _'Collapse Cell Input Code By Default'_ and uncheck the box. Now, your code will show expanded in the interactive Python console history by default.
- Search _'Always Scroll on New Cell'_ and make sure the box is checked.  Now, each time you run a chunk or command from your `.py` script the interactive window will scroll to the output.

## R Extension for Visual Studio Code

Yuki Ueda's [R extension](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) is the leading extension for using R within VScode. The [extension's wiki](https://github.com/REditorSupport/vscode-R/wiki) is a good guide. I recommend the following elements from their guide.

- [R Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r)
- [Radian for the R terminal](https://github.com/REditorSupport/vscode-R/wiki/Installation:-macOS#radian)
- [httpgd for chart management](https://github.com/REditorSupport/vscode-R/wiki/Installation:-macOS#httpgd)
- [Editing your VScode configuration](https://supunkavinda.blog/vscode-editing-settings-json) `"Edit in settings.json"`

```
{
  "r.bracketedPaste": true,
  "r.rterm.windows": "C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python37\\Scripts\\radian.exe"
  "r.rterm.mac": "/usr/local/bin/radian"
}
```
## Git and Github

Microsoft Github and is the lead developer of VScode.  As such, they are actively working on integrating Github and VScode functionality (see [Codespaces](https://github.com/features/codespaces)).  We will use the Git source control manager (SCM) that comes with VScode.  The [Git support guide from VScode](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support) will suffice for our needs. We will only leverage a small portion of Git within our class.

- [Clonning repositories from Github](https://code.visualstudio.com/docs/editor/versioncontrol#_cloning-a-repository)
- [staging and committing](https://code.visualstudio.com/docs/editor/versioncontrol#_commit)
- [Push and Pull commands](https://code.visualstudio.com/docs/editor/versioncontrol#_remotes)
