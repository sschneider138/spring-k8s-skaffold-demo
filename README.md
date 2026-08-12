# Information

### What's happening
- Spring Boot application is running in a container built by GoogleContainerTools `jib`.
- `k8s` directory defines the manifest files for postgres database and the Spring Boot application itself.
- `skaffold.yaml` defines the configuration for the `skaffold` tool. Skaffold is a tool for continuous development for Kubernetes. This, combined with Spring Boot dev tools and jib, allows for hot reload. Skaffold achieves this by...
  - Building Spring Boot app image.
  - Deploy PostgreSQL.
  - Deploy Spring Boot.
  - Port-forward localhost:8080 → Kubernetes service myapp:8080.
  - Watch your project.
  - Compile/sync changed Java classes.
  - Let Spring DevTools restart the application. 