# Payment Platform

Reference implementation of a scalable payment processing system using .NET 8, RabbitMQ, Redis and PostgreSQL.

## Problem

Payment systems must ensure reliability, consistency and fault tolerance while handling retries and external service failures.

This project demonstrates common enterprise payment architecture patterns.

## Features

* Payment creation
* Payment status tracking
* Idempotency support
* Retry mechanism
* Outbox pattern
* Event-driven processing

## Architecture

API
↓
Payment Service
↓
PostgreSQL
↓
RabbitMQ
↓
Background Workers

## Technology Stack

* .NET 8
* PostgreSQL
* RabbitMQ
* Redis
* Docker

## Design Decisions

### Why RabbitMQ instead of Kafka?

Pros:

* Easier operations
* Lower complexity
* Better fit for business workflows

Cons:

* Lower throughput

Decision:
Payment workloads prioritize reliability and simplicity over event-stream analytics.

### Why Outbox Pattern?

Pros:

* Prevents data inconsistency
* Reliable event publishing

Cons:

* Additional implementation complexity

Decision:
Data consistency is critical in payment systems.

### Why Redis?

Pros:

* Fast access
* Idempotency tracking

Cons:

* Additional infrastructure

Decision:
Prevents duplicate payment processing.

## Future Improvements

* Multi-region deployment
* Fraud detection module
* Distributed tracing
* OpenTelemetry support
