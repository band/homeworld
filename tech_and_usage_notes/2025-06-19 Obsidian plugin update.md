# 2025-06-19 Obsidian plugin update

### Updating Obsidian Plugin

- test, commit, and push the new release code

- update `manifest.json` to the latest version (and tag) number

- Git update tag example:

```shell
git tag -a 1.2.0 -m "Release 1.2.0"
git push origin 1.2.0
gh release list
```

- release list shows latest release as "Draft" status
- login in to GitHub and "publish" that draft
	- TODO: is there an automated way to change status to "Publish"?

- Obsidian recognizes and displays the plugin as being updated

