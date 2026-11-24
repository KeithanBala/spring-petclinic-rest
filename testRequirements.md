
## Ticket A: Filtering & Pagination Endpoint

### Requirement:  
Add GET /api/owners/search accepting optional query parameters lastName (case-insensitive partial match) and city (exact match).

### Constraints:  
• Return 200 OK with an empty list [] if no matches are found (do not return 404).  
• Ensure existing GET /api/owners tests still pass.  

### What Codility tests here: 
Query parameter binding (@RequestParam(required = false)), JPA query derivation or custom JPQL, and null handling.

## Ticket B: Business Rule Validation & Status Codes

### Requirement: 
Update POST /api/visits so a pet cannot have more than 2 visits scheduled on the same date, and visits cannot be booked on Sundays.

### Constraints:  
• Return 400 Bad Request or 422 Unprocessable Entity with a clear JSON error body when violated.  
• Return 404 Not Found if the petId does not exist.  

### What Codility tests here:   
Service-layer validation, @RestControllerAdvice exception mapping, and java.time.LocalDate edge cases.

## Ticket C: Partial Update (PATCH) & DTO Mapping

### Requirement:
Implement PATCH /api/pets/{petId} allowing callers to update only name or birthDate without overwriting omitted fields with null.

### Constraints:
• Reject blank strings for name with 400 Bad Request.  
• Write MockMvc integration tests covering partial updates, invalid payloads, and missing IDs.
