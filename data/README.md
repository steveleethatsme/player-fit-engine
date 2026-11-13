# Data policy

This folder is a **local workspace**. Its subfolders are git-ignored on purpose.

| Folder | Contents | Committed? |
|---|---|---|
| `raw/` | Data as downloaded from free public sources | No |
| `licensed/` | Data from paid or subscription sources | **Never** |
| `interim/` | Cleaned / joined intermediate tables | No |
| `processed/` | Model-ready features | No |

## Rules

1. **Free public sources first**, then paid data only where its license allows the intended use.
2. **Licensed third-party data** may be used only within the terms of its subscription. It is never committed, never published, and never shown in the public app unless those terms explicitly allow it.
3. Every source must be logged in [`docs/03-data-sources.md`](../docs/03-data-sources.md) with its license terms **before** it's used.
4. Scripts that fetch or build data are committed; the data itself is not. Anyone cloning the repo should be able to rebuild public-source data from the scripts.
