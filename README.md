# Cloud Middleware Dataset

This project contains cloud middleware (i.e. agents installed by cloud security providers) used across the major cloud service providers (Azure, AWS and GCP). 

The cloud middleware dataset lists all agents installed by the major cloud service providers (Azure, AWS, and GCP). The purpose of this project is to provide cloud customers fully visibility into the middleware that is installed in their environments, which could potentially increase the attack surface. 

## The cloud middleware problem

Cloud service providers install proprietary software on customers virtual machines usually without the customer’s awareness or explicit consent. This propriety software, that bridges between customers’ virtual machines and the cloud providers managed services, was often found to introduce new potential attack surface unknown to the cloud customers. Due to the implicit installation method of **cloud middleware** software, cloud customers are unaware of the existence of cloud middleware or of the new security risks it presents. As a result, when a new vulnerability is detected in a cloud middleware software, customers are left unknowingly exposed. Moreover, being the CSP’s proprietary software running on the customer environment, it is not always clear whose responsibility it is to update the middleware in the first place. 

## Field explanations

- Cloud provider: The name of the Cloud provider (AWS, GCP, or Azure) 
- Cloud services: A comma-seperated list of the names of the cloud services that install the cloud agent on the cloud users' virtual machines, **or** the name of the images where the agent is pre-installed. 
- Past vulnerabilities: A comma-separated list of past vulnerabilities found in the cloud agent. 
- Attack surface: A free text explanation of the potential attack surface of the cloud agent, such as.... 
- Open source: Indicates whether the cloud agent source is publicly accessible or not.
- Operating system: The operating system supported by the specific cloud agent. 
- Cloud Middleware Dataset

## Dataset

### Open Management Infrastructure (OMI)

* Cloud provider: Azure
* Cloud services: Azure Automation State Configuration, Extension Log Analytics, Agent Azure Diagnostics (LAD), Azure Update Management, Azure Automation, Azure Security Center, Azure Sentinel, Container Monitoring Solution, Azure HDInsight
* Past vulnerabilities: [CVE-2021-38645](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-38645) – Local privilege escalation to root, [CVE-2021-38647](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-38647) – Unauthenticated Remote Code Execution as root, [CVE-2021-38648](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-38648)– Local privilege escalation to root, [CVE-2021-38649](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-38649) – Local privilege escalation to root, [CVE-2022-29149](https://msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2022-29149) - Local privilege escalation
* Attack surface: 
  * Runs at high privileges (root)
  * Some configuration expose a remote attack surface
* Open source: https://github.com/microsoft/omi
* Operating system: Linux

### DSIMountAgent

* Cloud provider: Azure
* Cloud services: Azure Machine Learning
* Past vulnerabilities: [CVE-2023-23382](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2023-23382) – Azure Machine Learning Compute Instance Information Disclosure Vulnerability
* Attack surface: 
  * Runs at high privileges (root)
  * Used to expose a remote attack surface allowing information disclosure
* Open source: No
* Operating system: Linux

### Microsoft Azure Guest Agent (WALinuxAgent)

* Cloud provider: Azure
* Cloud services: Pre-built in all Azure Linux images
* Past vulnerabilities: [CVE-2019-0804](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-0804) - Incorrect Permission Assignment for Critical Resource
* Attack surface: 
  * Runs at high privileges (root)
* Open source: https://github.com/Azure/WALinuxAgent
* Operating system: Linux

### Operations Management Suite (OMS)

* Cloud provider: Azure
* Cloud services: Azure Log Analytics, Azure Sentinel, Azure Security Center
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges (root)
* Open source: https://github.com/microsoft/OMS-Agent-for-Linux
* Operating system: Linux

### Dependency agent

* Cloud provider: Azure
* Cloud services: Azure Log Analytics
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges  (root)
  * Exposes a kernel attack surface via kernel driver
* Open source: No
* Operating system: Linux

### Azure pipelines agent

* Cloud provider: Azure
* Cloud services: Azure Pipelines, Azure Log Analytics, Azure DevOps Server 2019+, TFS 2017+
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges 
* Open source: https://github.com/microsoft/azure-pipelines-agent
* Operating system: Linux, Windows

### Azure RD Agent Service

* Cloud provider: Azure
* Cloud services: Pre-built in all Azure Windows images
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges (SYSTEM)
* Open source: No
* Operating system: Windows

### Azure Arc-enabled Kubernetes agent

* Cloud provider: Azure
* Cloud services: Azure Arc
* Past vulnerabilities: [CVE-2022-37968](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2022-37968)
* Attack surface: 
  * Exposes remote attack surface via reverse proxy
* Open source: [No](https://learn.microsoft.com/en-us/azure/azure-arc/kubernetes/conceptual-agent-overview)
* Operating system: Linux

### AWS Systems Manager Agent (SSM Agent)

* Cloud provider: AWS
* Cloud services: Pre-built in Amazon virtual machine images
* Past vulnerabilities: [CVE-2022-29527](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-29527) - Local privilege escalation to root
* Attack surface: 
  * Runs at high privileges
* Open source: https://github.com/aws/amazon-ssm-agent
* Operating system: Windows, Linux, macOS

### AWS PV Drivers

* Cloud provider: AWS
* Cloud services: Pre-built in Amazon Windows virtual machine images
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Exposes a kernel attack surface
* Open source: No
* Operating system: Windows

### AWS ECS container agent

* Cloud provider: AWS
* Cloud services: Amazon ECS-optimized AMI, Amazon ECS-optimized Windows Server AMI, Amazon ECS-optimized Windows Server 2022 Full AMI, Amazon ECS-optimized Windows Server 2022 Core AMI, Amazon ECS-optimized Windows Server 2019 Full AMI, Amazon ECS-optimized Windows Server 2019 Core AMI, Amazon ECS-optimized Windows Server 2004 Core AMI
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges 
* Open source: https://github.com/aws/amazon-ecs-agent
* Operating system: Windows, Linux

### AWS EC2 Hibernation Initialization Agent

* Cloud Provider: AWS
* Cloud Services: Supported EC2 instances, including Amazon Linux
* Past vulnerabilities: No public vulnerabilities
* Attack surface:
  * Runs at high privileges
* Open Source: https://github.com/aws/amazon-ec2-hibinit-agent
* Operating system: Linux 

### Google Accounts Daemon

* Cloud provider: Google Cloud Platform
* Cloud services: Google OS Login
* Past vulnerabilities: [CVE-2020-8933](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8933) - Local privilege escalation to root
* Attack surface: 
  * Runs at high privileges 
* Open source: https://github.com/GoogleCloudPlatform/compute-image-packages/blob/master/packages/python-google-compute-engine/google_compute_engine/accounts/accounts_daemon.py
* Operating system: Linux

### Google OSConfig agent

* Cloud provider: Google Cloud Platform
* Cloud services: Pre-built in GCP virtual machine images
* Past vulnerabilities: [Google's osconfig agent - local privilege escalation](https://github.com/irsl/google-osconfig-privesc)
* Attack surface: 
  * Runs at high privileges 
* Open source: https://github.com/GoogleCloudPlatform/osconfig
* Operating system: Windows, Linux

### Google guest agent

* Cloud provider: Google Cloud Platform
* Cloud services: Pre-built in GCP virtual machine images
* Past vulnerabilities: No public vulnerabilities
* Attack surface: 
  * Runs at high privileges 
* Open source: https://github.com/GoogleCloudPlatform/guest-agent
* Operating system: Windows, Linux

​	
