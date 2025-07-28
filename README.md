# data_engineer_dbt

Learn and understand the basics of being a data engineer and work with DBT.

Please remember to add your local db details in profiles.yml file. You can also setup the dbt for BigQuery, SnowFlake, RedShift and DataBricks.

## Project Overview

This project demonstrates how to use [dbt](https://www.getdbt.com/) (Data Build Tool) for data engineering workflows, including setting up a local development environment, seeding raw data, and building views in a local Postgres database.

---

## Prerequisites

- **Python 3.7+** (recommended: Python 3.11)
- **PostgreSQL** (local instance running and accessible)
- **pip** (Python package manager)

---

## Setup Instructions

### 1. Create and Activate a Python Virtual Environment

A Python virtual environment is already present in the `dbt_env/` directory. If you need to recreate it, run:

```bash
python3 -m venv dbt_env
```

Activate the virtual environment:

- **macOS/Linux:**
  ```bash
  source dbt_env/bin/activate
  ```
- **Windows:**
  ```cmd
  dbt_env\Scripts\activate
  ```

You should see `(dbt_env)` in your terminal prompt when the environment is active.

---

### 2. Install dbt and Required Packages

With the virtual environment activated, install dbt and the Postgres adapter:

```bash
pip install dbt-core dbt-postgres
```

---

### 3. Configure dbt

- Edit your `profiles.yml` (usually in `~/.dbt/profiles.yml`) to point to your local Postgres database.
- Update connection details as needed for your environment.

---

### 4. Seed Raw Data

To load the raw data from CSV files in `jaffle_shop/seeds/` into your Postgres database, run:

```bash
dbt seed
```

This will insert the data into your database as tables.

---

### 5. Build Models (Create Views)

To build the dbt models (e.g., create views from the seeded data), run:

```bash
dbt run
```

This will execute the SQL models in `jaffle_shop/models/` and create the corresponding views in your database.

---

## Example Workflow

```bash
# Activate the virtual environment
source dbt_env/bin/activate

# Install dbt and Postgres adapter
pip install dbt-core dbt-postgres

# (Optional) Edit ~/.dbt/profiles.yml to configure your Postgres connection

# Seed the raw data
dbt seed

# Build the models (create views)
dbt run
```

---

## Additional Resources

- [dbt Documentation](https://docs.getdbt.com/docs/introduction)
- [dbt Postgres Adapter](https://docs.getdbt.com/reference/warehouse-setups/postgres-setup)
