## Dependencies

- `jq`   - For JSON processing
- `glow` - For terminal markdown rendering
- `gum`  - For terminal UI components

## Usage

```bash
per [options] "your question or prompt here"
```

Default model is sonar (see Options section to modify model).
Default context size is medium (see Options section to modify context size).

## Options
### Perplexity Models
- `-p` - Use the "sonar-pro" model (default model is "sonar")
- `-d` - Use the "sonar-deep-research" model (removes search context size parameter)
- `-r` - Use the "sonar-reasoning" model
- `-R` - Use the "sonar-reasoning-pro" model
### Claude AI
- `-c [VERSION]` - Use Claude AI instead of Perplexity (3.5 for Claude 3.5 Haiku, if left empty, defaults to Claude 3.7 Sonnet)
### History
- `-u [NAME]` - Use a specific named history file (stored at ~/.perplexity-history-[NAME])
- `-s` - Select a history file using interactive filter
- `-n` - Create a new history file
- `-l` - List all perplexity history files (only user-generated ones)
- `-L` - List all perplexity history files (including auto-generated ones)
### Context Size
- `-h` - Set context size to high

## History Management

We use the most recent history file if you ask a question within 10 minutes of the last question.
Otherwise, we create a new history file.

You can use options `-u`, `-s`, and `-n` to manage history files.

## Examples

Ask a question using the default model:
```bash
per "What is the capital of France?"
```

Ask a follow-up question (uses the same history file if you use the tool less than 10mn after last usage):
```bash
per "What is its population?"
```

Use the pro model:
```bash
per -p "Explain quantum computing"
```

Start a new conversation with a named history:
```bash
per -u research "Tell me about recent advances in AI"
```

Continue a specific conversation:
```bash
per -u research "What are the ethical implications?"
```

Deep research mode:
```bash
per -d "What are the long-term effects of climate change?"
```

Use Claude AI instead of Perplexity:
```bash
per -c 3.5 "What is the difference between transformers and RNNs?"
```
