# VOSU for Cursor

Generate images, videos, and 3D from Cursor using the VOSU MCP server at `https://vosu.ai/mcp`.

The first tool call asks you to sign in to VOSU. Listing tools does not.

## Install from source

Cursor loads local plugins from `~/.cursor/plugins/local/<name>/`. Copy this directory (a symlink is less reliable):

```bash
mkdir -p ~/.cursor/plugins/local
rsync -a --delete --exclude='.git' ./ ~/.cursor/plugins/local/vosu/
```

Reload Cursor: `Cmd-Shift-P` → **Developer: Reload Window**.

Then check:

- **Plugins** lists **VOSU**.
- **MCPs** lists the VOSU server. Connect when Cursor asks, then try “check my VOSU credits”. `check_balance` does not spend credits.

After pulling changes, run the same `rsync` and reload.

To uninstall:

```bash
rm -rf ~/.cursor/plugins/local/vosu
```

## Marketplace

This folder is the plugin root. Publish it as its own public Git repository, then submit that repository at [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish).

## Support

support@vosu.ai
