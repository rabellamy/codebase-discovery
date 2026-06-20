# Domain Model Template

When generating the Domain Model analysis, strictly adhere to the following markdown structure.

### Domain Model & Core Entities
* **Entities & Relationships**: Exhaustive list of all database tables, ORM models, and domain entities:
  * `[Entity Name 1]`: Description of purpose and key relationships (1:N, N:M).
  * `[Entity Name 2]`: Description of purpose and key relationships (1:N, N:M).
  * `...`
* **State Management**: Comprehensive breakdown of persistence strategies:
  * `[Primary database 1]`
  * `[Caching layer 1]`
  * `...`
* **Modeling Issues**: Exhaustive list of all identified bottlenecks:
  * `[Modeling Anti-pattern 1]`: Details...
  * `[Modeling Anti-pattern 2]`: Details...
  * `...`
