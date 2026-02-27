# Database Validation Notes

## Data Integrity Checks
- Verify data is stored correctly after transactions
- Validate relationships between tables
- Ensure no duplicate or orphan records

## Business Rule Validation
- Confirm calculated fields match expected values
- Verify status updates reflect business logic
- Validate timestamps and audit fields

## Data Consistency
- Compare UI data with database records
- Validate API responses against stored data
- Ensure updates propagate correctly

## Negative Scenarios
- Invalid data should not be persisted
- Rollback behavior works correctly on failures

## Performance Considerations
- Query response times are acceptable
- No unnecessary duplicate queries
