# rag

Keep a knowledge base, retrieve from it, and build the prompt.

## Install

```bash
ovc pkg install rag
```

## Use

```ov
import "rag"
 store = rag_build(["Ovyth compiles to native executables."], 8, 2)
hits = rag_topk(store, "what does ovyth compile to", 1)
print(hits[0]["text"])
```

## Conventions

Every public name is prefixed `rag_`: Ovyth flattens all top-level names
into one program, so the prefix *is* the namespace. Nothing here runs at
import time and the module holds no state between calls — the caller owns
the data and passes it in, which keeps it serializable and safe next to
other packages.

## License

MIT
