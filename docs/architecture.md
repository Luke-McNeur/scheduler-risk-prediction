# Architecture Documentation

## System Design Principles

This POC follows distributed systems patterns from Site Reliability Engineering:

### Task Master Pattern
- **Airtable** acts as the single source of truth (Task Master)
- All appointment state stored centrally
- Workflow reads current state, processes, writes results

### Stateless Worker Pattern  
- **n8n workflow** is a stateless worker
- No state stored between executions
- Each run is independent and repeatable

### Exactly-Once Semantics
- Each appointment processed once per execution
- Atomic updates to Airtable prevent duplicate processing

## Data Flow