# Murshid Mini — Generated Results

This folder contains the generated JSON outputs and evaluation evidence from the four-day Murshid Mini project.

All results were produced using synthetic data and a simulated model (`FakeClient`).

## Output Files

| File | Description |
|---|---|
| `baseline_results.json` | Day 1 baseline responses and associated execution information. |
| `day2_results.json` | Day 2 structured-ticket and read-only tool test results. |
| `day3_results.json` | Day 3 golden test suite results for cases C01–C10. |
| `day4_results.json` | Day 4 controlled cache experiment results. |
| `final_report.json` | Final project evaluation, test results, caching comparison, hypothetical costs, and limitations. |
| `metrics.json` | Per-request metrics including trace IDs, mock calls, cache hits, tool calls, and Python execution time. |
| `synthetic_data.json` | Fictional service directory and application records used for testing. |

## Results Summary

### Day 1
Baseline service responses and empty-input validation were verified.

### Day 2
Five cases tested structured tickets, clarification, ownership checks, missing records, and unsupported modifications.

### Day 3
All ten golden test cases passed.

**Golden Test Pass Rate: 100% (10/10 selected cases)**

### Day 4
The controlled cache experiment produced:

- Requests: 3
- Mock-client calls without cache: 3
- Mock-client calls with cache: 1
- Cache hits: 2
- Cache hit rate: 66.7%

Cache expiration, version changes, and status-query exclusion were also tested.

## Data and Measurement Notes

- All records and identifiers are fictional.
- No real personal or government records were used.
- The project makes zero external model inference API calls.
- Recorded latency values measure local Python execution time and may vary between runs.
- Hypothetical costs are illustrative and do not represent actual charges.
- The results demonstrate behavior on selected mock test cases, not production accuracy or security.

## Reproducibility

To regenerate the outputs, run the final `notebooks/murshid.ipynb` notebook from top to bottom in Google Colab.

The notebook generates the result files in the `murshid_outputs/` folder.
