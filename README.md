# Git cloning folders (without the entire repo)
## Steps
### Clone repo without the contents
`git clone --filter=blob:none --no-checkout git@github.com:ishan1608/CloningFolders.git`
### Change directory
`cd CloningFolders`
### Initialize sparse checkout
`git sparse-checkout init --cone`
### Add original folder to sparse checkout
Command: `git sparse-checkout set <original-folder-path>`

Example: `git sparse-checkout set base`
### Checkout
`git checkout`
### Duplicate folder
Command: `cp -r <original-folder-path> <new-folder-path>`

Example: `cp -r base clone2`
### Add new folder to sparse checkout
Command: `git sparse-checkout set <original-folder-path> <new-folder-path>`

Example: `git sparse-checkout set base clone2`
### Add new folder to git
Command: `git add <new-folder-path>`

Example: `git add clone2`
### Commit the new folder
Command: `git commit -m "Duplicate folder <original-folder-path> to <new-folder-path>"`

Example: `git commit -m "Duplicate folder base to clone2"`
### Push the changes
`git push`
