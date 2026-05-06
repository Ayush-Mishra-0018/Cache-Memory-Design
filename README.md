# Cache Memory Design

## Project explanation
A small educational project that explores **cache memory design concepts** through code and experiments.

This repository is intended to help understand how CPU caches work and how common design choices affect behavior/performance, such as:
- Cache organizations (direct-mapped, set-associative, fully-associative)
- Replacement policies (e.g., LRU / FIFO / Random)
- Write policies (write-through vs write-back, write-allocate vs no-write-allocate)
- Hit/miss behavior using small traces/examples

## Folder structure
A typical layout for this project looks like:
- `src/` — implementation
- `include/` — headers
- `tests/` — tests or sample traces
- `docs/` — notes and explanations

## Code (brief)
At a high level, cache access usually follows this flow:

```pseudo
function read(address):
    index = getIndex(address)
    tag   = getTag(address)

    line = cache[index]
    if line.valid and line.tag == tag:
        return line.data            # HIT

    data = memoryRead(address)      # MISS → fetch from memory
    cache[index] = { valid: true, tag: tag, data: data }
    return data
```

If you share the main source file path (e.g., `src/...`), I can replace the pseudo-code with a short snippet from your actual implementation.
