# UGCHooks MCP

Paste a product link, get 100 TikToks and Reels: slideshows, reaction hook videos and GIF memes with captions.

get_profile reads your email and credits. list_batches and get_batch read your post batches with hooks, slide text, captions, hashtags and saved render links. create_batch turns a product link into a brief and the first 10 posts; write_part writes parts of batches you unlocked. No credit spending, unlocking or posting.

## Remote MCP

Use **https://ugchooks.app/mcp** in a client that supports remote MCP with OAuth. Sign in to UGCHooks and explicitly approve the connection.

## Claude Desktop and other stdio clients

Requires Node.js 22 or newer. Add this configuration:

```json
{
  "mcpServers": {
    "ugchooks": {
      "command": "npx",
      "args": [
        "-y",
        "ugchooks-mcp"
      ]
    }
  }
}
```

Or install the `.mcpb` file from [Releases](https://github.com/saeedmsdi-ugchooks/mcp-server/releases) in your desktop client's Extensions settings. The connector opens your browser for sign-in. If the consent page asks you to sign in, use its new-tab link, then return and refresh the consent page.

## Privacy and permissions

Existing profile-only connections must reconnect and approve the new permissions to use content tools. The consent screen lists the requested permissions. Your product password and provider credentials are not requested by this package. The pinned [mcp-remote](https://www.npmjs.com/package/mcp-remote) bridge handles OAuth, PKCE and local token storage. It connects only to the fixed endpoint above; command-line endpoint overrides are not supported. OAuth tokens are stored locally by mcp-remote and should be treated as credentials.

Revoke a connection at [UGCHooks MCP connections](https://ugchooks.app/oauth/mcp/connections).

## Development and publishing

Run `npm ci` and `npm test`. GitHub Actions publishes a new package version using the organization’s `NPM_TOKEN` secret, then builds and releases the desktop bundle. Keep package.json, manifest.json, server/config.json and server.json versions aligned.

Marketplace approval is separate from npm publication. See the product’s submission notes for endpoint tests and review prerequisites.

[Website](https://ugchooks.app) · [Issues](https://github.com/saeedmsdi-ugchooks/mcp-server/issues)
