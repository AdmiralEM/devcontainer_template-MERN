# MERN Stack DevContainer Template

A complete, portable development environment for MERN (MongoDB, Express, React, Node.js) applications using VS Code DevContainers.

## 🚀 Quick Start

### Prerequisites (Host Machine)
- VS Code with Dev Containers extension
- Docker Desktop
- Git / GitHub Desktop
- WSL2 (Windows only)

### Setup New Project
1. Clone this template repository
2. Open in VS Code
3. When prompted, click "Reopen in Container"
4. Wait for container to build and setup to complete
5. Start developing!

## 📁 Project Structure

```
.
├── .devcontainer/
│   ├── devcontainer.json       # Main devcontainer configuration
│   ├── docker-compose.yml      # Multi-service setup
│   ├── Dockerfile             # Custom development image
│   ├── scripts/               # Lifecycle scripts
│   └── mongo-init/            # MongoDB initialization
├── client/                    # React frontend
├── server/                    # Express backend
├── .env                       # Environment variables
├── .eslintrc.js              # ESLint configuration
├── .prettierrc               # Prettier configuration
└── package.json              # Root workspace configuration
```

## 🛠 Available Commands

### Development
- `npm run dev` - Start both client and server concurrently
- `npm run client` - Start React development server only
- `npm run server` - Start Express API server only

### Package Management
- `npm run install-all` - Install all dependencies (root, client, server)
- `npm run install-client` - Install client dependencies only
- `npm run install-server` - Install server dependencies only

### Production
- `npm run build` - Build React app for production

## 🌐 Port Mappings

| Port | Service | Description |
|------|---------|-------------|
| 3000 | Client | React development server |
| 5000 | Server | Express API server |
| 27017 | Database | MongoDB |

## 🗄 Database Configuration

### MongoDB Setup
- **Database**: `mern_dev`
- **Connection String**: `mongodb://localhost:27017/mern_dev`
- **Admin User**: `admin` / `password`
- **Dev User**: `dev_user` / `dev_password`

### VS Code MongoDB Extension
The MongoDB VS Code extension is pre-configured. Connection settings:
- **Connection String**: `mongodb://dev_user:dev_password@localhost:27017/mern_dev`

## 🔧 Development Tools

### Pre-installed Extensions
- **Language Support**: TypeScript, JavaScript ES6+ snippets
- **React**: React snippets, auto-rename tags
- **Node.js**: Node.js development pack
- **Database**: MongoDB for VS Code
- **Code Quality**: ESLint, Prettier, Spell Checker
- **Git**: GitLens, GitHub integration
- **Utilities**: REST Client, Docker, Material Theme

### Code Quality
- **ESLint**: Configured for React + TypeScript
- **Prettier**: Automatic code formatting
- **Format on Save**: Enabled by default

## 📦 Volume Management

### Persistent Volumes
- `mongodb_data` - MongoDB data persists between container rebuilds
- `mern-node_modules` - Root node_modules cache
- `mern-client-node_modules` - Client node_modules cache

### Performance Optimization
Node modules are stored in Docker volumes for better performance and persistence.

## 🔄 Lifecycle Scripts

### Container Lifecycle
- **on-create**: Sets up project structure for new projects
- **update-content**: Updates global packages
- **post-create**: Installs all dependencies
- **post-start**: Displays helpful information

## 🛡 Environment Variables

### Default Environment (.env)
```bash
NODE_ENV=development
PORT=5000
CLIENT_PORT=3000
MONGODB_URI=mongodb://localhost:27017/mern_dev
JWT_SECRET=your_jwt_secret_here_change_in_production
```

### Customization
- Copy `.env` to `.env.local` for local overrides
- Never commit sensitive data to version control

## 🚨 Troubleshooting

### Container Won't Start
1. Ensure Docker Desktop is running
2. Check that required ports aren't in use
3. Try rebuilding the container: `Ctrl+Shift+P` → "Dev Containers: Rebuild Container"

### Dependencies Not Installing
1. Check internet connection inside container
2. Clear npm cache: `npm cache clean --force`
3. Delete node_modules volumes and rebuild

### MongoDB Connection Issues
1. Verify MongoDB service is running: `docker-compose ps`
2. Check connection string in `.env`
3. Ensure MongoDB is accessible on port 27017

### Performance Issues
1. Allocate more memory to Docker Desktop
2. Use volume mounts for node_modules (already configured)
3. Consider using Docker Desktop with WSL2 backend

## 🔄 Template Usage

### For New Projects
1. Clone this template
2. Update `package.json` name and description
3. Modify README.md for your project
4. Start developing!

### Updating Template
1. Make changes to `.devcontainer/` configuration
2. Test with a fresh container build
3. Update documentation
4. Commit changes

## 🎯 Best Practices

### Development Workflow
1. Always work inside the devcontainer
2. Use `npm run dev` for full-stack development
3. Commit `.devcontainer/` changes for team consistency
4. Use environment variables for configuration

### Git Workflow
1. `.devcontainer/` should be committed
2. `node_modules/` are ignored (handled by volumes)
3. Environment files (`.env.local`) should be gitignored

### Performance Tips
1. Use volume mounts for node_modules
2. Minimize container rebuilds
3. Keep Docker Desktop updated
4. Use WSL2 backend on Windows

## 🤝 Contributing

1. Fork the template repository
2. Create a feature branch
3. Test changes with a fresh container
4. Submit a pull request

## 📝 License

This template is provided as-is for development purposes. Choose your own license for your projects.

---

## 📚 Additional Resources

- [VS Code DevContainers Documentation](https://code.visualstudio.com/docs/devcontainers/containers)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [MERN Stack Tutorial](https://www.mongodb.com/languages/mern-stack-tutorial)
- [MongoDB Documentation](https://docs.mongodb.com/)

---

**Happy Coding! 🎉**
