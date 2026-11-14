# Database

Use Laravel migrations and Eloquent conventions across MySQL, MariaDB, PostgreSQL, SQLite and SQL Server. Ship module-owned migrations before introducing routes that depend on their tables. Use explicit foreign key delete behavior, indexes for actual query paths, unique constraints for invariants, and transactions for related writes. Check engine-specific SQL against both supported engines when it matters.

Add new migrations for changes to released schemas. Prefer additive changes and staged backfills for deployed data. Define retention and recovery for destructive changes. Keep connection verification read-only. Run migrations once through the authorized finalization step or a controlled release. Keep ordinary requests free of automatic schema changes. Surface actionable, redacted migration errors and test interrupted DDL recovery. See [database operations](../docs/database.md).
