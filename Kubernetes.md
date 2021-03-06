# Kubernetes Notes

* **Kubernetes:** Container orchestration platform.

* **Pod:** Abstraction over container.
  
  *  Usually 1 app/pod but can be more.
    
  *  Has separate IP(not of container).
    
  *  New IP on recreation.


*  **Service:** Unique name & Static cluster IP.
  
  *  Life cycle is not connected to pod.
    
*  **Ingress:** Manages external access to cluster.
  
*  **ConfigMap:** External config to the application.
  
*  **Secret:** Used to store secret data.
  
   * Base64 Encoded
    
*  **Nodes:**
  
  *  Worker Node: 
    *  Processes:
      *  Kubelet: Connect with master node.
      *  KubeProxy: Monitors and controls the connection of nodes.
      *  Container Runtime.
  *  Master Node:
    *  Processes: 
      *  API Server: Connect to worker nodes.
      *  Scheduler: Decides on which worker a pod should be scheduled by observing server loads.
      *  Controller Manager: Detect po states, and recreate if died/crashed.
      *  Etcd: Key-value store used to store information about clusters.

*  **Kubectl:** CLI to talk with API server of master node.

*  **Configuration File:** YAML script to perform operations in kubernetes.
  *  Parts: 
    *  Metadata: Data about data.
    *  Specifications: Main values.
    *  Status: Status about running process, generated by etcd.

*  **Project 1:** Mongo express with Mongo DB.
  *  File creation: MongoDB Dpl > MongoDB Int. Svc > MongoDB Secret > MongoDB ConfigMap > MongoExpress Dpl > MongoExpress Ext. Svc
  *  File deployment: MongoDB Secret > MongoDB Dpl > MongoDB Int. Svc > MongoDB ConfigMap > MongoExpress Dpl > MongoExpress Ext. Svc

*  **Namespaces:** Way to organize clusters into virtual sub-clusters.
    *  Characteristics: 
        *  ConfigMap & Secret of a namespace can't be accessed by another namespace.
        *  Service of a namespace can be accessed by another namespace.
        *  Volume & Node are global components i.e. they are not isolated under any namespace.
