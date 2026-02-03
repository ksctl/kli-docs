---
title: Core Manager
description: >
  The Component of kli responsible for managing Cloud controller and Distribution controller. It has multiple types of managers
categories: [Examples]
---

{{% pageinfo %}}
It is responsible for managing client requests and calls the corresponding controller
{{% /pageinfo %}}

## Types

### ManagerClusterkli
`Role`: Perform kli **getCluster**, **switchCluster**

### ManagerClusterKubernetes
`Role`: Perform kli **addApplicationAndCrds**
Currently to be used by machine to machine not by kli cli

### ManagerClusterManaged
`Role`: Perform kli **createCluster**, **deleteCluster**

### ManagerClusterSelfManaged
`Role`: Perform kli **createCluster**, **deleteCluster**, **addWorkerNodes**, **delWorkerNodes**
