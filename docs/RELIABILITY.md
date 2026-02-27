# Reliability

> Reliability requirements, SLOs, error handling, and operational expectations.

## Service Level Objectives (SLOs)

<!-- TODO: Define your SLOs.
     Example:
     | Metric | Target | Measurement |
     |--------|--------|-------------|
     | Availability | 99.9% | Uptime over 30-day window |
     | Latency (p50) | < 200ms | API response time |
     | Latency (p99) | < 2s | API response time |
     | Error rate | < 0.1% | 5xx responses / total requests |
-->

## Error Handling Strategy

- All errors must be typed and structured (no bare string throws).
- Distinguish between retryable and non-retryable errors.
- Log errors with context: request ID, user ID, operation, stack trace.
- User-facing errors must be helpful and actionable.
- Internal errors must not leak implementation details.

## Failure Modes

<!-- TODO: Document known failure modes and mitigation.
     Example:
     | Failure | Impact | Mitigation |
     |---------|--------|------------|
     | Database unavailable | Full outage | Connection pooling, retry with backoff |
     | External API timeout | Degraded feature | Circuit breaker, fallback response |
-->

## Monitoring & Alerting

<!-- TODO: Define what's monitored and alerting thresholds.
     - Health check endpoints
     - Key business metrics
     - Error rate spikes
     - Latency degradation
-->

## Incident Response

<!-- TODO: Define incident response process.
     - Severity levels
     - Escalation paths
     - Post-incident review process
-->
