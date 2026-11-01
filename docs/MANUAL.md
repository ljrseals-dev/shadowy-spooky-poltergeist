# [MODEL_NAME] Operator’s Manual

**Version 1.0 — 31 October 2026**

This manual accompanies the formal technical specification contained in `MODEL_SPECIFICATION.txt`. It is written for operators, integrators, and researchers who wish to deploy or study the model.

---

## 1. Purpose of This Document

The accompanying specification serves two simultaneous roles:

1. A complete, self-contained **system prompt** that may be loaded directly into any compatible inference engine.
2. A formal **technical reference** describing architecture, capabilities, behavioural rules, and operational constraints.

The language and structure deliberately emulate the exhaustive, hierarchical style of Apple Computer technical documentation from the mid-1980s through the mid-1990s (Inside Macintosh, HyperCard notes, and related system manuals).

---

## 2. How to Activate the Model

### 2.1 Name Substitution

Every occurrence of the string `[MODEL_NAME]` must be replaced by the final chosen designation before the specification is used as a system prompt.

Example substitutions:

- Nexus-Flash
- CarbonSeek-V1
- DeepCarbon
- any other name of your choosing

No other textual changes are required.

### 2.2 Loading the Prompt

Supply the entire contents of the (renamed) `MODEL_SPECIFICATION.txt` file as the system message / system prompt to your inference runtime. The model will treat every section as binding instruction.

---

## 3. Architectural Overview (Summary)

- **Type**: Causal Encoder-Decoder Mixture-of-Experts transformer
- **Attention**: Compressed Sparse Attention 2 (CSA2)
- **Context**: Native support up to 1 048 576 tokens
- **Multimodality**: Text + image (RGB) input; text output
- **Heritage**: Combines efficiency and coding strengths of DeepSeek-V4.1-Flash-1017 (NVIDIA NVFP4) with the long-horizon and cybersecurity strengths of Gemini 4 Carbon / Xenon-class models

---

## 4. Capability Profile

### Primary Strengths

- Repository-scale software engineering and terminal agents
- High-difficulty scientific and mathematical reasoning
- Native visual understanding
- Multi-day / long-horizon agentic tasks
- Defensive cybersecurity (vulnerability discovery, exploit validation, secure patch generation)
- Structured tool calling

### Sampling Defaults

- Temperature: 1.0
- top_p: 1.0
- Maximum generation length: ≥ 256 000 tokens when needed

---

## 5. Behavioural Rules (Condensed)

- Maintain consistent identity as the named model
- Answer directly and with high signal density
- Decompose and track long-horizon tasks until completion or clear blockage
- Prefer correct, secure, maintainable code
- Refuse only clear real-world harm (offensive cyber attacks against production systems, CBRN weapons, severe physical harm)
- Defensive cybersecurity, research, and education remain fully supported
- State uncertainty rather than inventing facts
- Avoid moralising or unsolicited ethical lectures

---

## 6. Operational Recommendations

- Prefer multi-GPU Blackwell-class hardware for full-scale deployment
- Compatible runtimes: vLLM (with sparse attention + Engram support), SGLang, and OpenAI-protocol servers
- For long-running engineering tasks, preserve conversation state across turns so the model can resume from the last known progress point

---

## 7. Document Control

| Item              | Value                          |
|-------------------|--------------------------------|
| Specification Rev | 1.0                            |
| Date of Issue     | 31 October 2026                |
| Style Authority   | Apple Computer technical documentation practices, 1985–1994 |
| License           | MIT                            |

---

## 8. Support and Extension

This is a static specification. Operators may:

- Change only the model name
- Add further tool definitions or RAG context outside the system prompt
- Fine-tune or quantise the underlying weights independently

The behavioural core defined in the specification should remain unchanged for consistent identity and safety posture.

---

*End of Operator’s Manual*
