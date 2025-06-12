
# Ultimate PostgreSQL & SQLC Snippets for VS Code

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql)
![SQLC](https://img.shields.io/badge/SQLC-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![VS Code](https://img.shields.io/badge/Visual_Studio_Code-007ACC?style=for-the-badge&logo=visual-studio-code)
![License](https://img.shields.io/badge/license-MIT-blue?style=for-the-badge)

Supercharge your database workflow with this comprehensive collection of snippets for **PostgreSQL** and **SQLC**. This collection is designed to eliminate boilerplate, enforce best practices, and accelerate development for anyone working with SQL and the SQLC code generator.

## Key Features

-   **Comprehensive SQLC Coverage**: Snippets for all core SQLC operations (`:one`, `:many`, `:exec`), including common patterns like returning IDs and batch inserts.
-   **Advanced SQL Patterns**: Tackle complex scenarios with snippets for JOINs, JSONB queries, array operations, full-text search, and transaction blocks.
-   **PostgreSQL DDL Mastery**: Quickly scaffold tables with audit columns, indexes, enums, functions, and triggers for auto-updating `updated_at` timestamps.
-   **Modern PostgreSQL Types**: Easy-to-use snippets for `UUID`, `JSONB`, arrays, and `TSVECTOR` for full-text search.
-   **SQLC v2 Ready**: Includes snippets leveraging named parameters (`@param`) and other modern SQLC features.
-   **Configuration & Utilities**: Get a head start with a `sqlc.yaml` template and helpers for migrations and database extensions.

## How to Set Up

To use these snippets, you need to add them to your VS Code user snippets file.

1.  In VS Code, go to **File > Preferences > Configure User Snippets**. (On macOS: **Code > Settings > Configure User Snippets**).
2.  Select `sql.json` from the dropdown. If it doesn't exist, VS Code will create it for you.
3.  Copy the entire content of the `snippets.json` file provided and paste it between the curly braces `{}` in your `sql.json` file.
4.  Save the file. The snippets are now ready to use in any `.sql` file.

## How to Use

In a `.sql` file, simply start typing one of the prefixes below and press `Tab` or `Enter` to insert the code block. Use `Tab` to navigate through the placeholders (`${1:name}`, `${2:table}`, etc.) to quickly fill in the details.

**Example:**

1.  Type `sqlcinsert`.
2.  Press `Tab`.
3.  The snippet for an insert operation will appear, with the query name (`CreateUser`) already selected for you to change.

## Available Snippets

### SQLC Core Operations
| Prefix | Description |
|---|---|
| `sqlcone` | Fetches a single row from a table (`:one`). |
| `sqlcmany` | Fetches multiple rows, often with pagination (`:many`). |
| `sqlcinsert` | Inserts a new record and returns specified columns (`:one`). |
| `sqlcupdate` | Updates a record based on its ID (`:exec`). |
| `sqlcdelete` | Deletes a record based on its ID (`:exec`). |
| `sqlcbatch` | A template for a batch insert operation (`:batchexec`). |
| `sqlcv2` | SQLC v2 query using named parameters (`@param`). |

### PostgreSQL DDL (Data Definition)
| Prefix | Description |
|---|---|
| `pgtbl` | Creates a new table with standard audit columns (`id`, `created_at`, `updated_at`). |
| `pgidx` | Creates an index on one or more columns. |
| `pgexpridx` | Creates an index on an expression (e.g., `LOWER(email)`). |
| `pgpartialidx`| Creates a partial index with a `WHERE` clause for optimization. |
| `pgenum` | Creates a new ENUM type. |
| `pgfunc` | Creates a basic PL/pgSQL function. |
| `pgtrigger` | Creates a trigger to automatically update the `updated_at` timestamp. |
| `pgext` | Creates a PostgreSQL extension (e.g., `uuid-ossp`). |

### PostgreSQL DML & Advanced Queries
| Prefix | Description |
|---|---|
| `pgcte` | A query using a Common Table Expression (CTE) with a `WITH` clause. |
| `pgjsonb` | A `JSONB` column definition with a default empty object. |
| `pgarray` | A `TEXT[]` array column definition. |
| `pgfts` | A `TSVECTOR` column for full-text search. |
| `pguuid` | Generates a UUID using `gen_random_uuid()`. |
| `pgjoin` | A `JOIN` query that aggregates related data into a JSON array. |
| `pgarrayagg` | A query that uses `ARRAY_AGG` to aggregate values into an array. |
| `pgjsonbuild` | A query that uses `jsonb_build_object` to construct a JSON object. |

### Security & Migrations
| Prefix | Description |
|---|---|
| `pgrls` | A template for enabling Row Level Security and creating a policy. |
| `pggrant` | Grants `SELECT`, `INSERT`, `UPDATE`, `DELETE` permissions on a table to a role. |
| `pgaddcol` | Adds a new column to an existing table. |
| `pgdropcol` | Drops a column from an existing table. |

### Configuration & Utilities
| Prefix | Description |
|---|---|
| `sqlcconfig` | A complete `sqlc.yaml` configuration template for Go (pgx/v5). |
| `sqlcmodel` | An SQLC comment to override a generated model's name. |
| `pgexplain` | Wraps a query with `EXPLAIN (ANALYZE, BUFFERS, VERBOSE)` for performance analysis. |
| `pgbegin` | A `BEGIN/ROLLBACK` block for testing queries safely. |

## Core Benefits

-   **Reduce Errors**: Pre-defined structures minimize typos and common syntax mistakes.
-   **Enforce Best Practices**: Snippets include audit columns, proper indexing, and standard SQLC naming conventions.
-   **Accelerate Development**: Spend less time writing boilerplate SQL and more time focusing on your application's logic.
-   **Seamless SQLC Integration**: Designed from the ground up to work perfectly with SQLC's query parsing and code generation.

## License

This project is licensed under the MIT License.
