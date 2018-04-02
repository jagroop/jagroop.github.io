# Git show files that were changed in the last specific time

```bash
git log --pretty=format: --name-only --since="2 hours ago"
git log --pretty=format: --name-only --since="2 days ago"
git log --pretty=format: --name-only --since="2 minutes ago"
```

If some files duplicate in multiple commits, you can use pipe to filter it

```bash
git log --pretty=format: --name-only --since="2 days ago" | sort | uniq
```

Short and effective

```bash
git diff --stat @{2.days.ago}
```
