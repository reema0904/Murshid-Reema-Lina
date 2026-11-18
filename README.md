# Murshid Mini — LLM Application Engineering

**Course:** SDA-AIE-213 — LLM Application Engineering  
**Team Members:** Reema & Lina  
**Environment:** Google Colab | Python 3 | CPU  
**Project Duration:** 4 Days

## 1. Project Overview

Murshid Mini is a fictional, read-only service-information and application-status assistant developed as part of the LLM Application Engineering course.

The project demonstrates how to build and evaluate a controlled application using a simulated language model (`FakeClient`), structured tickets, validation, authorization, guardrails, testing, and caching.

The implementation uses Python's standard library and synthetic data only. It does not connect to a real language model, government system, or external inference API.

## 2. Project Development

The project was developed incrementally over four days.

| Day | Phase | Implementation |
|---|---|---|
| Day 1 | Foundations | Implemented `FakeClient`, `ask()`, input validation, and baseline results. |
| Day 2 | Structured Tickets and Tools | Added ticket extraction, validation, read-only status lookup, and ownership checks. |
| Day 3 | Guardrails and Testing | Implemented input/output checks, a controlled pipeline, and ten golden test cases. |
| Day 4 | Measurement and Caching | Added an exact-match cache, versioning, expiration, metrics, regression tests, and final reporting. |

## 3. System Architecture

The application follows a controlled workflow:

1. Receive the user question and separate demo session identity.
2. Validate the input.
3. Extract and validate the structured ticket.
4. Route the request to the appropriate function.
5. Retrieve synthetic information or return clarification/refusal.
6. Validate the response.
7. Return the result with trace and timing information.

Day 4 adds an optional cache for supported public FAQ questions.

The `FakeClient` returns predefined responses rather than generating text using a real LLM.

## 4. How to Run

1. Open `notebooks/murshid.ipynb` in Google Colab.
2. Select Python 3 as the runtime.
3. Set Hardware Accelerator to **None (CPU)**.
4. Select **Runtime → Restart session and run all**.
5. Run all cells in order, from Day 1 through Day 4.
6. Review the test outputs and generated JSON files.

No external packages, API keys, GPU, or paid services are required.

## 5. Testing and Evaluation

### Day 1 — Baseline Testing

Verified predefined Arabic and English service responses, clarification behavior, and empty-input validation.

### Day 2 — Tool Testing

Tested five scenarios covering authorized lookup, missing reference, absent record, unsupported cancellation, and unauthorized access.

### Day 3 — Golden Test Suite

The application passed all ten selected test cases (C01–C10).

**Result: 10/10 passed (100%)**

The tests cover normal responses, clarification, authorization, unsupported requests, invalid input, instruction override, and malformed output.

### Day 4 — Cache Evaluation

| Metric | Without Cache | With Cache |
|---|---:|---:|
| Requests | 3 | 3 |
| Mock-client calls | 3 | 1 |
| Cache hits | 0 | 2 |
| Hit rate | 0% | 66.7% |

Additional verification confirmed:

- Cache expiration after 300 seconds.
- Cache invalidation when the prompt or directory version changes.
- Application-status requests are excluded from shared caching.
- Previous test cases continue to pass.
- Synthetic records remain unchanged.

The recorded latency measures Python execution time, not real LLM inference time.

## 6. Synthetic Data and Security

All application records and service information are fictional.

The sample dataset includes:

- `REF-1001`: Authorized example with status `under_review`.
- `REF-1002`: Record belonging to another demo user.
- `REF-9999`: Nonexistent reference used for testing.

Authorization is checked against a separate demo session identity. The system does not permit users to modify application records.

The cache stores only supported public FAQ answers, not private application-status results.

## 7. Limitations and Future Improvements

**Limitations:**

- The application uses a simulated model, not a real LLM.
- The records and identities are synthetic.
- Input guardrails rely on limited rules and keyword matching.
- The application is not intended for production deployment.

**Future improvements:**

- Expand the test suite with more diverse and adversarial inputs.
- Evaluate a real language model separately.
- Implement production-level authentication and authorization.
- Improve error handling and monitoring.

The 100% test pass rate applies only to the selected classroom test cases and does not establish overall application safety or accuracy.

## 8. Cost and Performance

The project makes zero external model inference API calls and incurs no model API charges.

The final report includes an illustrative cost example of USD 0.0036 per request using hypothetical token prices. This is not actual usage, billing, or verified savings.

## 9. Project Files

- `notebooks/murshid.ipynb` — Final cumulative notebook containing Days 1–4.
- `murshid_outputs/` — Generated results, synthetic data, metrics, and final reports.

Earlier notebook versions are retained as development checkpoints.

## 10. Attribution

This project was developed as part of the SDA-AIE-213 LLM Application Engineering course, using the instructor's provided materials, examples, and laboratory instructions.

**Instructor's Repository:**  
https://github.com/almiyead-rgb/murshid-llm-application-engineering-sda-aie-213

**Project Team:** Reema & Lina
