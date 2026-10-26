# ADR-0004: PostgreSQL и Docker Compose

## Status
Accepted

## Context
Бележките се губят, когато приложението използва паметта.

## Decision
Използваме PostgreSQL 17 с Docker Compose.
DATABASE_URL свързва приложението с базата.
Именуван volume запазва данните.
Healthcheck и depends_on осигуряват готовността на базата.

## Consequences
Предимства: постоянни данни, лесно стартиране и обща конфигурация.
Недостатъци: повече компоненти, нужда от backups и управление на volumes.
