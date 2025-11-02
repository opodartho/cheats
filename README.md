## My DevOps Cheat Sheet

A personal reference of commonly used commands.

---

### Table of Contents

- [Linux Basics](#linux-basics)
- [Docker / Posman](#docker--podman)
- [Kubernetes (kubectl)](#kubernetes-kubectl)
- [PostgreSQL](#postgresql)
- [Networking](#networking)
- [System Info](#system-info)

### Linux Basics

```bash
# Show disk usage in human-redable form
df -h

# View listening ports
ss -tuln
```

### Kubernetes (kubectl)

```bash
# Get all pods in all namespaces
kubectl get pods -A

# Describe a pod
kubectl describe pod <pod_name> -n <namespace>

# View logs
kubectl logs <pod_name> -n <namespace>

# Apply a YAML file
kubectl apply -f deployment.yaml

# Port forward
kubectl port-forward svc/my-service 8080:80 -n my-namespace
```

### PostgreSQL

```bash
# List all users
\du

# List all schemas
\dn

# List all tables in a schema
\dt <schema>.*

# Create database
createdb -U postgres <dbName>

# Copy a database from existing (new db must be created before)
pg_dumb -U postgres <oldDB> | psql -U postgres <newDB>

# Change owner of a database
ALTER DATABASE mydb OWNER TO new_owner;
```

### Networking

```bash
# TCP Port Scan
nmap -nP 22,80,443 <target>

# Top common ports
nmap -nP --top-ports 100 <target>

# Scan for UDP Ports
sudo nmap -sU -Pn -p 53,123 <target>
```

### System Info

```bash
# Check OS version
cat /etc/os-release

# Show kernel info
uname -r

# Check uptime
uptime
```
