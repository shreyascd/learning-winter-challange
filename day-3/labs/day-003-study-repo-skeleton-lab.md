# Lab - Day 003: Create the study-repo folder skeleton and push it

## Steps
1. Make the folder tree in one command:
```bash
mkdir -p ~/study-repo/day-3/{notes,cheatsheets,flashcards,labs}
```
2. Add a `.gitkeep` to each empty folder so git tracks it:
```bash
touch ~/study-repo/day-3/{notes,cheatsheets,flashcards,labs}/.gitkeep
```
3. Check the structure:
```bash
tree -L 3 ~/study-repo
```
4. Initialise git, commit and push (one commit per step, as in the roadmap).

## Archive and verify practice
```bash
tar -czvf ~/day-3.tar.gz -C ~ study-repo
tar -tzf ~/day-3.tar.gz
sha256sum ~/day-3.tar.gz
file ~/day-3.tar.gz
```

## My output
```
(paste real output here)
```

## Screenshots to add
- [ ] `tree` output of study-repo
- [ ] `tar -tzf` listing
- [ ] `sha256sum` output

## Notes
- Which file system is my home folder on? (`df -T ~`)
- Does `file` agree with the extension on my downloads?
