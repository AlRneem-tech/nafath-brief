
Track: Cybersecurity

## Overview
A reliable 5G service for emergency responders depends on six IT fields working together. Software must handle requests safely, especially when failed requests are retried. AI can help predict network congestion, but its models must be evaluated to avoid unreliable predictions. Mobile applications should remain useful when responders lose connectivity and synchronize data carefully after reconnecting. Network slicing can help reserve network resources for emergency communications, although it cannot eliminate every outage. Cybersecurity processes help teams detect, contain, and recover from attacks. Data engineering supports accurate reports about service usage across regions and days. Together, these fields help the operator make informed decisions, protect critical communications, and maintain service continuity under difficult conditions. Effective planning must also account for the incident response lifecycle when a cyber attack threatens the service.
## Software
HTTP safe methods are read-only by definition; GET, HEAD, OPTIONS and TRACE are safe. Idempotent methods produce the same intended server effect when the same request is repeated. PUT and DELETE are idempotent, although they are not both safe. This distinction matters when a response is lost and a client retries a request. Automatic retries of non-idempotent requests can cause unintended duplicate actions.

Resource: RFC 9110 - HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html
## AI
Overfitting occurs when a model learns patterns specific to its training data and performs poorly on unseen data. For congestion prediction, an overfitted model may appear accurate on historical training records but fail under new network conditions. Cross-validation evaluates a model across multiple training and validation splits. Comparing validation performance helps identify overfitting and supports more reliable model selection before deployment.

Resource: Scikit-learn - Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html
## Mobile
An emergency responder's mobile app should keep essential information available locally when connectivity is lost. User actions and updates can be stored on the device and queued for synchronization when the network returns. The app should handle synchronization failures, detect conflicting changes, and apply a defined conflict-resolution strategy. Clear offline status indicators help responders understand whether their latest updates have reached the server.

Resource: Android Developers - Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first
## Networking
5G network slicing allows an operator to create logically separated networks on shared physical infrastructure, with different performance and management requirements. A dedicated slice could prioritize emergency responders' traffic and support service reliability during congestion. However, slicing does not guarantee uninterrupted service by itself. Radio coverage, transport capacity, core network failures, and power outages must also be addressed.

Resource: 3GPP - Release 15 - https://www.3gpp.org/specifications-technologies/releases/release-15
## Cybersecurity
The incident response lifecycle includes preparation; detection and analysis; containment, eradication, and recovery; and post-incident activity. During an attack on the emergency 5G service, the team should identify affected systems, limit the attack's spread, remove the threat, restore services safely, and document lessons learned. Preparation and clear responsibilities help responders act quickly while preserving evidence and maintaining essential communications where possible.

Resource: NIST - Computer Security Incident Handling Guide - https://csrc.nist.gov/pubs/sp/800/61/r2/final
## Data
A star schema stores measurable facts, such as service usage, in a central fact table connected directly to dimension tables such as date and region. A snowflake schema normalizes dimensions into additional related tables. For reporting usage by region and day, a star schema is often simpler because analysts can query the fact table and its dimensions with fewer joins. The choice should still reflect data quality and maintenance needs.

Resource: Microsoft - Star schema guidance - https://learn.microsoft.com/en-us/power-bi/guidance/star-schema
## Misconception in My Track

## Open Question
