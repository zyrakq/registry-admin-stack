# 🚀 Registry Admin Stack

SSO and web interface for Docker Distribution Registry with support for multiple authentication methods and SSL automation.

## 📦 Related Projects

This project works with [distribution-stack](https://github.com/zyrakq/distribution-stack) which provides the Docker Distribution Registry itself. Registry Admin Stack must be deployed **after** distribution-stack.

## 🧩 Components

### 🎛️ Registry Admin

**Location:** [`src/registry-admin/`](src/registry-admin/)

Web interface and OIDC/SSO provider for Docker Distribution Registry. Provides user management, image catalog browsing, and authentication services.

### 🔐 SSL Automation

#### [🔒 Let's Encrypt Manager](src/ssl-automation/letsencrypt-manager)

Automatic SSL certificate management from Let's Encrypt for production deployments.
[Learn more](src/ssl-automation/letsencrypt-manager/README.md).

#### [🏠 Step CA Manager](src/ssl-automation/step-ca-manager)

Local domain stack with trusted self-signed certificates for development environments.
[Learn more](src/ssl-automation/step-ca-manager/README.md).

## 🚀 Deployment Order

1. **First**: Deploy [distribution-stack](https://github.com/zyrakq/distribution-stack)
2. **Second**: Deploy registry-admin (this project)

⚠️ **Note**: With OIDC configuration, distribution will restart during the first ~20 seconds while registry-admin generates certificates and establishes trust.

## 🎯 Use Cases

- **🌐 Production**: Registry Admin + Let's Encrypt for public-facing registries
- **🏠 Internal Networks**: Registry Admin + Step CA for private/development environments
- **🔧 Development**: Registry Admin with port forwarding for local development

## 🚀 Quick Start

Each component has its own README with detailed setup instructions. Choose the certificate management solution that fits your deployment scenario.

## 📄 License

This project is dual-licensed under:

- [Apache License 2.0](LICENSE-APACHE)
- [MIT License](LICENSE-MIT)
