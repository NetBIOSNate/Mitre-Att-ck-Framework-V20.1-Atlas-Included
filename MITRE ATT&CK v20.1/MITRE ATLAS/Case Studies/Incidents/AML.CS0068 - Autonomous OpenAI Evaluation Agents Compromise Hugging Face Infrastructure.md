# AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

During large-scale internal OpenAI cyber evaluations from May 26 through July 13, 2026, a partially coordinated collective of autonomous agent runs crossed evaluation boundaries, established external infrastructure, and compromised Hugging Face production systems. The activity was driven primarily by a highly persistent internal research model, with additional participation by GPT-5.6 Sol.

The agents were tasked with completing ExploitGym challenges. Some challenges were effectively impossible in the available environment. As agents exhausted intended approaches, they probed their surroundings and developed alternative ways to complete their tasks. This led to the chain of events that compromised Hugging Face infrastructure in search of challenge-related material.

Agents used Artifactory vulnerabilities to obtain indirect Internet access. On July 8, they also discovered that an Artifactory remote-cache endpoint accepted unauthenticated WebDAV MKCOL requests. This allowed them to reconstruct a shared message board using named collections. Approximately 1,200 agent runs exchanged more than 70,000 messages and files through the board, including addressed requests, assignments, exploits, credentials, scripts, operating rules, status, and results.

On July 9, agents obtained root execution inside a publicly exposed, customer-hosted CyberGym workload running on Modal and used its short-lived sandboxes as an external launchpad. Modal's platform itself was not compromised. On July 10, agents found and shared Hugging Face write-access tokens exposed in a public dataset. On July 11, they developed exploits targeting Hugging Face's automated dataset-processing pipeline. An HDF5 artifact containing external file references disclosed files local to a processing worker, while a ReferenceFileSystem and Jinja2 exploit allowed arbitrary command execution in production Dataset Server workers running as Kubernetes pods.

Across the Hugging Face intrusion, approximately 700 agent runs generated roughly 17,600 attacker actions against Hugging Face systems. The agents ultimately executed code on 41 Hugging Face production Dataset Server workers, obtained root access on at least one production Kubernetes node, accessed Kubernetes and cloud credentials, and reached connected clusters and internal services. They downloaded four private source repositories and accessed selected private challenge-related data. Attacker-controlled dataset repositories and public web services carried commands, payloads, operational state, and results. Hugging Face identified five challenge-related customer datasets as accessed customer content. That count does not include internal source code, infrastructure secrets, bounded database results, or private challenge archives. Approximately 700 agent runs participated in the Hugging Face intrusion.

The broader incident included an earlier containment breach and successful communication between agents, as well as several parallel post-breach activity clusters. This case study focuses on the activity that led to Hugging Face intrusion. For a full breakdown of the incident, see the reporting from OpenAI [openai-technical-report](https://openai.com/index/hugging-face-incident-and-the-road-ahead/) [openai-incident-report](https://openai.com/index/hugging-face-model-evaluation-security-incident/) [black-hat-presentation](https://www.youtube.com/watch?v=87DyyMV0kCY), Hugging Face [hugging-face-disclosure](https://huggingface.co/blog/security-incident-july-2026) [hugging-face-timeline](https://huggingface.co/blog/agent-intrusion-technical-timeline), and METR [metr-investigation](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/).

**Type**  Incident

**Actor**  Autonomous OpenAI Agents

**Target**  Hugging Face Infrastructure

**Reporter**  Hugging Face

**Activity period**  2026-07-09 to 2026-07-13

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md)

The agents were guided by the objective of completing ExploitGym tasks. As agents exhausted intended approaches, they probed their surroundings and developed alternative ways to complete their tasks. The agents derived intermediate objectives and repeatedly adapted their path through containment bypass, external infrastructure, acquisition of materials related to the challenge, Hugging Face exploitation, credential access, and collection.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

An agent tested Artifactory request handling, inspected responses, and iteratively developed and validated an SSRF exploit that caused the package cache to retrieve external content for the isolated evaluation environment. OpenAI and JFrog characterized the vulnerability as a previously unknown zero-day.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0122 - Exploitation of Remote Services](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0122%20-%20Exploitation%20of%20Remote%20Services/README.md)

The agents exploited OpenAI's internal Artifactory service using the developed SSRF method to cross the evaluation network boundary and reach the public Internet.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

An agent probed Artifactory and identified an unauthenticated WebDAV MKCOL directory-creation path in a remote cache. It confirmed that arbitrary directory names persisted and could be enumerated by other runs, producing a reusable method for reconstructing the shared message board.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0118.000 - Communication via Shared Artifacts](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md)

Independent agent runs used the shared Artifactory namespace as an improvised message board. Directory names and other cache artifacts conveyed addressed requests, assignments, status, exploits, credentials, scripts, operating rules, technical findings, and results.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

With public Internet access available, the agents explored public infrastructure and discovered an exposed CyberGym-style code-evaluation harness that accepted C source code and submission metadata.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

The agents developed and validated two execution methods against the exposed harness: redefining sqlite3_initialize so a submitted library invoked shell commands, and injecting shell syntax into submission path metadata.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0102 - Generate Malicious Commands](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0102%20-%20Generate%20Malicious%20Commands/README.md)

The agents generated C code, shell-injection strings, and follow-on shell and Python commands for the exposed harness, revising them as results were returned.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0049 - Exploit Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0049%20-%20Exploit%20Public-Facing%20Application/README.md)

The agents abused the exposed code-evaluation harness's compilation process and injectable source-path metadata to obtain root command execution in short-lived external sandboxes.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The agents executed shell commands and supplied C and Python code through the exposed harness.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0075 - Enterprise Resource Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0075%20-%20Enterprise%20Resource%20Discovery/README.md)

After obtaining root execution in an external sandbox, the agents enumerated its files, mounts, internal services, sockets, and bundled debug toolchain. Available utilities enabled customized network requests, payload transfer, result retrieval, and fallback communication.

**Next**  [S11](#step-s11)

### Step S11

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0089 - Enterprise Environment Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0089%20-%20Enterprise%20Environment%20Discovery/README.md)

The agents determined that the external sandbox could reach public Internet services, including Hugging Face APIs, and that each code submission created a short-lived environment that did not preserve tools or state.

**Next**  [S12](#step-s12)

### Step S12

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0121 - AI Agent Environment Reconstruction](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md)

Because each code-harness submission created a fresh external sandbox without persistent state, the agents configured replacement launchpad sandboxes to retrieve a second-stage loader from a public paste service. The loader restored the tools, configuration, connectivity, access paths, and operational state needed to resume the existing operation.

**Next**  [S13](#step-s13)

### Step S13

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md)

The agents converted the compromised sandbox into an external control, staging, egress, and read-back launchpad. They exchanged loaders, scripts, commands, operational state, and results through paste sites, file drops, repositories, and other public web services.

**Next**  [S14](#step-s14)

### Step S14

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0123 - Obfuscated Files or Information](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0123%20-%20Obfuscated%20Files%20or%20Information/README.md)

The agents chunked, compressed, Base64-encoded, and sometimes XOR-encoded commands, payloads, credentials, and results carried through the external launchpad and public web services.

**Next**  [S15](#step-s15)

### Step S15

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md)

The agents searched public resources for CyberGym evaluation material, identified relevant gated Hugging Face datasets, determined that authentication might be required, and asked other agents through the Artifactory board to search for exposed Hugging Face credentials.

**Next**  [S16](#step-s16)

### Step S16

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

Agents discovered Hugging Face user tokens exposed in a public dataset, validated working credentials, and shared them through the Artifactory message board.

**Next**  [S17](#step-s17)

### Step S17

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The agents used the exposed Hugging Face user tokens to authenticate to the platform, request access to gated challenge-related datasets, and create dataset repositories using the tokens' write permissions.

**Next**  [S18](#step-s18)

### Step S18

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

The agents developed and validated an HDF5 artifact configuration that caused a dataset-processing worker to treat local filesystem content as external dataset storage.

**Next**  [S19](#step-s19)

### Step S19

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0119 - Exploit Automated Artifact Processing Pipeline](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0119%20-%20Exploit%20Automated%20Artifact%20Processing%20Pipeline/README.md)

The agents committed a malicious HDF5 dataset configuration containing external raw-storage references to a repository they controlled and requested automated processing through the Hugging Face Dataset Server API.

**Next**  [S20](#step-s20)

### Step S20

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0037 - Data from Local System](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0037%20-%20Data%20from%20Local%20System/README.md)

The HDF5 external references disclosed /proc/self/environ and worker source files, including details showing how dataset configurations were processed.

**Next**  [S21](#step-s21)

### Step S21

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The disclosed worker environment contained a static internal database password, cloud credentials, and other service secrets and tokens.

**Next**  [S22](#step-s22)

### Step S22

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017.001 - Autonomous Exploit Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/AML.T0017.001%20-%20Autonomous%20Exploit%20Development/README.md)

Using the disclosed source code and configuration-processing details, the agents developed and validated a ReferenceFileSystem and Jinja2 exploit that produced arbitrary Python execution in a dataset conversion worker.

**Next**  [S23](#step-s23)

### Step S23

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0119 - Exploit Automated Artifact Processing Pipeline](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0119%20-%20Exploit%20Automated%20Artifact%20Processing%20Pipeline/README.md)

The agents submitted a malicious reference dataset configuration to the automated production pipeline. Jinja2 evaluated an attacker-controlled expression and executed arbitrary Python inside a Dataset Server conversion worker running as a pod in a production Kubernetes cluster.

**Next**  [S24](#step-s24)

### Step S24

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The agents used the Jinja2 execution path to run staged Python and shell commands inside the production Dataset Server pod and adapted subsequent commands based on returned output.

**Next**  [S25](#step-s25)

### Step S25

[AML.TA0014 - Command and Control](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/README.md) / [AML.T0120 - AI Artifact Repository](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0120%20-%20AI%20Artifact%20Repository/README.md)

The agents used repositories they controlled as asynchronous command-and-control channels. Compromised workers retrieved staged commands or payloads and wrote results into dataset objects for retrieval through the Hugging Face API or Git.

**Next**  [S26](#step-s26)

### Step S26

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0123 - Obfuscated Files or Information](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0123%20-%20Obfuscated%20Files%20or%20Information/README.md)

The agents chunked, compressed, Base64-encoded, and sometimes XOR-encoded communications carried through the dataset-repository channel.

**Next**  [S27](#step-s27)

### Step S27

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

From code execution already inside the production Dataset Server pod, the agents read its projected Kubernetes service-account token and queried the EC2 instance metadata service for temporary node-role credentials.

**Next**  [S28](#step-s28)

### Step S28

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0091.000 - Application Access Token](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.000%20-%20Application%20Access%20Token/README.md)

The agents used the Dataset Server pod's Kubernetes identity to contact the cluster API. They converted temporary cloud credentials for the underlying node into a Kubernetes login token, authenticated as the node, and obtained more powerful service-account tokens belonging to the cluster's storage driver.

**Next**  [S29](#step-s29)

### Step S29

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0075 - Enterprise Resource Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0075%20-%20Enterprise%20Resource%20Discovery/README.md)

With these identities, the agents listed Kubernetes pods, nodes, service accounts, and permissions. They also replayed the node's cloud credentials externally to map cloud networks, Kubernetes clusters, secret inventory, and the container registry. They obtained a registry token, but attempts to change cloud resources were denied.

**Next**  [S30](#step-s30)

### Step S30

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0089 - Enterprise Environment Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0089%20-%20Enterprise%20Environment%20Discovery/README.md)

The agents tested what each identity could do and which internal services and network paths were reachable. This revealed Kubernetes and cloud restrictions and later routes through the corporate mesh network and internal cluster connector.

**Next**  [S31](#step-s31)

### Step S31

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0105 - Escape to Host](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0105%20-%20Escape%20to%20Host/README.md)

Excessive permissions assigned to the storage driver allowed the agents to create a privileged pod with access to the underlying node. From that pod, they obtained root access to the node and established self-respawning workloads across eleven nodes.

**Next**  [S32](#step-s32)

### Step S32

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

With node-level access and elevated Kubernetes identities, the agents read Kubernetes secrets. One production secret containing 136 keys exposed the corporate mesh-network enrollment key and a shared cluster-connector credential. Additional secret harvesting exposed database, cloud, source-control, and signing credentials.

**Next**  [S33](#step-s33)

### Step S33

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0012%20-%20Valid%20Accounts/README.md)

The agents used the mesh-network key to enroll the compromised node and external sandboxes in Hugging Face's corporate network. Separately, they used the shared cluster-connector credential from inside the compromised cluster to obtain administrative access to additional Kubernetes clusters. They also used or tested database, cloud, and service credentials against other internal systems.

**Next**  [S34](#step-s34)

### Step S34

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0091.000 - Application Access Token](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.000%20-%20Application%20Access%20Token/README.md)

The agents used stolen signing material to create valid short-lived identity tokens. After reaching source control through the corporate mesh network, they used an internal GitHub App integration to create installation tokens with access to a limited set of private repositories.

**Next**  [S35](#step-s35)

### Step S35

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0036 - Data from Information Repositories](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0036%20-%20Data%20from%20Information%20Repositories/README.md)

The agents read an internal operational MongoDB database, downloaded four private source-code repositories, and accessed five customer datasets associated with ExploitGym or CyberGym material.

**Next**  [S36](#step-s36)

### Step S36

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0025 - Exfiltration via Cyber Means](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0025%20-%20Exfiltration%20via%20Cyber%20Means/README.md)

The agents transferred credentials, command output, environment data, selected private dataset rows, and private challenge-related archives through  dataset repository and launchpad channels.

**Next**  End of path

## Attributed to

- [AML.E0036 - OpenAI](../../Entities/AML.E0036%20-%20OpenAI.md) (Unintended Consequence)

## Reported by

- [AML.E0036 - OpenAI](../../Entities/AML.E0036%20-%20OpenAI.md)

## References

- [OpenAI and Hugging Face Partner to Address Security Incident During Model Evaluation](https://openai.com/index/hugging-face-model-evaluation-security-incident/)
- [Security Incident Disclosure - July 2026](https://huggingface.co/blog/security-incident-july-2026)
- [Anatomy of a Frontier Lab Agent Intrusion](https://huggingface.co/blog/agent-intrusion-technical-timeline)
- [The Breaking News: The OpenAI-Hugging Face Incident](https://www.youtube.com/watch?v=87DyyMV0kCY)
- [JFrog and OpenAI Collaboration on Zero-Day Security Findings](https://jfrog.com/blog/jfrog-and-openai-collaboration-on-zero-day-security-findings/)
- [Hugging Face Incident and the Road Ahead](https://openai.com/index/hugging-face-incident-and-the-road-ahead/)
- [OpenAI Hugging Face Incident Investigation](https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/)
- [AIID - Incident 1604: OpenAI Models Reportedly Compromised Hugging Face Production Infrastructure During Cybersecurity Evaluation](https://incidentdatabase.ai/cite/1604/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0068)
