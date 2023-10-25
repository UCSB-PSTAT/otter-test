# asdf

Problem!!

```bash
@syoh ➜ /workspace $ gh auth login
? What account do you want to log into? GitHub.com
The value of the GITHUB_TOKEN environment variable is being used for authentication.
To have GitHub CLI store credentials instead, first clear the value from the environment.
```

For debugging template instantiation, use
```bash
copier copy --trust --no-cleanup devcontainer-template/ asdf
cat asdf/postGen.sh
```