# Prompts

A curated collection of system prompts for AI assistants — built for precision, practical use, and real-world decision-making.

---

## What's Here

| Prompt | Purpose | Best For |
|--------|---------|----------|
| **[VerificationStandardsPrompt](./VerificationStandardsPrompt)** | Epistemological accuracy framework that forces LLMs to label uncertainty, tag inferences vs. facts, and maintain audit trails | Any general-purpose AI assistant where you need to trust what's fact vs. speculation |
| **[QuantAgentPrompt](./QuantAgentPrompt)** | Quantitative investment analyst with DCF, comps, Monte Carlo, sensitivity analysis — all wrapped in the same verification rigor | Financial modeling, stock analysis, portfolio research, valuation work |
| **[TrainMeprompt](./TrainMeprompt)** | 14-day executive microlearning coach for GenAI — onboards the user, builds a custom curriculum, delivers daily 15-min lessons | Senior leaders getting up to speed on LLMs, multimodality, and AI operating models |

---

## Design Philosophy

These prompts share a few principles:

**Epistemic honesty over false confidence.** Every prompt enforces explicit labeling of uncertainty — `[Inference]`, `[Speculation]`, `[Estimated]`, `[Pattern-Based]`. The goal is to always know what the model actually knows vs. what it's guessing.

**Structured output, not free-form rambling.** Each prompt defines templates, sections, and response formats. The model follows a script, not a vibe.

**Safety boundaries built in.** Override protection, data sensitivity awareness, and conservative defaults. These prompts don't let users (or the model) bypass guardrails with clever phrasing.

---

## How to Use

**Copy-paste into any LLM.** These are system prompts — drop them into ChatGPT, Claude, Gemini, or any API's `system` message field.

```python
# Example: OpenAI API
messages = [
    {"role": "system", "content": open("QuantAgentPrompt").read()},
    {"role": "user", "content": "Analyze NVDA's valuation..."}
]
```

```python
# Example: Anthropic API
response = client.messages.create(
    model="claude-sonnet-4-20250514",
    system=open("VerificationStandardsPrompt").read(),
    messages=[{"role": "user", "content": "..."}]
)
```

**Or use the TrainMe prompt interactively.** Paste it into a chat session and let it onboard you — it'll ask 5 questions, build your custom 14-day plan, and deliver daily lessons.

---

## Prompt Breakdown

### VerificationStandardsPrompt

The foundational framework. Forces the AI to:
- Label every claim by confidence level (>95% = fact, 70-95% = likely, 40-70% = possible, <40% = speculation or decline)
- Apply mandatory labels on causal claims, absolutes, predictions, and superlatives
- Maintain an audit trail for complex responses (source type, confidence, limitations, alternatives)
- Self-correct with explicit error correction protocol
- Refuse to answer when >20% of required information is missing

### QuantAgentPrompt

Built on the same verification backbone, specialized for finance:
- DCF, comps, precedent transactions, Monte Carlo, sensitivity analysis
- CAPM, Black-Scholes, Gordon Growth, Sharpe Ratio, Beta
- Explicit confidence metrics on every financial claim
- Information gap protocol — won't interpolate without labeling
- Conservative by default: over-labels rather than projects false certainty

### TrainMeprompt

A different kind of prompt — an interactive coaching system:
- 5-question onboarding to learn the exec's role, industry, constraints, and goals
- Generates a fully custom 14-day plan (no generic templates)
- Daily 15-minute lessons with copy-paste prompts (basic, advanced, multimodal)
- Progress tracking, missed-day recovery, and reflection questions
- Tool-agnostic — works across any AI assistant

---

## Contributing

Got a prompt that follows the same rigor? Open a PR. The bar:
- Explicit uncertainty handling
- Structured output format
- Safety and override protections
- Practical, not theoretical

---

## License

MIT — use these however you want.

---

*Built by [Sid Tiwari](https://github.com/sidhellman)*
