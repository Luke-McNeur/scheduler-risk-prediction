# Scheduler Risk Prediction POC

AI-powered appointment risk prediction for home care scheduling.

## Overview

This POC validates that caregiver historical completion rates can predict appointment risk and identify high-risk shifts requiring contingency coverage.

**Status**: Proof of Concept  
**Stack**: n8n, Airtable, OpenRouter (GPT-4o-mini)

## Quick Start

1. Import Airtable schema from `/data/airtable-schema/`
2. Configure credentials (see `/config/.env.example`)
3. Import n8n workflow from `/workflows/n8n/appointment-risk-predictor.json`
4. Run manual trigger to test

## Documentation

- [POC Handoff Documentation](docs/poc-handoff.md) - Complete context and architecture
- [Architecture Decisions](docs/architecture.md) - System design rationale

## Risk Scoring Model

- **High Risk (70-85)**: Caregiver completion rate < 80%
- **Moderate Risk (50-65)**: Caregiver completion rate 80-90%
- **Low Risk (15-40)**: Caregiver completion rate > 90%

## Out of Scope (Post-POC)

- Automated notifications
- Multi-factor prediction models
- Contingency scheduling automation
- Production error handling

## License

MIT