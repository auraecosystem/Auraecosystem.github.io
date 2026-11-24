### `lib/main.dart` vs. root `main.dart`

[`lib/main.dart`](https://github.com/gh-io/auraecosystem/blob/main/lib/main.dart) is a small Flutter app: it requests album 1 from JSONPlaceholder, parses the response into an `Album`, and displays its title with loading and error states.

The root [`main.dart`](https://github.com/gh-io/auraecosystem/blob/main/main.dart) is a separate, minimal Dart HTTP example. It posts sample data to DartPad’s `whatsit/create` endpoint, prints the response, then tries to read `foobar.txt`. It doesn’t extend or connect to the Flutter app.

### Why both `docs/` and `Docs/` exist—and what’s published

They are distinct directories, not case variants that the repository merges:

- [`Docs/`](https://github.com/gh-io/auraecosystem/tree/main/Docs) contains an `index.md` describing an interactive quantum-circuit simulator and ecosystem notes.
- [`docs/`](https://github.com/gh-io/auraecosystem/tree/main/docs) contains an `rb-us/` subdirectory; the directory listing shows no files there.

The checked-in Pages workflows don’t designate either directory as the publishing source. [`static.yml`](https://github.com/gh-io/auraecosystem/blob/main/.github/workflows/static.yml#L32-L43) uploads the repository root, while [`jekyll.yml`](https://github.com/gh-io/auraecosystem/blob/main/.github/workflows/jekyll.yml#L29-L53) builds Jekyll from the root. Both are configured to deploy on pushes to `main`, so the files alone don’t establish which deployment is currently active or which workflow’s output is live. In short: **neither `docs/` nor `Docs/` is explicitly selected as the published directory.**

### `MCPToolsListView.swift`, LM Studio, and MCP docs

[`MCPToolsListView.swift`](https://github.com/gh-io/auraecosystem/blob/main/MCPToolsListView.swift) is a SwiftUI view for listing and searching MCP server tools. It reads available tools from `CopilotMCPToolManagerObservable` and persisted status from `AppState`; the code points to a GitHub Copilot service integration, not an LM Studio integration.

The repository has some MCP-related artifacts, including an [empty default MCP server config](https://github.com/gh-io/auraecosystem/blob/main/mcp_config.default.json) and a [GitHub MCP server binary/checksum file](https://github.com/gh-io/auraecosystem/blob/main/github-mcp-server_0.12.1_checksums). However, the `lmstudio.ai/` listing contains only a one-byte `Index.es.mjs` file, and the `webllms/docs/` listing is empty. I couldn’t find substantive LM Studio or MCP documentation tying those materials to the Swift view. The evidence suggests they are separate or incomplete pieces in this repository, rather than one documented, integrated feature.
