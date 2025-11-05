---
title: Azure
description: >
  Azure Cloud Provider
categories: [Cloud Provider]
tags: [azure, ha, managed, core]
---

{{% pageinfo %}}
Azure support for Self-Managed and Managed Kubernetes Clusters
{{% /pageinfo %}}

{{% alert color="warning" title="Caution" %}}
Azure credentials are required to access clusters. These credentials are sensitive information and must be kept secure.
{{% /alert %}}

## Azure Credential Requirements

### Subscription ID
Your Azure subscription identifier can be found in your subscription details.

![azure-subscription](/img/azure/azure-subs-id.png)

### Tenant ID
Located in the Azure Dashboard, which provides access to all required credentials.

![azure-dashboard](/img/azure/azure-dashboard.png)

To locate your Tenant ID:

![](/img/azure/azure-tenantid.png)

### Client ID (Application ID)
Represents the identifier of your registered application.

Steps to create:
1. Navigate to App Registrations

![](/img/azure/azure-app-reg.png)

2. Register a new application
![](/img/azure/azure-create-app-reg.png)

3. Obtain the Client ID
![](/img/azure/azure-clientid.png)

### Client Secret
Authentication key for your registered application.

Steps to generate:
1. Access secret creation
![create app secret](/img/azure/azure-client-secret1.png)

2. Configure secret settings
![after-click](/img/azure/azure-client-secret.png)

3. Save the generated secret
![copy-secret](/img/azure/azure-client-secret2.png)

### Role Assignment
Configure application permissions:

1. Navigate to Subscriptions > Access Control (IAM)
2. Select "Role Assignment"
3. Click "Add > Add Role Assignment"
4. Create new role and specify the application name
5. Configure desired permissions

![role-assign-app](/img/azure/azure-role-app.png)

You can create a custom Role and then attach to this app if you want fine grained permission **Beta**

```json
{
    "properties": {
        "roleName": "Ksctl",
        "description": "Kubmin.ksctl.com",
        "assignableScopes": [
            "/subscriptions/<subscription_id>"
        ],
        "permissions": [
            {
                "actions": [
                    "Microsoft.ContainerService/register/action",
                    "Microsoft.ContainerService/unregister/action",
                    "Microsoft.ContainerService/operations/*",
                    "Microsoft.ContainerService/managedClusters/*",
                    "Microsoft.ContainerService/managedclustersnapshots/*",
                    "Microsoft.ContainerService/containerServices/*",
                    "Microsoft.ContainerService/deploymentSafeguards/*",
                    "Microsoft.ContainerService/locations/*",
                    "Microsoft.ContainerService/snapshots/*",

                    "Microsoft.Network/register/action",
                    "Microsoft.Network/unregister/action",
                    "Microsoft.Network/checkTrafficManagerNameAvailability/action",
                    "Microsoft.Network/internalNotify/action",
                    "Microsoft.Network/getDnsResourceReference/action",
                    "Microsoft.Network/queryExpressRoutePortsBandwidth/action",
                    "Microsoft.Network/checkFrontDoorNameAvailability/action",
                    "Microsoft.Network/privateDnsZonesInternal/action",
                    "Microsoft.Network/adminNetworkSecurityGroups/*",
                    "Microsoft.Network/applicationGateways/*",
                    "Microsoft.Network/ApplicationGatewayWebApplicationFirewallPolicies/*",
                    "Microsoft.Network/applicationGatewayAvailableRequestHeaders/*",
                    "Microsoft.Network/applicationGatewayAvailableResponseHeaders/*",
                    "Microsoft.Network/applicationGatewayAvailableServerVariables/*",
                    "Microsoft.Network/applicationGatewayAvailableSslOptions/*",
                    "Microsoft.Network/applicationGatewayAvailableWafRuleSets/read",
                    "Microsoft.Network/applicationSecurityGroups/*",
                    "Microsoft.Network/operations/*",
                    "Microsoft.Network/azurefirewalls/*",
                    "Microsoft.Network/azureFirewallFqdnTags/read",
                    "Microsoft.Network/dnsResolvers/*",
                    "Microsoft.Network/dnszones/*",
                    "Microsoft.Network/dnsoperationresults/*",
                    "Microsoft.Network/firewallPolicies/*",
                    "Microsoft.Network/gatewayLoadBalancerAliases/*",
                    "Microsoft.Network/ipAllocations/*",
                    "Microsoft.Network/ipGroups/*",
                    "Microsoft.Network/loadBalancers/*",
                    "Microsoft.Network/natGateways/*",
                    "Microsoft.Network/networkInterfaces/*",
                    "Microsoft.Network/virtualNetworks/*",
                    "Microsoft.Network/virtualNetworkGateways/read",
                    "Microsoft.Network/virtualNetworkGateways/write",
                    "Microsoft.Network/virtualNetworkGateways/delete",
                    "microsoft.network/virtualnetworkgateways/*",
                    "Microsoft.Network/virtualRouters/*",

                    "Microsoft.Resources/checkResourceName/action",
                    "Microsoft.Resources/changes/*",
                    "Microsoft.Resources/deployments/*",
                    "Microsoft.Resources/deploymentScripts/*",
                    "Microsoft.Resources/deploymentStacks/*",
                    "Microsoft.Resources/locations/*",
                    "Microsoft.Resources/providers/*",
                    "Microsoft.Resources/links/*",
                    "Microsoft.Resources/resources/*",
                    "Microsoft.Resources/subscriptions/*",
                    "Microsoft.Resources/subscriptions/locations/*",
                    "Microsoft.Resources/subscriptions/resourceGroups/*",
                    "Microsoft.Resources/subscriptions/providers/*",
                    "Microsoft.Resources/subscriptions/operationresults/*",
                    "Microsoft.Resources/subscriptions/resources/*",
                    "Microsoft.Resources/subscriptions/tagNames/*",
                    "Microsoft.Resources/subscriptionRegistrations/*",
                    "Microsoft.Resources/tags/*",
                    "Microsoft.Resources/templateSpecs/*",
                    "Microsoft.Resources/templateSpecs/versions/*",
                    "Microsoft.Resources/tenants/*",

                    "Microsoft.ManagedIdentity/register/*",
                    "Microsoft.ManagedIdentity/operations/*",
                    "Microsoft.ManagedIdentity/identities/*",
                    "Microsoft.ManagedIdentity/userAssignedIdentities/*"
                ],
                "notActions": [],
                "dataActions": [],
                "notDataActions": []
            }
        ]
    }
}
```


## Authentication Methods

### Command Line Interface
```bash
ksctl configure cloud
```

## Available Cluster Types

### Self-Managed Clusters
Self-managed clusters with the following components:
- Distributed etcd database instances
- HAProxy load balancer for control plane high availability
- Multiple control plane nodes
- Worker nodes

Bootstrap options:
- k3s (lightweight Kubernetes distribution)
- kubeadm (official Kubernetes bootstrap tool)

### Azure Kubernetes Service (AKS)
Fully managed Kubernetes service by Azure.

## Cluster Management Features

{{% alert title="Cluster Operations" %}}

### Managed Clusters (AKS)
- Create and delete operations
- Cluster switching
- Infrastructure updates currently not supported

### High Availability Clusters
- Worker node scaling (add/remove)
- Secure SSH access to all components:
  - Database nodes
  - Load balancer
  - Control plane nodes
  - Worker nodes
- Protected by SSH key authentication
- Public access enabled

{{% /alert %}}


## Looking for CLI Commands?

All CLI commands mentioned in this documentation have detailed explanations in our command reference guide.

{{% alert title="CLI Reference" %}}
👉 Check out our comprehensive [CLI Commands Reference](/docs/reference/) for:
- Detailed command syntax
- Usage examples
- Available options and flags
- Common use cases
{{% /alert %}}
