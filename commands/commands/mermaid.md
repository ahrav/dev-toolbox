# Claude Code Command: Mermaid ERD Generator

This command creates entity relationship diagrams from SQL files using Mermaid syntax.

## Key Functionality

The tool processes SQL migration files and database schemas to generate visual ERDs. It follows a six-step workflow:

1. **Argument parsing** to identify source and output paths
2. **SQL file discovery** in common locations like `migrations/`, `db/`, and `schema/` directories
3. **Schema extraction** from CREATE TABLE statements, identifying tables, columns, keys, and relationships
4. **Mermaid diagram generation** using standard ERD syntax
5. **Validation** via mermaid-cli when available
6. **Output configuration** supporting single files, separate schemas, or multiple databases

## Supported Formats

The command handles multiple SQL dialects including PostgreSQL, MySQL, and SQLite, plus various migration frameworks (Rails, Django, Flyway).

## Usage Examples

The documentation provides three primary use cases: processing entire migration directories, converting specific schema files, and handling wildcard patterns across multiple SQL files.

The output defaults to `docs/erd.md` unless otherwise specified.