# Backend and synchronization

Need for a server: <which REQ cannot be satisfied locally>. If none, consider N/A.
Trust boundaries: <client/server/provider>. Authorization: <role → resource → permitted action>.
Sign-in/sign-out/account deletion: <behavior>; anonymous mode: <whether available>.

| Operation / REQ | Request / validation | Response | Errors | Authorization |
|---|---|---|---|---|
| <operation> | <fields, types, limits> | <contract> | <codes and UX> | <rule> |

Source of truth: <which system is authoritative>. Offline: <what is available>.
Sync: <timing, queue, versions>. Conflicts: <rule with example>.
Retries/idempotency: <keys and deduplication>; timeout/retry/backoff: <limits>.
Deletion and resynchronization: <how to avoid resurrecting deleted data>.
Schema/indexes/migrations: <description>; backup/restore: <rule and check>.
Environments/secrets: <where stored, without values>. Logs: <minimum required, without personal data>.
Expected load, limits, and budget: <hypothesis and validation method>.
