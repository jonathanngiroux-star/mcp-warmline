# mcp-warmline

MCP server for transactional email - send emails, track delivery, monitor reputation.

## Tools

### send_email
Send a transactional email.

**Parameters:**
- `to` (string, required): Recipient email address
- `subject` (string, required): Email subject
- `body` (string, required): Email body (HTML or text)
- `from` (string, optional): Sender email address (default: "noreply@example.com")
- `tags` (array, optional): Email tags for tracking
- `metadata` (object, optional): Custom metadata

### send_batch
Send batch of transactional emails.

**Parameters:**
- `emails` (array, required): Array of emails to send, each with to, subject, body, from, tags, metadata

### get_delivery_status
Get delivery status for an email.

**Parameters:**
- `email_id` (string, required): Email ID from send response

### get_reputation_metrics
Get email reputation metrics for a domain.

**Parameters:**
- `domain` (string, required): Domain to check reputation for
- `days` (integer, optional): Days of history (default: 30)

## Installation

```bash
pip install -r requirements.txt
```

## Usage

```bash
python main.py
```

## Connecting to Claude Desktop

Add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "warmline": {
      "command": "python",
      "args": ["/path/to/mcp-warmline/main.py"],
      "cwd": "/path/to/mcp-warmline"
    }
  }
}
```

## License

MIT