# Version manifest

This repository holds a single file, [`version.json`](version.json), recording
the current and minimum-supported version of an internal YunoJuno browser tool.
Installed copies read it to tell whether they are up to date.

It is public **only** because the tool itself lives in a private repository, and
an installed copy has no credentials with which to check a private one. Nothing
here describes what the tool does.

There is no application code in this repository.

## The file

```json
{
  "version": "2.61",
  "released": "2026-08-19",
  "minSupported": "2.50",
  "notice": ""
}
```

| Field | Meaning |
|---|---|
| `version` | The current release. An install on anything lower is out of date. |
| `released` | ISO date of that release. Informational. |
| `minSupported` | The oldest release still considered usable. An install below this gets a prominent warning rather than a gentle one. |
| `notice` | Optional one-line message shown alongside the update prompt. Leave empty unless there is something people must know before updating. |

Versions are compared **numerically, part by part** — `2.9` is older than
`2.57`, not newer.

## Updating it

On each release, set `version` and `released` to the new release. Move
`minSupported` only when an older version genuinely stops working — raising it
puts a prominent warning in front of everyone below the new floor.

> **This file is public.** Keep it to version numbers. No client names, no
> feature descriptions, no internal URLs, no screenshots — including in `notice`
> and in commit messages.
