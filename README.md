# Platform Engineering as the Actualization of DevOps: A Kratix Implementation - Workshop Lab

Welcome to the workshop! This lab provides a hands-on environment to explore platform engineering concepts using Kratix, Kubernetes, and modern cloud-native tools.

## 🚀 Quick Start

### Prerequisites

- Docker and Docker Compose installed on your system
- At least 4GB of available RAM
- Internet connection for downloading container images

### 1. Download the Lab

```bash
# Download the docker-compose file
curl -O https://raw.githubusercontent.com/mrdankuta/oscafest-lab/main/docker-compose.yaml

# Or clone the repository if available
git clone https://github.com/mrdankuta/oscafest-lab.git
cd oscafest-lab
```

### 2. Start the Lab Environment

```bash
# Start all services
docker-compose up -d

# Check that all containers are running
docker-compose ps
```

### 3. Access the Workshop Portal

Once the containers are running, open your web browser and navigate to:

**🌐 Workshop Portal: http://localhost:32535**

The portal will show the platform initialization progress. **Wait for the setup to complete** (typically 2-3 minutes) before proceeding with the workshop scenarios.

## 📋 Lab Components

The lab environment includes:

- **🏗️ Platform Cluster**: Kratix platform controller, MinIO storage, Istio service mesh
- **🔧 Development Cluster**: Simulated development environment  
- **🚀 Staging Cluster**: Simulated staging environment
- **🌐 Workshop Portal**: Interactive web interface with guided scenarios
- **📊 Observability Stack**: Grafana, Jaeger, Prometheus dashboards

## 🔐 Access Information

### Cluster Access
- **Username**: `root`
- **Password**: `root`

### Direct Cluster Access (Optional)

If you need direct access to the clusters via SSH:

```bash
# Access platform cluster
docker exec -it $(docker ps -q --filter "name=platform-cluster") bash

# Access development cluster  
docker exec -it $(docker ps -q --filter "name=dev-cluster") bash

# Access staging cluster
docker exec -it $(docker ps -q --filter "name=staging-cluster") bash
```

### Kubernetes Access

Each cluster has kubectl pre-configured:

```bash
# Inside any cluster container
kubectl get nodes
kubectl get pods --all-namespaces
```

## 🎯 Workshop Scenarios

The workshop includes two main learning paths accessible through the portal:

### 1. Platform Team Guide
- Install and configure Kratix platform components
- Deploy enterprise-grade Promises (platform capabilities)
- Set up observability and monitoring
- Configure multi-cluster destinations

### 2. Development Teams Guide  
- Request platform services through self-service
- Deploy compliant microservices with different compliance levels:
  - Basic compliance
  - PCI-DSS compliance  
  - GDPR compliance
- Observe automated policy enforcement
- Access service mesh observability dashboards

## 🔍 Monitoring and Observability

Once the platform is initialized, you can access:

- **Grafana**: http://localhost:3000 (admin/admin)
- **Jaeger**: http://localhost:16686
- **Prometheus**: http://localhost:9090

## 🛠️ Troubleshooting

### Platform Not Ready?
- Check the portal at http://localhost:32535 for initialization progress
- Wait for all components to show "ready" status (green checkmarks)
- Initial setup typically takes 2-3 minutes

### Container Issues?
```bash
# Check container status
docker-compose ps

# View logs for specific service
docker-compose logs portal
docker-compose logs platform-cluster

# Restart if needed
docker-compose restart
```

### Reset Environment?
```bash
# Stop and remove all containers
docker-compose down

# Remove volumes (complete reset)
docker-compose down -v

# Start fresh
docker-compose up -d
```

## 📚 Learning Objectives

By the end of this workshop, you will understand:

- **Platform Engineering Fundamentals**: Core concepts and benefits
- **Kratix Platform Controller**: How to build self-service platforms
- **Promise-Based Architecture**: Defining and consuming platform capabilities
- **GitOps Workflows**: Automated deployment and configuration management
- **Service Mesh Integration**: Istio for observability and security
- **Multi-Cluster Management**: Deploying across development and staging environments
- **Compliance Automation**: Automated policy enforcement and governance

## 🏁 Getting Started

1. ✅ Start the lab environment: `docker-compose up -d`
2. ✅ Open the portal: http://localhost:32535
3. ✅ Wait for platform initialization to complete
4. ✅ Follow the **Platform Team Guide** to set up the platform
5. ✅ Switch to **Development Teams Guide** to experience self-service consumption
6. ✅ Explore observability dashboards and monitoring tools

## 💡 Tips

- **Terminal Sessions**: The portal preserves terminal sessions when navigating between scenarios
- **Real-Time Updates**: Status updates refresh every 10 seconds automatically
- **Copy-Paste**: Use the copy buttons in code blocks for easy command execution
- **Multiple Tabs**: You can open multiple browser tabs to compare different views

## 🆘 Support

If you encounter issues during the workshop:

1. Check the troubleshooting section above
2. Review container logs for error messages
3. Ensure your system meets the prerequisites
4. Try resetting the environment if problems persist

---

**Happy Platform Engineering! 🚀**

*This lab demonstrates enterprise-grade platform engineering patterns using open-source tools and real-world scenarios.*
