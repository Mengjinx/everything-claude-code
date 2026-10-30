# Test Evidence Registry

Reuse an existing registry when present. Store only synthetic or sanitized examples.
One TEST-ID can reference multiple original findings without merging their dispositions.

| TEST-ID | Original finding / requirement | State | Level | Input and expected observable behavior | Real / simulated boundary | Test file / node | Exact command | Environment / version | Exit code | Evidence reference |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TEST-AUTH-001 | F-001 | unverified | E2E | Synthetic user from facility A cannot read facility B record | Record which gateway, app, and IRIS components are real | Record path and test selector | Record reviewed invocation; do not embed credentials | Record target identity and version | NOT RUN | Link to restricted evidence store |

For each unresolved point, record the blocker, next permitted check, and any required access.
A successful transport response does not prove authorization or data isolation.
