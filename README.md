# Python AI Application — Data Pipeline Extension

> Original AI application retained as a learning project. This README outlines a separately scoped data-ingestion extension.

## Cisco-aligned skills
Python, REST APIs, SQL, ETL/ELT, data quality and cloud data platform concepts.

## Proposed data flow
API/source metadata → Python extraction → JSONL raw landing → Snowflake RAW → dbt staging → usage analytics mart.

## Engineering considerations
- Keep prompts, secrets and personal data out of logs.
- Validate payload shape before processing.
- Use bounded retries and request timeouts.
- Track run_id, source, records_read, records_written and status.
- Build tests with synthetic payloads.

## SQL example
```sql
select date_trunc('day', event_timestamp) as event_day,
       count(*) as request_count
from analytics.fct_application_events
group by 1;
```

The pipeline is a proposed extension, not a claimed deployed system.

[LinkedIn](https://www.linkedin.com/in/shivam-mathur-172751289)