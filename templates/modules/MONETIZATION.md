# Monetization

Model: <one-time purchase/subscription/IAP/ads>. Value without payment: <description>.
Products/entitlements: <what each product unlocks>; pricing: <hypothesis, regions, validation>.
Source of truth for purchases: <description, related ADR>.

| Situation | UI behavior | Data/access | TEST |
|---|---|---|---|
| Success / repeated callback | <description> | <exactly-once effect> | <ID> |
| Cancellation / error / pending | <description> | <no incorrect access grant> | <ID> |
| Restore / new device | <description> | <restoration> | <ID> |
| Refund / expiry / offline | <description> | <rule> | <ID> |

For ads: placement, frequency, optional rewarded ads, no-fill, interruptions, reward accounting, data minimization. Mark irrelevant rows N/A.
Sandbox checks: <environment and evidence>. Platform/SDK requirements: <official sources and verification date>.
