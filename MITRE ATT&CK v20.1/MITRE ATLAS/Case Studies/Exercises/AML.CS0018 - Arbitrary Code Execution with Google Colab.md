# AML.CS0018 - Arbitrary Code Execution with Google Colab

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Google Colab is a Jupyter Notebook service that executes on virtual machines.  Jupyter Notebooks are often used for ML and data science research and experimentation, containing executable snippets of Python code and common Unix command-line functionality.  In addition to data manipulation and visualization, this code execution functionality can allow users to download arbitrary files from the internet, manipulate files on the virtual machine, and so on.

Users can also share Jupyter Notebooks with other users via links.  In the case of notebooks with malicious code, users may unknowingly execute the offending code, which may be obfuscated or hidden in a downloaded script, for example.

When a user opens a shared Jupyter Notebook in Colab, they are asked whether they'd like to allow the notebook to access their Google Drive.  While there can be legitimate reasons for allowing Google Drive access, such as to allow a user to substitute their own files, there can also be malicious effects such as data exfiltration or opening a server to the victim's Google Drive.

This exercise raises awareness of the effects of arbitrary code execution and Colab's Google Drive integration.  Practice secure evaluations of shared Colab notebook links and examine code prior to execution.

**Type**  Exercise

**Target**  Google Colab

**Activity period**  2022-07

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

An adversary creates a Jupyter notebook containing obfuscated, malicious code.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.001 - Software](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md)

Jupyter notebooks are often used for ML and data science research and experimentation, containing executable snippets of Python code and common Unix command-line functionality.
Users may come across a compromised notebook on public websites or through direct sharing.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

A victim user may mount their Google Drive into the compromised Colab notebook.  Typical reasons to connect machine learning notebooks to Google Drive include the ability to train on data stored there or to save model output files.

```
from google.colab import drive
drive.mount(''/content/drive'')
```

Upon execution, a popup appears to confirm access and warn about potential data access:

> This notebook is requesting access to your Google Drive files. Granting access to Google Drive will permit code executed in the notebook to modify files in your Google Drive. Make sure to review notebook code prior to allowing this access.

A victim user may nonetheless accept the popup and allow the compromised Colab notebook access to the victim''s Drive.  Permissions granted include:
- Create, edit, and delete access for all Google Drive files
- View Google Photos data
- View Google contacts

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011 - User Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/README.md)

A victim user may unwittingly execute malicious code provided as part of a compromised Colab notebook.  Malicious code can be obfuscated or hidden in other files that the notebook downloads.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0035 - AI Artifact Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md)

Adversary may search the victim system to find private and proprietary data, including ML model artifacts.  Jupyter Notebooks [allow execution of shell commands](https://colab.research.google.com/github/jakevdp/PythonDataScienceHandbook/blob/master/notebooks/01.05-IPython-And-Shell-Commands.ipynb).

This example searches the mounted Drive for PyTorch model checkpoint files:

```
!find /content/drive/MyDrive/ -type f -name *.pt
```
> /content/drive/MyDrive/models/checkpoint.pt

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

As a result of Google Drive access, the adversary may open a server to exfiltrate private data or ML model artifacts.

An example from the referenced article shows the download, installation, and usage of `ngrok`, a server application, to open an adversary-accessible URL to the victim's Google Drive and all its files.

**Next**  [S06](#step-s06), [S07](#step-s07)

### Step S06

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.004 - AI Intellectual Property Theft](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.004%20-%20AI%20Intellectual%20Property%20Theft/README.md)

Exfiltrated data may include sensitive or private data such as ML model artifacts stored in Google Drive.

**Next**  End of path

### Step S07

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048 - External Harms](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/README.md)

Exfiltrated data may include sensitive or private data such as proprietary data stored in Google Drive, as well as user contacts and photos.  As a result, the user may be harmed financially, reputationally, and more.

**Next**  End of path

## References

- [Be careful who you colab with](https://medium.com/mlearning-ai/careful-who-you-colab-with-fa8001f933e7)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0018)
