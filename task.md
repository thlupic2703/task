# Module Installation in PyCharm

PyCharm is an IDE specifically designed for Python. One of the reasons for its wide-spread use is definitely its user-friendly nature. This is especially highlighted in one of its most important features - the installation of *modules* and *packages*.
<br>
</br>
## Key Terms

<mark>Modules</mark> are files in Python containing functions and/or dictionaries, lists, classes, etc. that have to be **imported** in order to be used. 

One can either import the whole module or only one part of it.

Modules are organized into larger structures called <mark>packages</mark>. One package includes modules designed for a similar purpose. An example of a package would be *Requests* used for communication with servers.
<br>
</br>
## Installation Process through Pip


Usually the process of installation includes the use of command-line and *pip*, package manager for Python:

```
 python <python-version> -m pip install <package-name>
```

Where:
* pip needs to be installed beforehand (it is not included in Python by default)
* the version of Python is needed only when multiple ones are installed
* <mark>-m</mark> stands for module

<br>
</br>
## Installation Process in PyCharm

However, in PyCharm, this is possible without installing the package manager first. This is because Pycharm comes with a pre-installed package manager for Python. Command-line does not need to be used, but everything can be done through the IDE.

After launching PyCharm, open a project in which this module will be used by clicking on *File* > *New Project...* > *Create*. 

Then go to *File* > *Settings* > *Project: \[project-name\]* > *Python Interpreter*. From there, packages can be:

* installed <span style="color:red">**(1.)**</span>
* uninstalled <span style="color:red">**(2.)**</span>
* updated <span style="color:red">**(3.)**</span>

and their early releases <span style="color:red">**(4.)**</span> can be shown.

When the update is available, it is indicated by a triangle next to the number of the latest version (column 3). <span style="color:red">**(5.)**</span>

<br>

<center>
  <img width="550" src="module_manager.png">
</center>

</br>

> :information_source: *Note:*
>
><span style="color:grey">*If by default Python Interpreter is set to `<No interpreter>`, choose one by clicking on the settings button in the upper right corner and then on *Add*. It is recommended to use the System Interpreter (Python.exe).*</span>

<br>

When everything is set up, the module installation process can begin. By clicking on the **+ sign** above the list of packages, a new dialog box opens. Here, packages can be searched for and installed. 

Note that a choice can be made to *"Install [the package] to user's site packages directory"* or, in other words, to the specified directory. However, if this checkbox is left unchecked, the package is installed to the IDE's designated directory.

Simply type in the name of the desired package and once it is found, click on *Install Package*:

</br>

<center>
  <img width="550" src="spacy.png">
</center>

<br>

Once the package is installed, on the bottom of the dialog box the following message will be shown:

</br>

<center>
  <img width="250" src="success.png">
</center>

<br>

This means that the package is ready to be used. The installation has been successful when the package can be found on the list of installed packages.

</br>

<details>
  <summary markdown="span">SHOW THE EXAMPLE OF MODULE USAGE</summary>
<br>
When installing, for example, Spacy, as in the picture above, the English dictionary (en_core_web_sm) needs to be installed separately. This is done by writing and running the following code:

</br>

```python
import spacy
spacy.cli.download("en_core_web_sm")
```

<br>

Once everything is installed with no error messages popping up, the module and its dictionary can successfuly be used for natural language processing in Python:

</br>

```python
import spacy
nlp = spacy.load("en_core_web_sm")

doc = nlp("In 2020, Apple made a profit of $10 million dollars in the U.S. only.")

for token in doc:
    print(token.text, token.pos_, token.dep_)
```
</details>