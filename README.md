# Sniprelay agent skill

Use the [Sniprelay](https://sniprelay.passarelli.dev) ephemeral pastebin through its agent-native CLI: share text/code, inspect links safely, explicitly consume one-time content, and delete using creation capabilities.

## Install the skill

```sh
npx skills add Ale1x/sniprelay-skill --skill sniprelay
```

Select the agents to install into. For a global Codex installation:

```sh
npx skills add Ale1x/sniprelay-skill --skill sniprelay --agent codex --global
```

This installs agent instructions, not the CLI. With Node.js 24+:

```sh
npm install --global sniprelay
sniprelay --help
```

Both the repository and the npm package are public. No GitHub/npm login is needed to install either. The Sniprelay application source is maintained separately.

## Use

Ask your agent, for example:

- “Use $sniprelay to share this file privately, with a one-time reveal.”
- “Use $sniprelay to inspect this paste's expiry without consuming it.”
- “Use $sniprelay to read the contents of this one-time link.”
- “Use $sniprelay to delete the paste using the key file I provided.”

The skill preserves the user's upload intent and explains JSON receipts, safe secret sources, explicit consumption and ambiguous failures. Private pastes are not end-to-end encrypted, and deletion does not certify removal from infrastructure backups.

Read the [skill entrypoint](skills/sniprelay/SKILL.md) and [CLI reference](skills/sniprelay/references/cli.md) before installing. The canonical live service instructions are [llms.txt](https://sniprelay-backend.passarelli.dev/llms.txt), also available through `sniprelay instructions --raw`; the machine contract is [OpenAPI](https://sniprelay-backend.passarelli.dev/openapi.json).

## Maintenance

Update with `npx skills update sniprelay`. Contributions should keep CLI examples consistent with the public npm executable and the live OpenAPI contract. Keep passwords, deletion keys, paste content and real receipts out of this repository. The skill does not require scripts, credentials or MCP configuration.

The skill content is MIT licensed; this does not change the application's or CLI's license.
