# Murshid Mini — Project Notebooks

This folder contains the Google Colab notebooks developed throughout the four-day Murshid Mini project.

## Final Notebook

**`murshid.ipynb`** is the final cumulative notebook containing the implementation of all four days.

### Day 1 — Foundations
- Created the synthetic service directory.
- Implemented the `FakeClient` mock model.
- Built the `ask()` interface.
- Validated initial responses and saved baseline results.

### Day 2 — Structured Tickets and Tools
- Implemented structured ticket extraction and validation.
- Added the read-only `check_status` tool.
- Implemented record ownership verification.
- Tested five application-status scenarios.

### Day 3 — Guardrails and Testing
- Added input and output validation.
- Built the controlled application pipeline.
- Implemented the golden test suite (C01–C10).
- Achieved 10/10 passing tests.

### Day 4 — Measurement and Caching
- Implemented an exact-match cache for supported public FAQs.
- Added cache versioning and a 300-second expiration time.
- Measured mock-client calls and cache hits.
- Verified previous functionality through regression testing.
- Generated the final evaluation report and metrics.

## How to Run

1. Open `murshid.ipynb` in Google Colab.
2. Select Python 3 and CPU.
3. Run all cells sequentially from the beginning.
4. Review the generated results in `murshid_outputs/`.

No additional Python packages or external API keys are required.

## Previous Versions

Earlier notebooks are retained to document the development progress across Days 1–3.

The final `murshid.ipynb` should be used for execution and evaluation.
