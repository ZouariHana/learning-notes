# Benchmarking vs Profiling

| Aspect            | Benchmarking 🏎️                          | Profiling 🔍                          |
|-------------------|-------------------------------------------|----------------------------------------|
| **Goal**          | Measure overall performance               | Analyze where time/resources are spent |
| **Scope**         | High-level (whole system/component)       | Fine-grained (functions, lines, memory)|
| **Question**      | “How fast is it overall?”                 | “Why is it slow / resource-heavy?”     |
| **Output**        | Execution time, throughput, latency       | Hotspots, function time, allocations   |
| **Use Case**      | Compare algorithms, track regressions     | Find bottlenecks, guide optimization   |
| **When Used**     | First step: check performance             | Second step: diagnose inefficiencies   |