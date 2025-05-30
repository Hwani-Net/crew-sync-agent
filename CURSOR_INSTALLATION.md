# 🎯 Cursor IDE Installation Guide for Crew Sync Agent

Complete setup guide for integrating **Crew Sync Agent** with Cursor IDE's MCP protocol.

## 📋 Prerequisites

- **Cursor IDE** (latest version recommended)
- **Python 3.8+** installed and accessible in PATH
- **Git** for repository management
- **Environment variables** configured (optional API keys)

## 🚀 Quick Setup

### 1. Clone Repository

```bash
git clone https://github.com/Hwani-Net/crew-sync-agent.git
cd crew-sync-agent
```

### 2. Install Dependencies

```bash
# Install Python dependencies
pip install -r requirements.txt

# Verify MCP server works
python test_crew_sync.py
```

### 3. Configure Cursor IDE

#### Option A: Auto-Configuration (Recommended)

Copy the provided configuration to your Cursor settings:

```bash
# Copy Cursor MCP configuration
cp cursor-mcp-config.json ~/.cursor/mcp-servers/crew-sync-agent.json
```

#### Option B: Manual Configuration

1. Open **Cursor IDE Settings** (Ctrl/Cmd + ,)
2. Navigate to **Extensions** → **MCP Servers**
3. Add new server with these settings:

```json
{
  "name": "crew-sync-agent",
  "displayName": "🔄 Crew Sync Agent", 
  "command": "python",
  "args": ["./mcp_server.py"],
  "cwd": "/path/to/crew-sync-agent",
  "env": {
    "MAX_CREW_SIZE": "10",
    "AI_SERVICE": "claude", 
    "MODEL_NAME": "claude-3-sonnet"
  }
}
```

### 4. Environment Variables (Optional)

Create `.env` file in the project root:

```env
# Optional API keys for enhanced features
OPENAI_API_KEY=your_openai_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
AI_SERVICE=claude
MODEL_NAME=claude-3-sonnet
MAX_CREW_SIZE=10
```

## 🛠️ Usage in Cursor

### Available MCP Tools

Once configured, these tools will be available in Cursor's command palette:

#### 🔄 **sync_crew** - Team Synchronization
```json
{
  "task": "Build React dashboard with authentication",
  "crew_members": ["Jordan", "Avery", "Riley"],
  "priority": "high"
}
```

#### 👥 **add_crew_member** - Expand Team
```json
{
  "name": "Alex",
  "role": "DevOps Engineer - CI/CD and infrastructure automation"
}
```

#### 📋 **list_crew** - View Current Team
```json
{}
```

#### 📡 **echo** - Test Connection
```json
{
  "text": "Testing Crew Sync Agent connection"
}
```

### Integration Examples

#### 1. **Project Planning**
- Use `sync_crew` to assemble optimal team for your project
- Specify task requirements and priority level
- Get team recommendations and synchronization status

#### 2. **Dynamic Team Management**
- Add specialists with `add_crew_member` as needs evolve
- View current team composition with `list_crew`
- Adapt team structure for different project phases

#### 3. **Real-time Collaboration**
- Teams sync instantly through MCP protocol
- Priority-based task handling (Low/Medium/High/Urgent)
- Cross-project team member utilization

## 🔧 Troubleshooting

### Common Issues

#### ❌ **"MCP server not found"**
```bash
# Verify Python path
which python
python --version

# Check if mcp_server.py is executable
python mcp_server.py --help
```

#### ❌ **"Permission denied"**
```bash
# Fix file permissions
chmod +x mcp_server.py

# Ensure Python can access the directory
ls -la mcp_server.py
```

#### ❌ **"Module not found"**
```bash
# Reinstall dependencies
pip install --upgrade -r requirements.txt

# Verify installation
python -c "import json, sys; print('Dependencies OK')"
```

### Debug Mode

Enable verbose logging for troubleshooting:

```json
{
  "env": {
    "DEBUG": "true",
    "LOG_LEVEL": "debug"
  }
}
```

## 🔄 Updates & Maintenance

### Keep Updated
```bash
# Pull latest changes
git pull origin main

# Update dependencies if needed
pip install --upgrade -r requirements.txt

# Test after updates
python test_crew_sync.py
```

### Configuration Refresh
```bash
# Restart Cursor IDE after configuration changes
# Or reload MCP servers from Command Palette:
# "MCP: Reload Servers"
```

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/Hwani-Net/crew-sync-agent/issues)
- **Documentation**: [Main README](./README.md)
- **Configuration Examples**: `cursor-mcp-config.json`
- **Testing**: Run `python test_crew_sync.py`

## 🎯 Next Steps

1. **Explore Tools**: Try each MCP tool in Cursor's command palette
2. **Customize Teams**: Add project-specific crew members
3. **Integrate Workflows**: Use with your existing Cursor projects
4. **Share Configurations**: Export settings for team members

---

**Crew Sync Agent**: Bringing dynamic team collaboration to your Cursor IDE workflow! 🚀
