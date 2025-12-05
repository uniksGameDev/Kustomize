# Kustomize Example

## What this Kustomization Repository has
- Multi-environment configuration
- Database connections
- Service and deployment management
- Production-ready practices

## Directory Structure
```
.
├── base/                      # Base configuration
│   ├── deployment.yaml       # Web application deployment
│   ├── service.yaml         # Service definition
│   ├── configmap.yaml       # Base configuration
│   └── kustomization.yaml   # Base kustomization
└── overlays/                 # Environment-specific configs
    ├── development/         # Development environment
    │   └── kustomization.yaml
    └── production/          # Production environment
        └── kustomization.yaml
```

## Understanding the Setup

### Base Components
1. **Deployment**
   - Nginx web server
   - Configurable database connection
   - Resource definitions

2. **Service**
   - Load balancing
   - Port configuration
   - Service discovery

3. **ConfigMap**
   - Database connection settings
   - Environment-specific values

### Environment Overlays
1. **Development**
   - `dev-` prefix
   - Development database connection
   - Lower resource limits

2. **Production**
   - `prod-` prefix
   - Production database connection
   - Higher resource limits

## Try these commands once you're at home directory which contain /base and /overlays

1. View base configuration:
```bash
kubectl kustomize base/
```

2. View development configuration:
```bash
kubectl kustomize overlays/development/
```

3. View production configuration:
```bash
kubectl kustomize overlays/production/
```

4. Apply to development:
```bash
kubectl apply -k overlays/development/
```

## Best Practices Demonstrated

1. **Environment Separation**
   - Clear separation of environments
   - Environment-specific configurations
   - Consistent naming conventions

2. **Resource Management**
   - Proper service configuration
   - Database connection management
   - Resource limits and requests

3. **Configuration Management**
   - Environment variables
   - ConfigMap usage
   - Secret handling

4. **Naming Conventions**
   - Environment prefixes
   - Consistent resource names
   - Clear file structure

## Common Customizations
1. Resource limits
2. Replica counts
3. Environment variables
4. Service configurations
5. Database connections

## Production Considerations
1. Resource management
2. High availability
3. Security configurations
4. Monitoring and logging
5. Backup and disaster recovery
