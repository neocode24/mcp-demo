# MCP Demo Project

This repository demonstrates the configuration and usage of Model Context Protocol (MCP) servers with Cursor IDE.

## 🚀 MCP Servers Configured

### 1. **Upstash Context7** 
- **Purpose**: Library documentation and code examples
- **Features**: Access to 2000+ React code snippets, latest library versions, and API documentation
- **Package**: `@upstash/context7-mcp@latest`

### 2. **Supabase MCP**
- **Purpose**: Database management and authentication services
- **Features**: SQL queries, table management, user authentication, real-time logs
- **Package**: `supabase-mcp-server` (Python-based)

### 3. **GitHub CLI Integration** 
- **Purpose**: Repository and issue management via GitHub CLI
- **Features**: Repository operations, issue tracking, PR management, branch operations
- **Tool**: GitHub CLI (`gh` command) - No MCP server needed

## 📁 Configuration

### 🔒 Security Setup

**IMPORTANT**: Never commit actual API keys or tokens to version control!

1. **Copy the example configuration**:
   ```bash
   cp .cursor/mcp.example.json .cursor/mcp.json
   ```

2. **Edit `.cursor/mcp.json`** with your actual credentials:
   - Replace `your-upstash-context7-token-here` with your Upstash token
   - Replace `your-query-api-key-here` with your thequery.dev API key
   - Replace `your-project-ref-here` with your Supabase project reference
   - Replace `your-db-password-here` with your Supabase database password
   - Replace `your-service-role-key-here` with your Supabase service role key

3. **Setup GitHub CLI** (separate from MCP):
   ```bash
   # Install GitHub CLI (if not already installed)
   brew install gh  # macOS
   # or visit https://cli.github.com for other platforms
   
   # Login to GitHub
   gh auth login
   ```

4. **Verify `.cursor/mcp.json` is ignored by Git** (already configured in .gitignore)

### 📄 Configuration Files

- `.cursor/mcp.example.json` - Template configuration (safe to commit)
- `.cursor/mcp.json` - Your actual configuration (ignored by Git)

The configuration includes:
- Server commands and arguments
- Environment variables for authentication
- API keys and connection details

## 🛠️ Setup Instructions

1. **Install Required Dependencies**:
   ```bash
   # Install Python-based Supabase MCP server
   pipx install supabase-mcp-server
   ```

2. **Configure Environment Variables**:
   - `UPSTASH_CONTEXT7_TOKEN`: Your Upstash Context7 API token
   - `QUERY_API_KEY`: API key from thequery.dev
   - `SUPABASE_*`: Various Supabase configuration variables
   - `GITHUB_TOKEN`: GitHub Personal Access Token

3. **Restart Cursor IDE** to apply MCP server configurations

## 🧪 Testing Your Setup

### MCP Servers (via Cursor)
Once configured, you can test the MCP servers with prompts like:

- **Context7**: "Show me React hooks documentation"
- **Supabase**: "List all tables in my database"

### GitHub CLI (via Terminal)
Test GitHub CLI functionality directly:

```bash
# Test GitHub CLI authentication
gh auth status

# List your repositories
gh repo list

# Create a new repository
gh repo create my-new-repo --public --description "My new project"

# View repository issues
gh issue list

# Create a new issue
gh issue create --title "Bug report" --body "Description of the bug"
```

## 🔒 Security Notes

- All API keys and sensitive tokens are configured as environment variables
- Supabase MCP includes safety modes to prevent destructive operations
- GitHub CLI uses secure OAuth authentication (no manual token management required)
- `.gitignore` prevents accidental commit of sensitive configuration files

## 📚 Resources

- [Model Context Protocol Documentation](https://modelcontextprotocol.io/)
- [Cursor MCP Setup Guide](https://docs.cursor.com/context/mcp)
- [Upstash Context7](https://upstash.com/docs/context7)
- [Supabase MCP Server](https://github.com/alexander-zuev/supabase-mcp-server)
- [GitHub CLI Documentation](https://cli.github.com/manual/)

---

*This project demonstrates the power of integrating multiple MCP servers for enhanced AI-assisted development workflows.*