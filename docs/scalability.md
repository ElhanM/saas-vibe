# Scalability

- Before implementing, ask: "does this work at 10x current load?"
- Ask: "what is the worst-case query this generates?" — if it's a full table scan, fix it before shipping
- List endpoints must be paginated — never return unbounded collections
- N+1 queries: if you're fetching related data inside a loop, batch the fetch outside the loop
- Heavy work (file processing, emails, report generation) belongs in a background job, not the request path
- Scale concerns are proportional to traffic — don't over-engineer admin-only features on small datasets
