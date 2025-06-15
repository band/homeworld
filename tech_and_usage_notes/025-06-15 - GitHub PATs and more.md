# 2025-06-15 - GitHub PATs and more  

- What a confused mess trying to figure out how to set up GitHub PATs and how to set them up for use.
- What confuses me is building a mental model of where credentials are stored, used, modified, etc.

- What I did today:  
	- apparently re-generated the "bsky-comments" PAT
	- installed `git-credential-manager`
		- this seems to have removed an existing gitPAT from `.git-credentials`
		- DONE: recover old file from TimeMachine (and put aside)
	- now I do not know where the current credential is stored  

- 2025-06-15 two tests and one observation:
	- same page name in different directories are correctly indexed when using Obsidian to specify the wiki links (Obsidian creates a link to a specific file and used standard Markdown syntax when needed (yay!))  
	- testing pages with ":", "?", "#" in names yields correct links
	- Observation: attempting to `urllib.parse.quote` filenames in links yields
		- messy looking links on file names on web pages
		- these file links still yield 404's (do not understand this yet)
		- changes to the code in more than three places
		- so, perhaps the ambiguity in reverse filename lookup from url can be tolerated?
		- or, need to figure this out in a maintainable way  
