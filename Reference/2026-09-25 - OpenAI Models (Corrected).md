---
created: 2026-09-25
updated: 2026-09-25
source: claude-code-jarvis
status: reviewed
---

# OpenAI Models (Corrected)

## Summary

A corrected and updated version of the unreviewed local-LLM draft [[openai-models-20260921030308]]. That draft stopped at GPT-4o (mid-2024), was truncated, and had several factual errors. This version fixes them, adds releases through September 2026, and marks how each claim was sourced.

**Confidence key**
- **(web)**: checked against a web source on 2026-09-25 (see Sources).
- **(gk)**: Claude's general knowledge, not re-checked. Verify before relying on it.

OpenAI doesn't publish parameter counts, architectures or training-data details for its proprietary models after GPT-3. Anything claimed about those is an estimate.

## Corrections to the original draft

| Original claim | Correction |
| --- | --- |
| GPT-1 trained on "8 million documents from the WebText dataset" | GPT-1 (117M parameters) was trained on BooksCorpus, about 7,000 unpublished books. WebText (~8M documents) was GPT-2's dataset. (gk) |
| GPT-2 "introduced the concept of emergent abilities" | GPT-2 showed zero-shot task transfer. "Emergent abilities" is a later framing, usually tied to much larger models. (gk) |
| GPT-3 "later open-sourced via the GPT-3.5 family" | GPT-3 and GPT-3.5 were never open-sourced. OpenAI's first open-weight language models since GPT-2 were gpt-oss (August 2025). (web) |
| GPT-4 "supports up to 128k tokens" | GPT-4 launched with 8K and 32K context versions. 128K arrived with GPT-4 Turbo on 2023-11-06. (web) |
| GPT-4o is the "latest major release" | Out of date. See the timeline below, which runs through GPT-6 (September 2026). (web) |
| Codex "evolved into Code Interpreter / Advanced Data Analysis" | The Codex API was retired in 2023. Code Interpreter was a separate ChatGPT feature. OpenAI has since reused the name "Codex" for its coding agent products. (gk) |
| OpenAI Gym is an active OpenAI toolkit | Gym is now maintained by the Farama Foundation as **Gymnasium**. (gk) |

## Model timeline

### Base GPT models
- **GPT-1**: 2018-06-11. 117M parameters, BooksCorpus. (web date; gk details)
- **GPT-2**: staged release starting 2019-02-14. 1.5B parameters in the largest version, which was held back at first over misuse concerns. (web date; gk details)
- **GPT-3**: 2020-06-11, via a private API beta. 175B parameters, 2,048-token context. (web date; gk details)

### ChatGPT era and GPT-4
- **GPT-3.5**: powered the ChatGPT launch on 2022-11-30. Tuned for dialogue with RLHF. (web)
- **gpt-3.5-turbo**: 2023-03-01, in the Chat Completions API. (web)
- **GPT-4**: 2023-03-14. Accepts text and image input; 8K and 32K context versions. (web)
- **GPT-4 Turbo**: 2023-11-06. 128K context. (web)
- **GPT-4o**: 2024-05-13. One model for text, audio and image input and output; 128K context. (web)
- **GPT-4o mini**: 2024-07-18. (web)

### Reasoning ("o") series
- **o1-preview / o1-mini**: 2024-09-12. OpenAI's first reasoning models, trained to think before answering. (web)
- **o1**: 2024-12-05. (web)
- **o3-mini**: 2025-01-31. (web)
- **o3 / o4-mini**: 2025-04-16. OpenAI's first reasoning models that could use all of ChatGPT's tools on their own. (web)

### 2025 releases
- **GPT-4.5**: 2025-02-27, research preview. (web)
- **GPT-4.1 / 4.1 mini / 4.1 nano**: 2025-04-14. 1M-token context window. (web)
- **gpt-oss-120b / gpt-oss-20b**: August 2025. Open-weight under Apache 2.0, mixture-of-experts (MoE) design. 120b: 117B total / 5.1B active parameters, fits on a single 80 GB GPU. 20b: 21B total / 3.6B active. Not served through the OpenAI API. (web)
- **GPT-5**: 2025-08-07. One system combining a fast model with a deeper "GPT-5 thinking" reasoning model. (web)
- **GPT-5.1**: 2025-11-12, Instant and Thinking versions. (web)
- **GPT-5.2**: 2025-12-11. (web)

### 2026 releases
- **GPT-5.3 Instant** and **GPT-5.4 Thinking / Pro**: 2026-03-05. GPT-5.4 was the first mainline model with built-in computer use. (web)
- **GPT-5.4 mini / nano**: 2026-03-17. (web)
- **GPT-5.5**: 2026-04-23. (web)
- **GPT-5.6**: limited preview 2026-06-26, public release 2026-07-09. Three tiers: **Sol** (most capable), **Terra** (middle), **Luna** (fastest, cheapest). A secondary source says government restrictions delayed the rollout. (web)
- **GPT-6 Astra**: 2026-09-03. OpenAI calls it its current frontier model. (web)
- **GPT-6 Sol / GPT-6 Luna**: 2026-09-22. Faster, cheaper models in the GPT-6 generation. (web)

## Other models
- **Whisper**: open-source speech recognition, released September 2022. Trained on 680,000 hours of audio; handles about 99 languages. (gk)
- **DALL-E 1 / 2 / 3**: image generation, 2021 / 2022 / 2023. DALL-E 3 was built into ChatGPT. Image generation later moved to GPT-4o's built-in image generation and the `gpt-image` API models. (gk)
- **Codex (2021)**: GPT-3 fine-tuned on code. The original API has been retired, and the name is reused for OpenAI's current coding agent. (gk)

## Methods
- **RLHF** (the original draft's description is broadly right): pre-train, supervised fine-tuning, train a reward model, then optimize with PPO. (gk)
- **Mixture of experts (MoE)**: confirmed for the open-weight gpt-oss models (web). For proprietary models like GPT-4 and GPT-4o, MoE is still industry speculation, not confirmed. (gk)
- **Reasoning models**: from o1 onward, OpenAI has trained models to generate a hidden chain of thought before answering. The GPT-5 family and later merge this into the main model line. (web/gk)

## Open questions
- What exactly is the GPT-6 lineup, and how is it priced? Sol and Luna now exist in both GPT-5.6 and GPT-6, so check which generation any reference means.
- Which models are still offered in the API, and which are retired? Neither draft tracks this.
- The GPT-5.6 policy and regulatory details come from secondary sources and weren't checked against OpenAI's own posts.
- Exact gpt-oss release day: sources say August 5–8, 2025.

## Related notes
- [[openai-models-20260921030308]]: the original unreviewed, truncated local-LLM draft this note corrects.

## Sources
- OpenAI GPT model release timeline (secondary compilation): https://hidekazu-konishi.com/entry/openai_gpt_model_release_timeline.html
- OpenAI Help Center, Model Release Notes: https://help.openai.com/en/articles/9624314-model-release-notes
- gpt-oss-120b model card (Hugging Face): https://huggingface.co/openai/gpt-oss-120b
- Introducing gpt-oss (OpenAI; returned 403 when fetched): https://openai.com/index/introducing-gpt-oss/
- GPT-5.6 (Wikipedia): https://en.wikipedia.org/wiki/GPT-5.6
- Introducing GPT-5.5 (OpenAI): https://openai.com/index/introducing-gpt-5-5/
- GPT-5.6 announcement (OpenAI): https://openai.com/index/gpt-5-6/
