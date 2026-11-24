### Dart files

[`lib/main.dart`](https://github.com/gh-io/auraecosystem/blob/main/lib/main.dart) is a small Flutter app: it requests album 1 from JSONPlaceholder, parses the response into an `Album`, and displays the album title with loading and error states.

The root [`main.dart`](https://github.com/gh-io/auraecosystem/blob/main/main.dart) is separate, minimal Dart sample code. It makes a POST request to `dartpad.dev`, prints the response, then tries to read another URL. It doesn’t add functionality to the Flutter app or call into `lib/main.dart`.

### `docs/` and `Docs/`; what gets published

They’re distinct paths because GitHub treats capitalization as significant. The commit history shows a file was moved from `Docs/readme.mdx` to `docs/rb-us/web/Index.md`, suggesting the lowercase tree contains a reorganized or migrated document; `Docs/index.md` remains a separate file.

Neither Pages workflow selects one of those directories as its publishing source: [`static.yml`](https://github.com/gh-io/auraecosystem/blob/main/.github/workflows/static.yml) uploads the repository root, while [`jekyll.yml`](https://github.com/gh-io/auraecosystem/blob/main/.github/workflows/jekyll.yml) runs a Jekyll build from the root. So the checked-in workflow files don’t establish that either `docs/` or `Docs/` alone is published.

### Swift MCP view and LM Studio/MCP materials

[`MCPToolsListView.swift`](https://github.com/gh-io/auraecosystem/blob/main/MCPToolsListView.swift) is a SwiftUI interface for showing and searching available MCP server tools. It reads tool collections from a Copilot MCP manager, maintains server toggle state, and uses persistence APIs. That makes it MCP-related code, but the file doesn’t show a direct LM Studio integration.

The connection to the repository’s LM Studio materials is unclear: [`lmstudio.ai/Index.es.mjs`](https://github.com/gh-io/auraecosystem/blob/main/lmstudio.ai/Index.es.mjs) is effectively empty, and [`mcp_config.default.json`](https://github.com/gh-io/auraecosystem/blob/main/mcp_config.default.json) has an empty `mcpServers` object. The Swift view appears alongside these MCP artifacts, but the repository doesn’t document a working setup linking them.
