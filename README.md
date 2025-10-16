# AWS EKS Terraform Project

This project creates an Amazon EKS cluster on AWS using Terraform.

## Features
- AWS EKS Cluster with managed node groups.
- Cluster addons: `vpc-cni`, `kube-proxy`, `coredns`.
- VPC with public, private, and intra subnets.
- Node group with SPOT instances for cost optimization.
- Modular Terraform setup for scalability.
- Environment tagging: `dev`, `staging`, `prod`.


## Prerequisites

- **Terraform** (v1.0+) - [Download here](https://www.terraform.io/downloads)
- **AWS CLI** (v2.0+) - [Install guide](https://aws.amazon.com/cli/)
- **kubectl** - [Install guide](https://kubernetes.io/docs/tasks/tools/)
- **AWS Account** with appropriate IAM permissions

Configure AWS credentials:
```bash
aws configure
```

## Clone the Repository

```bash
git clone <repository-url>
cd <project-directory>
```

## Usage

### Initialize Terraform

```bash
terraform init
```

### Plan Infrastructure

```bash
terraform plan
```

### Create Infrastructure

```bash
terraform apply
```

Type `yes` when prompted. Cluster creation takes 15-20 minutes.

### Configure kubectl

```bash
aws eks update-kubeconfig --region us-east-2 --name tws-eks-cluster
kubectl get nodes
```

### Deploy Applications

```bash
kubectl apply -f your-deployment.yaml
kubectl get pods
kubectl get services
```

### Destroy Infrastructure

```bash
terraform destroy
```

Type `yes` when prompted.

## Terraform Commands

| Command | Description |
|---------|-------------|
| `terraform init` | Initialize and download providers |
| `terraform plan` | Preview changes |
| `terraform apply` | Create/update resources |
| `terraform destroy` | Delete all resources |
| `terraform state list` | List all resources |

## Configuration

Edit `variables.tf` to customize settings like region, cluster name, and instance types.

## Author

**Saeedullah Shaikh**
- GitHub: [@Saeedullahshaikh](https://github.com/Saeedullahshaikh)

## License

MIT License
