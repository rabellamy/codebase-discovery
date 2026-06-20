# Code Quality Template

When generating the Code Quality analysis, strictly adhere to the following markdown structure.

### Code Quality & Test Coverage Signals
* **Test Coverage**: Detailed test coverage percentages with a full breakdown:
  * Unit tests.
    * `[Testable entity/module 1]`: `[Percentage]%`
    * `[Testable entity/module 2]`: `[Percentage]%`
    * `...`
  * Integration tests.
    * `[Testable entity/module 1]`: `[Percentage]%`
    * `...`
  * E2E tests.
    * `[Testable entity/module 1]`: `[Percentage]%`
    * `...`
* **Testing Patterns**: Exhaustive evaluation of testing quality:
  * `[Testing Pattern 1]`: Reliance on mocks vs real databases, test suite execution speed/flakiness.
  * `[Testing Pattern 2]`: Details...
  * `...`
* **Code Health Metrics**: Comprehensive metrics across the entire codebase:
  * `[Cyclomatic complexity metric 1]`: Details.
  * `[Duplication metric 1]`: Details.
  * `...`
* **Observability**: Exhaustive list of implementations:
  * `[Metric implementation 1]`: Implementation details.
  * `[Logger implementation 1]`: Implementation details.
  * `[Tracer implementation 1]`: Implementation details.
  * `...`
