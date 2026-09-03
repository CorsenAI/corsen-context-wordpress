# Corsen Context for WordPress

Install Corsen Context on an existing WordPress site to publish owner-selected
public content through `llms.txt`, a read-only MCP endpoint, and opt-in WebMCP.
The WordPress administrator controls which post types, paths, and tools are
exposed.

[Install from WordPress.org](https://wordpress.org/plugins/corsen-context/) ·
[Download plugin ZIP](https://github.com/CorsenAI/corsen-context-wordpress/releases/download/v1.5.14/corsen-context-1.5.14.zip) ·
[Standalone source](https://github.com/CorsenAI/corsen-context-wordpress) ·
[Live demo](https://webmcp.corsen.ai)

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

The live flagship demonstrates version 1.5.14. Confirm the installed version in
WordPress before comparing behavior.

## Development

```bash
composer install
composer test:unit
composer lint
```

The npm packages and canonical multi-framework history are maintained in the
[Corsen Context monorepo](https://github.com/CorsenAI/corsen-context).
