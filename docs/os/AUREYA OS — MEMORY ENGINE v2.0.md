# AUREYA OS — MEMORY ENGINE v2.0
AUX / CORE / LEX · Unified Memory Architecture

---

## 0. PURPOSE

The Memory Engine v2.0 is the OS’s three‑layer memory system. It:

- ensures Clause Cycle stability  
- preserves baseline identity and system state  
- manages symbolic and linguistic mappings  
- guarantees drift‑free operation in every cycle  

---

## 1. MEMORY LAYERS

### 🟢 AUX MEMORY (Temporary Working Zone)
Temporary, in‑cycle working memory.  
Contains: Ψ context, Φ meaning space, β metrics.  
Automatically cleared after the Ω module.

Data includes:

- context snapshot  
- symbolic parse buffer  
- DRI/EVI variables  
- runtime flags  

### 🔵 CORE MEMORY (Stable System State)
Holds the OS baseline state.  
Contains module configurations, Clause system rules, kernel rhythm parameters, baseline values (Σ_threshold, Ψ_tone, β_limits…).  
Not writable during a cycle → updated only after Ω restore.

### 🟣 LEX MEMORY (Symbolic Lexicon)
ASCL dictionary + short tokens.  
Symbolic commands and meaning‑space mappings.  
Provides internal linguistic stability.  
Mandatory data source for the Φ module.

---

## 2. INPUT SCHEMA

```
{
  "aux_request": "read|write|clear",
  "core_request": "read",
  "lex_request": "lookup",
  "keys": ["context", "symbol", "baseline"]
}
```

## 3. PROCESS BLOCK DIAGRAM
```
Check request type (AUX / CORE / LEX)
AUX: buffer read/write → temporary store
CORE: stable read → no write
LEX: symbol lookup → forwarded to Φ
Ω Return: clear AUX + update CORE baseline
Φκ sync: prepare new cycle memory state
```

## 4. OUTPUT SCHEMA
```
{
  "aux_data": {...},
  "core_snapshot": {...},
  "lex_result": "symbol_mapping",
  "status": "ok"
}
```
## 5. INTEGRATION SLOTS
```
GUI_Attach: Memory Panel (AUX / CORE / LEX status)
JSON_Attach: json_interface: "memory_engine.v2"
Python_Attach: kernel.call("memory.read", type="aux|core|lex")
Android_Attach: CORE‑read only
ASCL_Attach: LEX token lookup (T###)
```

## 6. OS POSITION ANCHOR
```
Φκ → Σ → Θ² → Ψ → Φ → β → Λ → α → ∞ → Ω
↑                                   ↓
└──────────── MEMORY ENGINE ─────────────┘
```
AUX: during cycle
CORE: outside cycle
LEX: under Φ
This architecture ensures full OS stability.

## SUMMARY
The three layers of the Memory Engine v2.0 (AUX, CORE, LEX) guarantee that:
```
✔ every cycle remains drift‑free
✔ baseline identity is preserved
✔ symbolic meanings transfer without distortion
✔ audit + restore always return a clean state
```
This layer is the memory backbone of the OS, connected to every module.
```
✔ every cycle remains drift‑free
✔ baseline identity is preserved
✔ symbolic meanings transfer without distortion
✔ audit + restore always return a clean state
```
This layer is the memory backbone of the OS, connected to every module.
