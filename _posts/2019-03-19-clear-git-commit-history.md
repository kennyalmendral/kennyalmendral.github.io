---
layout: post
title: Clear Commit History of a Git Repository
---

Here's how you can clear a cluttered commit history in a Git repository.

Open your bash terminal, clone the repository and inside that repository, run the following commands:

```
rm -rf .git
	
git init
git add .
git commit -m "Initial commit"

git remote add origin <repository_url>
git push -u --force origin master
```