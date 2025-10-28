# Git cloning folders (without the entire repo)
## Steps
### Clone repo without the contents
git clone --filter=blob:none --no-checkout git@github.com:ishan1608/CloningFolders.git
### Change directory
cd CloningFolders
### Initialize sparse checkout
git sparse-checkout init --cone
### Add original folder to sparse checkout
[//]: # (git sparse-checkout set <original-folder-path>)
git sparse-checkout set base
### Checkout
git checkout
### Duplicate folder
[//]: # (cp -r <original-folder-path> <new-folder-path>)
cp -r base clone2
### Add new folder to sparse checkout
[//]: # (git sparse-checkout set <original-folder-path> <new-folder-path>)
git sparse-checkout set base clone2
### Add new folder to git
[//]: # (git add <new-folder-path>)
git add clone2
### Commit the new folder
[//]: # (git commit -m "Duplicate folder <original-folder-path> to <new-folder-path>")
git commit -m "Duplicate folder base to clone2"
### Push the changes
git push
