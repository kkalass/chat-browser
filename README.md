
# Chat Analyzer

A web-based tool for exploring AI-analyzed chat data through an intuitive three-column interface. Browse clusters, groups, and individual messages with advanced filtering and context expansion.

## Overview

Chat Analyzer provides a visual interface for exploring pre-analyzed chat room data. The tool uses AI-generated clusters and groups to organize conversations into meaningful topics, making it easy to navigate large chat histories and understand discussion themes.

**Note:** This is a rapid prototype developed through collaborative coding with AI assistance. While functional, you may encounter some UI sluggishness when working with large datasets. We appreciate your patience and understanding!

## Features

### Three-Column Layout
- **Clusters** (left): AI-generated topic clusters summarizing major themes
- **Groups** (center): Conversation groups within each cluster
- **Messages** (right): Original chat messages

### Visual Indicators
- **Color-coded borders**: Each group has a unique color for easy message identification
- **Highlighted vs. Outlined**: Direct selections are highlighted; related items are outlined
- **AI-generated labels**: Clear distinction between AI-analyzed content and original messages

### Interactive Exploration
- **Bidirectional navigation**: Click clusters to see all groups, or click messages to highlight their group and cluster
- **Keyword filtering**: Filter by topic keywords with automatic collapse/expand
- **Text search**: Search across clusters, groups, and messages with context preservation
- **Context expansion**: Expand collapsed items with +3/-3 incremental controls
- **Radio button selection**: Exclusive filtering with clear buttons

### Smart Collapsing
- GitHub-style diff collapsing for non-relevant items
- Automatic context management
- Expandable before/after context

## Usage

### Local Development
1. Clone or download this repository
2. Start a local web server in the project directory:
   ```bash
   python3 -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser

### GitHub Pages Deployment
The tool is designed to work seamlessly with GitHub Pages:
1. Push the repository to GitHub
2. Enable GitHub Pages in repository settings
3. Set source to main branch / root directory
4. Access at `https://yourusername.github.io/repository-name/`

## Data Structure

The tool expects the following structure:

```
chats/
  your-chat-name/
    export.json              # Original messages
    clustered_groups.jsonl   # AI-analyzed groups
    final_topic_report.json  # AI-generated clusters
chats.json                   # Chat metadata configuration
```

### Adding New Chats

1. Create a new directory under `chats/` with your chat data files
2. Update `chats.json` with chat metadata:

```json
{
  "id": "your-chat-name",
  "name": "Display Name",
  "exportDate": "2025-11-14",
  "description": "AI-analyzed snapshot of the chat room"
}
```

Note: Cluster, group, and message counts are automatically determined from the data files.

## Technology Stack

- **Vue.js 3**: Reactive UI framework (loaded via CDN)
- **Pure HTML/CSS/JavaScript**: No build process required
- **Static hosting compatible**: Works on any static file server

## File Overview

- `index.html` - Chat selection page
- `chat_browser.html` - Main exploration interface
- `chats.json` - Chat metadata configuration
- `chats/` - Directory containing analyzed chat data

## Data Privacy

This tool operates entirely in the browser on static data. No data is sent to external servers. All analysis has been performed offline, and the tool simply presents pre-analyzed results.

## Limitations

- **Static snapshots**: Data represents a point-in-time export, not live data
- **Performance**: Large datasets may cause UI sluggishness
- **Browser compatibility**: Tested on modern browsers (Chrome, Firefox, Safari, Edge)

## Contributing

This is a lightweight visualization tool for exploring chat analysis results. Feel free to fork and adapt for your needs.

## License

MIT License - See LICENSE file for details

---

**Disclaimer**: This tool was rapidly prototyped with AI assistance to provide a functional exploration interface. While we've aimed for a smooth user experience, performance optimizations for very large datasets are ongoing. Thank you for your understanding!