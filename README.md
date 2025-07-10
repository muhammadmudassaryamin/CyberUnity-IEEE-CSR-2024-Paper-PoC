# Modelling Attack and Defense Scenarios on Federated Cyber Ranges

Cybersecurity threats are evolving rapidly, necessitating the creation of new scenarios to address these emerging threats. Cyber Ranges offer a solution by providing a platform to practice against these evolving threats and develop mitigation strategies. However, it is becoming increasingly difficult for a single Cyber Range to generate scenarios that keep pace with such rapid changes. Cyber Range federation offers a potential solution by connecting multiple Cyber Ranges, enabling them to share data, scenarios, and run exercises in a unified manner. This federation allows a broader audience to participate in cybersecurity training and education, enhancing their understanding of evolving threats. In this paper, we focus on operational cybersecurity scenarios and how they can be federated within our simulation environment. These scenario models help us plan cybersecurity exercises for future use. This federation involves several algorithms for merging operational networks, identifying attack paths, and calculating potential outcomes of scenarios.

Demo: [Link](https://muhammadmudassaryamin.github.io/CyberUnity-IEEE-CSR-2025-Paper-PoC/FNVA.html), Complimentary Network Creataor: [Link](https://muhammadmudassaryamin.github.io/CyberUnity-IEEE-CSR-2025-Paper-PoC/network-creator.html)


# Features
1. Network Visualization: Interactive network graph displaying nodes and edges, with tooltips showing node risk and vulnerabilities.
2. Critical Node Analysis: Identifies the top 10 critical nodes based on betweenness centrality, visualized in a bar chart.
3. Attack Path Analysis: Displays the top 5 high-risk attack paths with a highlight feature on the network graph.
4. Attack Simulation: Runs random walk simulations to identify frequently targeted nodes, shown in a bar chart.
5. Node Merging: Combines two nodes into a single node, updating network topology and attributes.

# Installation
Clone the Repository:
No backend server is required, as the application runs entirely in the browser. Open index.html directly in a modern web browser (e.g., Chrome, Firefox), but note that some features (e.g., file uploads) may be restricted due to browser security policies.

# Usage
In the "Upload JSON Files" section, upload three required JSON files:
1. vulnerability_database.json: Contains vulnerability data with CVSS scores.
2. network1.json: First network dataset with nodes and edges.
3. network2.json: Second network dataset with nodes and edges.

Click Load Files to process and merge the networks. A spinner indicates loading, and a success/error message appears.


# Example Workflow:
Upload sample JSON files (see File Format below).
Check the health score (e.g., 85/100).
Review automatic attack paths (e.g., node1 -> node2 -> node3, risk 12.5) and highlight them.
Apply a suggested patch (e.g., CVE-2023-1234 on node2) to reduce risk.
Download a report to share the analysis.

# The application requires three JSON files with specific structures:

vulnerability_database.json:
```json
{
  "vuln_id": { "cvss_score": number, ... },
  ...
}
```
Example:
```json
{
  "CVE-2023-1234": { "cvss_score": 7.5 },
  "CVE-2023-5678": { "cvss_score": 5.0 }
}
```
network1.json and network2.json:
```json
{
  "nodes": [
    { "id": string, "subnet": string, "vulnerabilities": [string], ... }
  ],
  "edges": [
    { "source": string, "target": string, ... }
  ]
}
```
Example:
```
{
  "nodes": [
    { "id": "node1", "subnet": "subnetA", "vulnerabilities": ["CVE-2023-1234"] },
    { "id": "node2", "subnet": "subnetB", "vulnerabilities": ["CVE-2023-5678"] }
  ],
  "edges": [
    { "source": "node1", "target": "node2" }
  ]
}
```
