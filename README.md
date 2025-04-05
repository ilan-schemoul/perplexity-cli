## Dependencies

- `jq` - For JSON processing
- `glow` - For terminal markdown rendering

## Usage

```bash
per [options] "your question or prompt here"
```

Currently it only ever use "high" for the parameter context size.
Default model is sonar (see Options section to modify model).

## Options

- `-p` - Use the "sonar-pro" model (default model is "sonar")
- `-d` - Use the "sonar-deep-research" model with expanded context
- `-u [NAME]` - Use a specific named history file (stored at ~/.perplexity-history-[NAME])
- `-l` - List all perplexity history files
- `-L` - List all perplexity history files (including auto-generated ones)

## History Management

Use most recent history file if you ask a question less than 10mn after the last question. If more
than 10mn has elapsed since the last question we start afresh with new history file.

See section #Options above to specify manually history files.

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
