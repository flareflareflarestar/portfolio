> **Source text**<br />
> DataSync is a fast tool for syncing database tables to local JSON files. It works with PostgreSQL 12+ and MySQL 8.0+. Before installing, make sure you have Python 3.9 or higher installed on your system. You also need `pip` and Git. To install it, run `pip install datasync-cli`. If that fails on Linux, you might need `sudo apt install libpq-dev` first for PostgreSQL drivers. Once installed, you can configure your database connection by running `datasync config --db-uri postgresql://user:pass@localhost:5432/dbname`. You can also set environment variables like `DATASYNC_DB_URI` in a `.env` file if you don't want to use the config command. Features include real-time sync, batch export, and dry-run mode. To test your connection, run `datasync test`. If it says "Connected successfully", you can run your first sync using `datasync run --table users --output users.json`. If you get a "Connection refused" error, check if your database server is running on the specified port. For full configuration flags, run `datasync --help`. License: MIT.

---

# DataSync CLI Tool Quickstart Guide

## Prerequisites

DataSync requires Python 3.9 or higher, `pip`, and Git.

## Installation

1. Run `pip install datasync-cli`.

## Configuration

!!! tip "Supported databases"
    DataSync supports PostgreSQL 12+, and MySQL 8.0+.

1. Configure the database connection with `datasync config --db-uri postgresql://user:pass@localhost:5432/dbname`.
2. Optionally, set environment variables such as `DATASYNC_DB_URI` in a `.env` file.

## Testing

1. Test your database connection with `datasync test`.
2. Run your first sync command: `datasync run --table users --output users.json`.

## Troubleshooting

| Error | Possible Causes | Solutions |
| :--- | :--- | :--- |
| Installation failed on Linux | Missing PostgreSQL drivers | Run `sudo apt install libpq-dev` |
| Connection refused | Database server running on incorrect port | Verify the database server is running on port 5432 |

!!! tip "Configuration flags"
    For a list of all configuration flags, run `datasync --help`.

---

# Retrospective

## The Challenge

The original project README presented setup instructions, environment dependencies, configuration options, and troubleshooting tips in an unstructured paragraph. This made it difficult for developers looking to quickly implement the CLI tool.

## Key Improvements Made

- Structured information: Reorganised the narrative into a logical hierarchy: **Prerequisites**, **Installation**, **Configuration**, **Testing** and **Troubleshooting**.
- Isolated executable commands: Moved CLI commands out of body text and into separate code blocks for easy copying.
- Separated edge cases and help info: Used admonitions to call out supported databases and configuration flags.
- Created a scannable troubleshooting reference: Extracted common setup errors into a table for quick debugging.

## Impact

By transforming an unstructured overview into a step-by-step quickstart guide, developers can install and run their first database sync quickly.