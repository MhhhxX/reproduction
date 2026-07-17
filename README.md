# minimal-reproduction-template

First, read the [Renovate minimal reproduction instructions](https://github.com/renovatebot/renovate/blob/main/docs/development/minimal-reproductions.md).

Then replace the current `h1` with the Renovate Issue/Discussion number.

## Current behavior

No Pr is created in this workspace crate with two crates although renovate detects the needed updates correctly
and shows it on the developer dashboard:


```
Detected Dependencies
cargo

    crates/crate1/Cargo.toml

        log 0.4.29

        → [Updates:

        0.4.29

        ]

    crates/crate2/Cargo.toml

        bytemuck 1.25.0

        → [Updates:

        1.25.0

        ]
```

excerpts from the log file:

```
WARN: Detected empty commit - aborting git push (branch="renovate/bytemuck-1.x-lockfile")
{
  "commitRes": {
    "author": null,
    "branch": "",
    "commit": "",
    "root": false,
    "summary": {
      "changes": 0,
      "insertions": 0,
      "deletions": 0
    }
  }
}

DEBUG: repository problems
{
  "repoProblems": [
    "⚠️ WARN: Detected empty commit - aborting git push"
  ]
}
```

## Expected behavior

A Pr should be created by renovate which updates 
both dependencies (log and bytemuck) in `Cargo.lock` to the newest version.

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
