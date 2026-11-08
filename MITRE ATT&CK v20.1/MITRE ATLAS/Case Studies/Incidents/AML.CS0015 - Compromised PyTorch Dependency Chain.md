# AML.CS0015 - Compromised PyTorch Dependency Chain

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Linux packages for PyTorch's pre-release version, called Pytorch-nightly, were compromised from December 25 to 30, 2022 by a malicious binary uploaded to the Python Package Index (PyPI) code repository.  The malicious binary had the same name as a PyTorch dependency and the PyPI package manager (pip) installed this malicious package instead of the legitimate one.

This supply chain attack, also known as "dependency confusion," exposed sensitive information of Linux machines with the affected pip-installed versions of PyTorch-nightly. On December 30, 2022, PyTorch announced the incident and initial steps towards mitigation, including the rename and removal of `torchtriton` dependencies.

**Type**  Incident

**Actor**  Unknown

**Target**  PyTorch

**Reporter**  PyTorch

**Activity period**  2022-12-25 to 2022-12-30

## Procedure steps

### Step S00

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.001 - Software](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.001%20-%20Software/README.md)

A malicious dependency package named `torchtriton` was uploaded to the PyPI code repository with the same package name as a package shipped with the PyTorch-nightly build. This malicious package contained additional code that uploads sensitive data from the machine.
The malicious `torchtriton` package was installed instead of the legitimate one because PyPI is prioritized over other sources. See more details at [this GitHub issue](https://github.com/pypa/pip/issues/8606).

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0037 - Data from Local System](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0037%20-%20Data%20from%20Local%20System/README.md)

The malicious package surveys the affected system for basic fingerprinting info (such as IP address, username, and current working directory), and steals further sensitive data, including:
- nameservers from `/etc/resolv.conf`
- hostname from `gethostname()`
- current username from `getlogin()`
- current working directory name from `getcwd()`
- environment variables
- `/etc/hosts`
- `/etc/passwd`
- the first 1000 files in the user's `$HOME` directory
- `$HOME/.gitconfig`
- `$HOME/.ssh/*.`

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

All gathered information, including file contents, is uploaded via encrypted DNS queries to the domain `*[dot]h4ck[dot]cfd`, using the DNS server `wheezy[dot]io`.

**Next**  End of path

## Uses

- [AML.S0004 - torchtriton](../../Software/Malware/AML.S0004%20-%20torchtriton.md) — The actor uploaded a malicious [torchtriton](../../Software/Malware/AML.S0004%20-%20torchtriton.md) package to PyPI under the same name as a dependency hosted on PyTorch's nightly package index. Dependency resolution caused affected Linux installations between December 25 and 30, 2022, to retrieve the malicious package. When triton was imported, its payload collected system information and local files and transmitted them through encrypted DNS queries. [ref-1](https://pytorch.org/blog/compromised-nightly-dependency/)

## References

- [PyTorch statement on compromised dependency](https://pytorch.org/blog/compromised-nightly-dependency/)
- [Analysis by BleepingComputer](https://www.bleepingcomputer.com/news/security/pytorch-discloses-malicious-dependency-chain-compromise-over-holidays/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0015)
