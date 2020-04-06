# Random

```bash
uname -ap
ifconfig
df -ah <directory>
du -h
```

Visual branch history

```bash
git log --graph --decorate --oneline
git log --graph --full-history --all --pretty=format:"%h%x09%d%x20%s"
git log --graph --full-history --all --color \
        --pretty=format:"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%s"
```

```bash
git blame <filename>
git log <commit hash> -p
```

testing