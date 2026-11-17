# Acme Orders checkout (Codex)

This project follows the supplied TypeScript code for POST /orders. Its central story is: reserve stock before payment; after a successful charge, call the order save path and order.placed publication before answering 201; on payment decline, await reservation release before answering 402.

## Scenarios and levels

- **Order placed successfully** is the default: HTTP input, minimal validation, generated order ID and total, stock reservation, payment, order construction, save(), publish(), and HTTP 201.
- **Payment declined; release stock and answer 402** shares the request/reservation prefix. Provider 402 becomes PaymentDeclinedError, release(reservation.id) is awaited, the original error is rethrown, and the controller maps it to HTTP 402. Save and publish are not reached.

Four levels reveal increasing detail: (1) checkout overview with four participants; (2) components and HTTP boundaries; (3) actual function calls and error propagation; (4) data, decisions, exact SQL arguments, event envelope and private helpers. Each scenario has a six-stop guided tour. No deployment instances were invented to fill a level.

## Evidence and source limits

Sources use repository name **repository** and paths relative to that repository. Code claims cite the files and line ranges that were read. Verified means confirmed in source, not observed during execution. The API client is an inferred caller abstraction; no UI or caller code was supplied.

The source has two important stubs:

- OrderRepository.save() calls query() with an orders INSERT and one order_items INSERT per item. query() is empty. No SQL execution, database connection, transaction or durable persistence is established. A PostgreSQL comment alone is not treated as evidence of a working database.
- EventBus.publish() builds { type, payload, publishedAt } and awaits send('orders', type, message). send() is empty. The order.placed invocation and envelope are shown, but broker delivery, acknowledgement, protocol, product and downstream consumers are unknown.

Inventory and payment are modeled only at the HTTP interfaces visible from their clients. Their implementations are absent. Successful remote HTTP statuses are unspecified, so no success status was invented. The successful scenario assumes valid Reservation and Charge response shapes. PaymentGateway checks only provider status 402; other statuses are parsed and cast as Charge without checking status=succeeded.

The declined scenario assumes release() fetch resolves and the remote reservation API honors DELETE. The code ignores the DELETE status, so a resolved HTTP error response would still permit API 402 without confirmed stock restoration. If release fetch rejects, the original-error rethrow is not reached; that failure is outside these two scenarios.

The order ID is newly generated on each placeOrder() call and is passed as the payment Idempotency-Key. This is not evidence of deduplication across repeated incoming checkout requests. Currency, amount units and item-level input validation are not established by this code. Inventory items are serialized unchanged, so unitPrice also travels despite the narrower reserve() parameter type.

## Illustrative choices and omissions

Project illustrative metadata remains true. Payload values are handwritten examples, with a synthetic SKU, quantity 2, unitPrice 25 and total 50. Customer, payment-method and authorization values are redacted. Generated identifiers, provider decline codes and timestamps are symbolic. No credentials or personal data were copied. No runtime timings were invented.

The project concentrates on the two requested outcomes. It does not animate invalid input (400), out of stock (409), malformed JSON, general transport failures, release failure, retries, cancellation, database/broker implementations or event consumers.

Only declarative project files were written. The source repository and reference files were read-only. No network, npm command or browser was used. All YAML files passed the supplied JSON Schemas. Entity, payload, flow and scenario references, evidence citations, source line ranges, hierarchy, guided tours and scenario ordering were checked. Browser rendering and live service behavior were not observed.
