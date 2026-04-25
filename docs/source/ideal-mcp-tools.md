# MCP Tool Reference

This page summarizes the MCP tools currently registered by `sktime-mcp`. It is intended as a compact reference for developers and advanced users; the user-facing workflows remain in [Usage Examples](usage-examples.md).

The active MCP surface is organized around discovery, instantiation, execution, data loading, persistence, and background jobs. Deprecated compatibility handlers may still exist in the dispatcher, but they are not advertised in the live tool list.

## Discovery

| Tool | Purpose |
|------|---------|
| `list_estimators` | Discover estimators by task, capability tags, text query, limit, and offset. |
| `describe_estimator` | Return detailed metadata for one estimator, including parameters, tags, and docstring excerpt. |
| `get_available_tags` | Return sktime tag metadata for capability-aware estimator filtering. |

## Instantiation and Composition

| Tool | Purpose |
|------|---------|
| `instantiate_estimator` | Create a single estimator handle from an estimator name and optional parameters. |
| `instantiate_pipeline` | Create a composed estimator handle from ordered components and optional per-component parameters. |
| `validate_pipeline` | Check whether a proposed component sequence is valid before instantiation. |
| `list_handles` | List active estimator handles held by the server. |
| `release_handle` | Release an estimator handle from memory. |

## Execution

| Tool | Purpose |
|------|---------|
| `fit_predict` | Fit an estimator on a demo dataset or loaded data handle, then return forecasts. |
| `fit_predict_async` | Start a background fit-predict job on a demo dataset and return a job id. |
| `evaluate_estimator` | Run expanding-window cross-validation for a forecasting estimator on a demo dataset. |

## Data

| Tool | Purpose |
|------|---------|
| `list_available_data` | List built-in demo datasets and active user-loaded data handles. |
| `load_data_source` | Load pandas, file, SQL, or URL data into a server-side data handle. |
| `load_data_source_async` | Start a background data-loading job and return a job id. |
| `format_time_series` | Create a formatted data handle with inferred frequency, duplicate handling, and missing-value filling. |
| `release_data_handle` | Release a data handle from memory. |

## Persistence and Export

| Tool | Purpose |
|------|---------|
| `export_code` | Generate Python code for an estimator or pipeline handle. |
| `save_model` | Persist a fitted estimator through sktime's MLflow integration. |
| `load_model` | Load a saved sktime model and register it as a fitted handle. |

## Background Jobs

| Tool | Purpose |
|------|---------|
| `check_job_status` | Inspect status, progress, result, and errors for one background job. |
| `list_jobs` | List background jobs, optionally filtered by status. |
| `cancel_job` | Cancel a pending/running job, or remove a completed job record with `delete=true`. |

## Common Workflows

For complete examples, see:

- [Usage Examples](usage-examples.md) for end-to-end assistant workflows.
- [Data Source Support](data-sources.md) for data loading configuration.
- [Background Jobs](background-jobs.md) for asynchronous execution.
