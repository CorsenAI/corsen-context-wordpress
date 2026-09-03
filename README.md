# Corsen Context for WordPress

Install Corsen Context on an existing WordPress site to publish owner-selected
public content through `llms.txt`, a read-only MCP endpoint, and opt-in WebMCP.
The WordPress administrator controls which post types, paths, and tools are
exposed.

[Install from WordPress.org](https://wordpress.org/plugins/corsen-context/) ·
[Download plugin ZIP](https://github.com/CorsenAI/corsen-context-wordpress/releases/download/v1.5.16/corsen-context-1.5.16.zip) ·
[Standalone source](https://github.com/CorsenAI/corsen-context-wordpress) ·
[Live demo](https://webmcp.corsen.ai)

## Set up on your own site

1. Install from WordPress.org (**Plugins > Add New**, search "Corsen
   Context") or upload the release ZIP, then activate.
2. Open **Settings > Corsen Context**: choose the public post types, exclude
   private paths, and pick which of the four core tools agents may call.
3. Open **Settings > Corsen Context Control** to enable optional extensions
   (products, sections, structured data, agent-access check, human-only
   expert intake) and the WebMCP bridge. Everything except the four core
   read-only tools is off by default.
4. Verify: open `/llms.txt`, run `tools/list` against the MCP endpoint shown
   in the settings, and open a page in a WebMCP-capable browser.
5. Revoke at any time from the same screens; the human pages never change.

No code, build step, or API key is required. The plugin readme documents
every setting, discovery hint and security boundary.

## Install

The simplest path is **Plugins > Add New**, search for **Corsen Context**, then
install and activate it. For a manual installation, download the plugin ZIP,
open **Plugins > Add New > Upload Plugin**, upload the ZIP, and activate it.

Open **Settings > Corsen Context** to choose the public content and tools that
site agents may read. WebMCP is opt-in and can be revoked by the owner without
removing the site content.

## Verify

After enabling the public surfaces, run:

```bash
npx @corsenai/corsen-context-cli doctor --url https://www.example.com
```

The current release is 1.5.16. The live flagship reports its installed version
in its MCP `initialize` response; confirm the installed version in WordPress
before comparing behavior.

## Development

```bash
composer install
composer test:unit
composer lint
```

The npm packages and canonical multi-framework history are maintained in the
[Corsen Context monorepo](https://github.com/CorsenAI/corsen-context).
