# 🔄 Crew Sync Agent

**Dynamic Team Collaboration MCP Server for Smithery**

## 🌟 Overview

Crew Sync Agent is a flexible, dynamic team collaboration system built for the Model Context Protocol (MCP). Unlike traditional fixed-team approaches, it allows for dynamic team composition and real-time synchronization of crew members for various projects.

## ✨ Key Features

- **🔄 Dynamic Team Sync**: Flexible team composition for project-specific optimization
- **👥 Scalable Teams**: Support for up to 10 dynamic team members
- **🎯 Priority-Based**: Task prioritization (Low/Medium/High/Urgent)
- **🔐 Secure**: Environment variable-based API key management
- **⚡ Real-time**: MCP protocol-based instant team synchronization

## 🏗️ Default Crew (Expandable)

- **🎯 Taylor**: Team Coordinator - Strategic planning & project coordination
- **⚡ Jordan**: Tech Engineer - Full-stack development & DevOps  
- **💡 Riley**: Product Strategist - UX research & feature planning
- **📊 Casey**: Data Specialist - ML, analytics & visualization
- **🏗️ Morgan**: System Architect - System design & scalability
- **🎨 Avery**: Design Lead - Interface design & prototyping

> **Note**: Team composition is completely dynamic and can be adjusted based on project requirements.

## 🛠️ Available Tools

### `sync_crew` - Synchronize Team Members

```json
{
  "task": "Task description",
  "crew_members": ["Taylor", "Jordan", "Riley"], // optional
  "priority": "high" // low/medium/high/urgent
}
```

### `add_crew_member` - Add New Team Member

```json
{
  "name": "New member name",
  "role": "Role and expertise description"
}
```

### `list_crew` - List Current Team

```json
{} // no parameters needed
```

### `echo` - Connection Test

```json
{
  "text": "Test message"
}
```

## 🚀 Quick Start

### Local Testing

```bash
python test_crew_sync.py
```

### Smithery Deployment

1. Create GitHub repository
2. Deploy to Smithery: `smithery deploy https://github.com/username/crew-sync-agent`
3. Configure environment variables in Smithery dashboard

## 📋 Example Usage

### Web Development Project

```json
{
  "task": "React + Node.js e-commerce platform development",
  "crew_members": ["Jordan", "Riley", "Avery"],
  "priority": "high"
}
```

### Data Analysis Project

```json
{
  "task": "User behavior pattern analysis and prediction model",
  "crew_members": ["Casey", "Morgan"],
  "priority": "medium"
}
```

## 🔧 Configuration

### Environment Variables

- `MAX_CREW_SIZE`: Maximum team size (default: 10)
- `OPENAI_API_KEY`: OpenAI API key (optional)
- `ANTHROPIC_API_KEY`: Anthropic API key (optional)
- `AI_SERVICE`: Preferred AI service
- `MODEL_NAME`: Default model name

## 🛡️ Security

- ✅ API keys via environment variables only
- ✅ No hardcoded secrets in code
- ✅ Docker non-root user execution
- ✅ Sensitive files excluded via `.dockerignore`
- ✅ MCP protocol standard compliance

## 📞 Support

- **Issues**: GitHub Issues for bug reports and feature requests
- **Documentation**: See `README_SMITHERY.md` for detailed deployment guide
- **Community**: MCP developer community

---

**Crew Sync Agent**: Flexible and scalable AI team collaboration solution 🚀
