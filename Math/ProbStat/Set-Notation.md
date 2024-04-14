# Set Notation

In probability theory, set notation follows the same rules as ordinary set notation but with specific interpretations tailored to probability concepts.

## Sample Space and Events

- **Sample Space ($\mathbb{\Omega}$):** This represents the universal set containing all possible outcomes of an experiment.

- **Event ($E$):** Any subset of the sample space $\Omega$.

Certain types of events have specific names:
- **Elementary Event ($\omega$):** Denotes a particular outcome of an experiment.
- **Null Event ($\varnothing$):** Represents the absence of any occurrence, essentially the empty set.

## Interpretation of Set Operations

- **Elementary Event in Event ($\omega \in E$):** Implies that event $E$ occurs when outcome $\omega$ occurs.
- **Elementary Event not in Event ($\omega \notin E$):** Implies that event $E$ does not occur when outcome $\omega$ occurs.
- **Subset ($E \subset F$):** Occurrence of $E$ implies occurrence of $F$.
- **Intersection ($E \cap F$):** Both $E$ and $F$ occur.
- **Union ($E \cup F$):** At least one of $E$ or $F$ occurs.
- **Mutually Exclusive ($E \cap F = \varnothing$):** Both $E$ and $F$ cannot simultaneously occur.
- **Complement ($E^c$ or $\overline{E}$):** Represents the event that $E$ did not occur.

## Laws of Set Theory

- **DeMorgan's Laws:**
  - $(A \cap B)^c = A^c \cup B^c$
  - $(A \cup B)^c = A^c \cap B^c$
  
- **Involution:** $(A^c)^c = A$

- **Distributive Laws:**
  - $(A \cup B) \cap C = (A \cap C) \cup (B \cap C)$
  - $(A \cap B) \cup C = (A \cup C) \cap (B \cup C)$
 
 - **Associative Laws:**
   - $(A \cup B) \cup C = A \cup (B \cup C)$
   - $(A \cap B) \cap C = A \cap (B \cap C)$

- **Identity Laws:**
   - $A \cup \varnothing = A$
   - $A \cap \Omega = A$

- **Absorption Laws:**
   - $A \cup (A \cap B) = A$
   - $A \cap (A \cup B) = A$

- **Complement Laws:**
   - $A \cup A^c = \Omega$
   - $A \cap A^c = \varnothing$

- **Idempotent Laws:**
   - $A \cup A = A$
   - $A \cap A = A$
   
## References:
1. Brian Caffo, (Instructor). (2024). _Mathematical Biostatistics Boot Camp 1_. Coursera. https://www.coursera.org/learn/biostatistics?specialization=advanced-statistics-data-science