# Backend

Controllers accept validated input, authorize the action, invoke the operation, and return a redirect, view, or resource. Use Form Requests for nontrivial validation and authorize each record through its policy. Use named routes and route-model binding with ownership checks. Inject collaborators through constructors or action parameters.

Put multi-step operations in focused service classes and use Eloquent for persistence, relationships, and casts. Use transactions for related database writes and publish side effects after commit when practical. Keep transaction boundaries narrow and account for retries and concurrency. Introduce repositories or interfaces only for a concrete boundary or multiple implementations.

Map expected domain failures to specific validation, conflict, or authorization responses. Let Laravel handle unexpected exceptions and log sanitized diagnostics. Limit response fields and use API Resources when an API contract requires them. Follow [security](security.md) and [database](database.md).
