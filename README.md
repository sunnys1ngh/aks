# aks
# sunny singh

Azure Kubernetes Services

A collection of configuration files for building microsservices in the cloud , specifically on Azure

# Help

az aks create --help

Command
    az aks create : Create a new managed Kubernetes cluster.


Examples
    Create a Kubernetes cluster with an existing SSH public key.
        az aks create -g MyResourceGroup -n MyManagedCluster --ssh-key-value /path/to/publickey

    Create a Kubernetes cluster with a specific version.
        az aks create -g MyResourceGroup -n MyManagedCluster --kubernetes-version 1.16.9

    Create a Kubernetes cluster with a larger node pool.
        az aks create -g MyResourceGroup -n MyManagedCluster --node-count 7

    Create a kubernetes cluster with k8s 1.13.9 but use vmas.
        az aks create -g MyResourceGroup -n MyManagedCluster --kubernetes-version 1.16.9 --vm-set-
        type AvailabilitySet

    Create a kubernetes cluster with default kubernetes version, default SKU load balancer
    (Standard) and default vm set type (VirtualMachineScaleSets).
        az aks create -g MyResourceGroup -n MyManagedCluster

    Create a kubernetes cluster with standard SKU load balancer and two AKS created IPs for the load
    balancer outbound connection usage.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-managed-outbound-ip-
        count 2

    Create a kubernetes cluster with a standard SKU load balancer, with two outbound AKS managed IPs
    an idle flow timeout of 5 minutes and 8000 allocated ports per machine
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-managed-outbound-ip-
        count 2 --load-balancer-idle-timeout 5 --load-balancer-outbound-ports 8000

    Create a kubernetes cluster with standard SKU load balancer and use the provided public IPs for
    the load balancer outbound connection usage.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-outbound-ips <ip-
        resource-id-1,ip-resource-id-2>

    Create a kubernetes cluster with standard SKU load balancer and use the provided public IP
    prefixes for the load balancer outbound connection usage.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-outbound-ip-prefixes
        <ip-prefix-resource-id-1,ip-prefix-resource-id-2>

    Create a kubernetes cluster with basic SKU load balancer and AvailabilitySet vm set type.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-sku basic --vm-set-type
        AvailabilitySet

    Create a kubernetes cluster with authorized apiserver IP ranges.
        az aks create -g MyResourceGroup -n MyManagedCluster --api-server-authorized-ip-ranges
        193.168.1.0/24,194.168.1.0/24,195.168.1.0

    Create a kubernetes cluster which enables managed identity.
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-managed-identity

    Create a kubernetes cluster with userDefinedRouting, standard load balancer SKU and a custom
    subnet preconfigured with a route table
        az aks create -g MyResourceGroup -n MyManagedCluster --outbound-type userDefinedRouting
        --load-balancer-sku standard --vnet-subnet-id customUserSubnetVnetID

    Create a kubernetes cluster with supporting Windows agent pools.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-sku Standard --network-
        plugin azure --windows-admin-username azure --windows-admin-password 'replacePassword1234$'

    Create a kubernetes cluster with supporting Windows agent pools with AHUB enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --load-balancer-sku Standard --network-
        plugin azure --windows-admin-username azure --windows-admin-password 'replacePassword1234$'
        --enable-ahub

    Create a kubernetes cluster with managed AAD enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-aad --aad-admin-group-object-
        ids <id-1,id-2> --aad-tenant-id <id>

    Create a kubernetes cluster with server side encryption using your owned key.
        az aks create -g MyResourceGroup -n MyManagedCluster --node-osdisk-diskencryptionset-id
        <disk-encryption-set-resource-id>

    Create a kubernetes cluster with ephemeral OS enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --node-osdisk-type Ephemeral --node-
        osdisk-size 48

    Create a kubernetes cluster with EncryptionAtHost enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-encryption-at-host

    Create a kubernetes cluster with UltraSSD enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-ultra-ssd

    Create a kubernetes cluster with Azure RBAC enabled.
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-aad --enable-azure-rbac

    Create a kubernetes cluster with custom control plane identity and kubelet identity.
        az aks create -g MyResourceGroup -n MyManagedCluster --assign-identity <control-plane-
        identity-resource-id> --assign-kubelet-identity <kubelet-identity-resource-id>

    Create a kubernetes cluster in the Edge Zone.
        az aks create -g MyResourceGroup -n MyManagedCluster --location <location> --kubernetes-
        version 1.20.7 --edge-zone <edge-zone-name>

    Create a kubernetes cluster with a specific OS SKU
        az aks create -g MyResourceGroup -n MyManagedCluster --os-sku Ubuntu

    Create a kubernetes cluster with custom tags
        az aks create -g MyResourceGroup -n MyManagedCluster --tags "foo=bar" "baz=qux"

    Create a kubernetes cluster with custom headers
        az aks create -g MyResourceGroup -n MyManagedCluster --aks-custom-headers WindowsContainerRu
        ntime=containerd,AKSHTTPCustomFeatures=Microsoft.ContainerService/CustomNodeConfigPreview

    Create a kubernetes cluster with FIPS-enabled OS
        az aks create -g MyResourceGroup -n MyManagedCluster --enable-fips-image

    create a kubernetes cluster with a snapshot id.
        az aks create -g MyResourceGroup -n MyManagedCluster --kubernetes-version 1.20.9 --snapshot-
        id "/subscriptions/00000/resourceGroups/AnotherResourceGroup/providers/Microsoft.ContainerSe
        rvice/snapshots/mysnapshot1"

To search AI knowledge base for examples, use: az find "az aks create"