# Contributing

Thanks for your interest in the MCP Security Registry!

## How This List Works

This list is **auto-generated** from [AgentSeal's MCP Registry](https://agentseal.org/mcp). Every server is automatically scanned through 9 security analyzers, scored, and published here daily.

## Submit a New Server

To add an MCP server to the registry:

1. Go to [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit)
2. Enter the package name (npm, PyPI, Git repo, or HTTP endpoint)
3. We'll scan it automatically and add it to the registry

Scans typically complete within a few hours.

## Report Issues

- **False positive?** If you believe a finding is incorrect, [email us](mailto:hello@agentseal.org) with the server name and the finding you'd like to dispute.
- **Missing server?** Submit it at [agentseal.org/mcp/submit](https://agentseal.org/mcp/submit).
- **Incorrect data?** Open a [GitHub issue](https://github.com/AgentSeal/mcp-security-scores/issues) describing what's wrong.

## Suggest Improvements

For improvements to the list format, translations, or documentation:

1. Fork the repository
2. Create a branch (`git checkout -b improve-docs`)
3. Make your changes
4. Submit a pull request

## Translations

We welcome translations! To add a new language:

1. Copy `README.md` to `README.{lang-code}.md` (e.g., `README.es.md` for Spanish)
2. Translate all section headers, descriptions, and static text
3. Keep server names, URLs, scores, and links unchanged
4. Submit a pull request

## Code of Conduct

Be respectful, constructive, and helpful. We're all here to make AI agents safer.
