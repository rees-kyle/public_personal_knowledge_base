---
id: rarn9wv3uu085cp101nbonc
title: Guide
desc: ''
updated: 1689297060477
created: 1689209064492
---

## Untrack File

To stop tracking a file, we must `remove` it **from** the `index`:

*git rm --cached file.ext*

---

## Remove File from Git History

1. git pull
2. git filter-branch --force --index-filter "git rm --cached --ignore-unmatch ./file/path/file.ext" --prune-empty --tag-name-filter cat -- --all
3. echo "file/path/file.ext" >> .gitignore
4. git push origin --force --all
5. git push origin --force --tags