# Usage

Certonaut offers two modes of operation:

* a pure command‑line invocation for scripts and automation (or just preferences)
* and and an interactive terminal menu for guided workflows.

It is possible to mix command-line and interactive options: The command-line options will be automatically applied, skipping interactive options. Interactive options can still add or override the command-line options.

### Command‑Line (Non‑Interactive) Mode

Invoke
`certonaut` with explicit subcommands to automate tasks in CI/CD pipelines, cron jobs, or scripts.
Interactive prompts are automatically disabled when run in non‑TTY environments.
You can also force certonaut to disable interactive prompts by invoking certonaut as `certonaut --non-interactive`.

Basic usage:

```bash
certonaut [GLOBAL OPTIONS] <SUBCOMMAND> [SUBCOMMAND OPTIONS]
```

Use `certonaut --help` for available subcommands and their documentation.

### Interactive Mode

Launch a fully interactive session with a selection menu that guides you through all commands:

```bash
certonaut
```

This requires a TTY terminal to work.

<!-- TODO: Demo -->