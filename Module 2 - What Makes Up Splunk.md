## **Module 2: What Makes Up Splunk**

### **Core Components and Environments Overview**

* Introduction to Splunk's architecture  
* Key focus: The "Big Three" components  
* Deployment types and scaling with clustering

### **What Makes Up Splunk?**

* Covers core components of Splunk  
* Explains different environments and deployments  
* Brief introduction to clustering for scalability

### **Core Splunk Components**

* **Forwarders**: Collect and forward raw logs/data  
* **Indexers**: Process and index data for storage  
* **Search Heads**: Provide interface for searching using SPL (Search Processing Language)

### **Role of Forwarders**

* Collect raw logs from the host machine  
* Forward data to indexers  
* Types: Universal, heavy, intermediary (simplified as "forwarder" for certification)

### **How Indexers Work**

* Process incoming raw data  
* Store in time-based buckets (directories grouped by event time)  
* Analogy: Like writing lines on a page sequentially until full  
* Enables efficient time-based searching

### **Role of Search Heads (SH)**

* User interface for crafting and running SPL searches  
* Send queries to indexers (e.g., search for specific indexes)  
* Indexers perform the actual data retrieval and processing

### **Standalone Environment**

* Single Splunk instance handling all roles (search head \+ indexer)  
* Common for local installations (e.g., on a laptop)  
* No forwarders needed; configure inputs directly (e.g., monitor logs or upload files)

### **Basic Environment**

* Forwarders on remote machines collect data  
* Send to a central Splunk server  
* Central server acts as both search head and indexer

### **Multi-Instance Environment**

* Typical for large production setups  
* Functional separation:  
  * Dedicated forwarders for collection  
  * Dedicated indexers for processing/storage  
  * Dedicated search heads for querying  
* Roles can be combined if needed

### **Clustering**

* **Search Head Clustering**: Minimum 3 replicas for reliability and capacity  
* **Indexer Clustering**: Data replication to prevent loss on failure  
* Management tools: Deployer (for search heads), deployment server (for many forwarders)

### **Summary**

* Core roles: Forwarders (collect), Indexers (process/store in buckets), Search Heads (query)  
* Deployments scale from standalone → basic → multi-instance → clustered  
* Focus on efficiency (time-based buckets) and high availability in production

