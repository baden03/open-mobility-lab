# Research notes and conversation ingestion

[Deutsch](README_DE.md) · [Documentation](../README.md)

**Status:** Working method

This area is the intake point for conversation history, interviews, source reviews, experiments, and unresolved observations. Raw material is evidence of what was discussed—not proof that a claim is true or a decision was made.

## Suggested future structure

```text
docs/research/
├── conversations/   # dated, attributed summaries; raw exports only when permitted
├── sources/         # source notes and applicability assessments
├── experiments/     # plans, data links, results, and limitations
└── decisions/       # accepted decisions with rationale and consequences
```

## Ingestion workflow

1. Create a dated note with provenance, language, participants or anonymization, and scope.
2. Summarize ideas as observations, hypotheses, requirements candidates, questions, or decisions.
3. Check claims against primary sources or tests; record uncertainty and conflicting evidence.
4. Link each durable item into the relevant concept, engineering, regulatory, or roadmap page.
5. Update both language versions or mark translation as pending.
6. Preserve privacy, consent, copyright, and license constraints; do not publish sensitive raw transcripts.

## Note header template

```markdown
# Topic — YYYY-MM-DD

- Status: raw | reviewed | integrated
- Language: en | de | mixed
- Provenance: conversation, interview, source, or test identifier
- Privacy: public | anonymized | restricted
- Related pages: links
- Translation: complete | pending
```

## First ingestion target

The prior discussion of German e-mobility rules, adaptive mobility needs, dual propulsion, and a rowing-inspired hand drive should be imported as a reviewed summary. Legal claims require fresh primary-source verification before they move into the regulatory pages.

