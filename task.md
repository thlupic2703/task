# Module Installation in PyCharm

PyCharm is an IDE specifically designed for Python. One of the reasons for its widespread use is its user-friendly nature. This is particularly highlighted in one of its most important newly-introduced features - the installation of *modules* and *packages* directly through the IDE's interface.

<br>

## Release Note

* quick and simple installation of modules directly through the GUI without using the terminal :rocket:

<br>

## Key Terms

**Modules** are files in Python containing functions and/or dictionaries, lists, classes, etc., which have to be **imported** in order to be used. 

One can either import the whole module or only a part of it.

Modules are organized into larger structures called **packages**. One package includes modules designed for a particular purpose. An example of a package would be *Requests* used for communication with servers.

<br>

## Installation Process through Pip

Usually, the process of installation includes the use of the command line and *pip*, package manager for Python:
<br>

```
 python <python-version> -m pip install <package-name>
```

Where:

* the version of Python should be included only when multiple ones are installed on the computer
* `-m` stands for module

<br>

## Installation Process in PyCharm

In the new version of PyCharm, the installation process is now possible without installing the package manager first. This is because the package manager is already included in this Python IDE! There is no need to use the command line since everything can be done with only a few clicks on the IDE's interface.

The process is as follows.

After launching PyCharm, open a project in which this module will be used by clicking on `File > New Project... > Create`. 

Then go to `File > Settings > Project: \[project-name\] > Python Interpreter`. From there, packages can be:

* installed <span style="color:red">**(1.)**</span>
* uninstalled <span style="color:red">**(2.)**</span>
* updated <span style="color:red">**(3.)**</span>

and their early releases <span style="color:red">**(4.)**</span> can be shown.

When an update is available, it is indicated by a triangle next to the number of the latest version (column 3). <span style="color:red">**(5.)**</span>

<br>

![Package Manager](https://github.com/thlupic2703/task/blob/master/images/module_manager.PNG?raw=true)

<br>

> :pushpin: **Note:**
>
><span style="color:grey">*If by default Python Interpreter is set to `<No interpreter>`, choose one by clicking on the settings button in the upper right corner and then on *Add*. It is recommended to use the System Interpreter (Python.exe).*</span>

<br>

When everything is set up, the module installation process can begin. By clicking on the **+ sign** above the list of packages, a new dialog box opens. Here, packages can be searched for and installed. 

Note that above the *Install Package* button a choice can be made to *"Install [the package] to user's site packages directory"*. If this is marked, the package will be installed to the location specified in the brackets. Alternatively, by default, the package will installed in the folder of the chosen **Python Interpreter** (in this case: Python 3.10).

Simply type in the name of the desired package and once it is found, click on *Install Package*:

<br>

![Installing a New Package](https://github.com/thlupic2703/task/blob/master/images/spacy.PNG?raw=true)

<br>

Once the package is installed, on the bottom of the dialog box, the following message will appear:
<br>

![Successful Installation](https://github.com/thlupic2703/task/blob/master/images/success.PNG?raw=true)
<br>

And voilá - the package is ready to be used! :tada: The installation has been successful when the package can be found on the list of installed packages.

Now all there is left to do is to import the package and start coding.

To see one of the modules in action, click on the arrow below:

<br>

<details>
  <summary markdown="span">SHOW THE EXAMPLE OF MODULE USAGE</summary>
<br>

When installing, for example, Spacy, as in the picture above, the English dictionary (en_core_web_sm) needs to be installed separately. This is done by writing and running the following code:
<br>

```python
import spacy
spacy.cli.download("en_core_web_sm")
```
<br>

Once everything is installed with no error messages popping up, the module and its dictionary can successfuly be used for natural language processing in Python:
<br>

```python
import spacy
nlp = spacy.load("en_core_web_sm")

doc = nlp("In 2020, Apple made a profit of $10 million dollars in the U.S. only.")

for token in doc:
    print(token.text, token.pos_, token.dep_)
```
</details>