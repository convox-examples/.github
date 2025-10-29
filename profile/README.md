<table>
  <tr>
    <td><img src="https://convox.com/images/logo.png" alt="Convox Logo"></td>
    <td><img src="https://convox.com/images/banner.png" alt="Convox Examples Banner"></td>
  </tr>
</table>

<br>

# Convox Examples

A comprehensive collection of **example applications** demonstrating how to deploy various languages, frameworks, and popular applications on [Convox](https://convox.com). Each example includes production-ready `convox.yml` configurations, optimized Dockerfiles, and best practices for deployment.

## Why Convox Examples?

These examples demonstrate the simplicity of deploying applications on Convox, whether you're using **Convox Cloud** for a fully-managed experience or your own **Convox Rack** for complete infrastructure control. Each example is:

- **Production-Ready**: Configured with health checks, scaling, and proper resource allocation
- **Well-Documented**: Includes detailed READMEs with deployment instructions
- **Best Practices**: Follows Docker and Convox best practices for optimal performance
- **Framework-Specific**: Tailored configurations for each language and framework
- **Quick to Deploy**: Get running in minutes with simple commands

## Quick Start

### Deploy to Convox Cloud

```bash
# Clone an example
$ git clone https://github.com/convox-examples/nodejs.git
$ cd nodejs

# Deploy to Convox Cloud
$ convox cloud apps create myapp -i machine-name
$ convox cloud deploy -a myapp -i machine-name
```

### Deploy to Convox Rack

```bash
# Clone an example
$ git clone https://github.com/convox-examples/rails.git
$ cd rails

# Deploy to your Rack
$ convox apps create myapp
$ convox deploy -a myapp
```

## 📚 Available Examples

### Languages & Runtimes

| Example | Description | Key Features |
|---------|-------------|--------------|
| [**Node.js**](https://github.com/convox-examples/nodejs) | Express.js application | Multi-stage builds, Health checks, Auto-scaling |
| [**PHP**](https://github.com/convox-examples/php) | PHP application | Apache/Nginx, Composer, Laravel/Symfony ready |
| [**Deno**](https://github.com/convox-examples/deno) | Deno runtime | TypeScript support, Secure by default |
| [**.NET Core**](https://github.com/convox-examples/dotnet-core) | C# applications | ASP.NET Core, Entity Framework, Multi-stage builds |

### Frameworks

#### Backend Frameworks
| Framework | Description | Features |
|-----------|-------------|----------|
| [**Django**](https://github.com/convox-examples/django) | Python web framework | PostgreSQL integration, Static files, Migrations |
| [**Rails**](https://github.com/convox-examples/rails) | Ruby on Rails | PostgreSQL, Redis, Sidekiq, Asset pipeline |

#### Frontend Frameworks
| Framework | Description | Features |
|-----------|-------------|----------|
| [**Next.js**](https://github.com/convox-examples/nextjs) | React framework | SSR, SSG, API routes, Optimized builds |
| [**Svelte**](https://github.com/convox-examples/Svelte) | Svelte/SvelteKit | Adapter-node, Static builds, Minimal runtime |
| [**Gatsby**](https://github.com/convox-examples/gatsby) | Static site generator | GraphQL, Progressive images, Plugin ecosystem |
| [**Gatsby + Contentful**](https://github.com/convox-examples/gatsby-contentful) | Gatsby with CMS | Contentful integration, Dynamic content, Webhooks |

### Web Servers

| Server | Use Case | Configuration |
|--------|----------|---------------|
| [**Apache httpd**](https://github.com/convox-examples/httpd) | Web server | .htaccess, mod_rewrite, SSL configuration |

### AI & Machine Learning

| Application | Description | Features |
|-------------|-------------|----------|
| [**LLM GPU API**](https://github.com/convox-examples/llm-gpu-api) | GPU-accelerated LLM API | CUDA support, Model serving, Auto-scaling |
| [**Llama2 Chatbot**](https://github.com/convox-examples/llama2-convox-chatbot) | Llama2-powered chatbot | Conversational AI, GPU optimization, WebSocket support |

### Popular Applications

| Application | Category | Features |
|-------------|----------|----------|
| [**n8n**](https://github.com/convox-examples/n8n) | Workflow Automation | PostgreSQL backend, Webhook support, 400+ integrations, User authentication |

## 🚀 Example Structure

Each example repository follows a consistent structure:

```
example-app/
├── README.md           # Deployment instructions & documentation
├── convox.yml          # Convox application manifest
├── Dockerfile          # Optimized container configuration
├── docker-compose.yml  # Local development setup (optional)
├── .env.example        # Environment variables template
├── src/                # Application source code
└── test/               # Test files
```

### Standard convox.yml Pattern

```yaml
environment:
  - NODE_ENV=production
  
resources:
  database:
    type: postgres
    options:
      storage: 10
      
services:
  web:
    build: .
    port: 3000
    health: /health
    scale:
      count: 1-10
      targets:
        cpu: 70
        memory: 90
    resources:
      - database
      
  worker:
    build: .
    command: npm run worker
    scale:
      count: 1-5
    resources:
      - database
```

## 📖 Documentation & Resources

### Getting Started
- [Get Started Free](https://console.convox.com/signup)
- [Convox Documentation](https://docs.convox.com/getting-started/introduction)
- [CLI Installation](https://docs.convox.com/installation/cli)
- [Your First Deployment](https://docs.convox.com/getting-started/introduction/#deploy-a-sample-app)

### Learn More
- [convox.yml Reference](https://docs.convox.com/configuration/convox-yml)
- [Environment Variables](https://docs.convox.com/configuration/environment)
- [Scaling Applications](https://docs.convox.com/deployment/scaling)
- [Custom Domains](https://docs.convox.com/deployment/custom-domains)
- [SSL Certificates](https://docs.convox.com/deployment/ssl)
- [CI/CD Workflows](https://docs.convox.com/deployment/workflows)

### Video Tutorials
- [Convox Academy Playlist](https://www.youtube.com/playlist?list=PL3w2iTa7QRGP48BP0NNgsLWCjMS9v-0go)
- [Getting Started Video](https://youtu.be/gbY0ZUKf1L8)
- [Deployment Tutorial](https://youtu.be/8QSt4-fiPXU)
- [CI/CD Setup](https://youtu.be/LogSDkIGZm0)

## 🤝 Contributing

We welcome contributions! To add or improve an example:

1. **Fork the repository** you want to contribute to
2. **Create a feature branch** (`git checkout -b add-new-example`)
3. **Make your changes** following the existing patterns
4. **Test your deployment** on both Convox Cloud and Rack
5. **Submit a Pull Request** with a clear description

### Guidelines for New Examples

- Include a comprehensive README with deployment instructions
- Provide both development and production configurations
- Follow Docker best practices (multi-stage builds, small images)
- Include health checks and proper scaling configuration
- Add environment variable documentation
- Test on multiple cloud providers when possible

### Requesting New Examples

Can't find what you're looking for? [Open an issue](https://github.com/convox-examples/examples/issues) to request a new example. Please include:

- The technology/framework you'd like to see
- Your use case and requirements
- Any specific configuration challenges

## 🌟 Featured Examples

### Example: AI-Powered Application

Deploy a GPU-accelerated AI application:

```bash
# Clone the LLM API example
$ git clone https://github.com/convox-examples/llm-gpu-api.git
$ cd llm-gpu-api

# Review the GPU configuration
$ cat convox.yml

# Deploy with GPU support
$ convox deploy -a my-llm-api
```

This example demonstrates:
- GPU resource allocation
- Model serving at scale
- Optimized inference
- Auto-scaling based on load

### Example: Modern Web Application with Rails

Deploy a full-featured Rails application:

```bash
# Clone the Rails example
$ git clone https://github.com/convox-examples/rails.git
$ cd rails

# Deploy the complete stack
$ convox deploy -a my-rails-app
```

Features:
- Rails web application
- PostgreSQL database
- Redis for caching/ActionCable
- Sidekiq background jobs
- Asset pipeline optimization

### Example: Workflow Automation with n8n

Deploy your own workflow automation platform:

```bash
# Clone the n8n example
$ git clone https://github.com/convox-examples/n8n.git
$ cd n8n

# Deploy n8n
$ convox deploy -a my-n8n
```

Includes:
- PostgreSQL for persistent storage
- Webhook support with SSL
- User authentication
- 400+ service integrations

## 💬 Community & Support

### Get Help
- [Community Forum](https://community.convox.com)
- [GitHub Discussions](https://github.com/convox/convox/discussions)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/convox)

### Stay Updated
- [Website](https://convox.com)
- [Blog](https://convox.com/blog)
- [Twitter](https://twitter.com/goconvox)
- [LinkedIn](https://linkedin.com/company/convox)

### Support
- Documentation: [docs.convox.com](https://docs.convox.com)
- Enterprise: [convox.com/enterprise](https://convox.com/enterprise)
- Community: [community.convox.com](https://community.convox.com)

## 📄 License

All examples are provided under the [Apache 2.0 License](LICENSE).

---

<p align="center">
  <strong>Deploy with confidence using Convox</strong><br>
  The Platform-as-a-Service that puts you in control
</p>

<p align="center">
  <a href="https://console.convox.com/signup">Get Started Free</a> •
  <a href="https://docs.convox.com">Documentation</a> •
  <a href="https://github.com/convox/convox">Main Repository</a>
</p>