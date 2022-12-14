# gw-util
Git Worktree Utilities

# Contents
1. [Setup](#setup)

1. [Commands](#commands)

    1.1. [Create a new worktree with an existing branch](#create-a-new-worktree-with-a-new-branch)

    1.2. [Create a new worktree with a new branch](#create-a-new-worktree-with-a-new-branch)

    1.3. [Remove a worktree](#remove-a-worktree)

# Setup

1. Clone the repo.

2. Create a folder where you want your worktrees to go. 

```bash
mkdir ~/worktrees
```

3. Create `GW_UTILS_TARGET_DIR` environment variable. It should point to the directory you created in step 2.

```bash
# in ~/.zshrc
export GW_UTILS_TARGET_DIR="~/worktrees"
```

4. Autoload functions when terminal starts up.

```bash
# autoload functions to be used in the shell
fpath=(
	~path/to/cloned/repo/commands
	"${fpath[@]}"
)
autoload -U $fpath[1]/*(.:t)
```

5. Restart the terminal.

# Commands
## Create a new worktree with an existing branch
1. Go to the relevant repo

```bash
cd ~/repos/my-new-project
```

2. Execute the command
```bash
gwa existing-branch-name
```

2. This will:
    * Create a new folder at `{GW_UTILS_TARGET_DIR}/my-new-project/existing-branch-name`
    * `cd` to the new directory
    * Open VSCode to the directory

## Create a new worktree with a new branch
1. Go to the relevant repo

```bash
cd ~/repos/my-new-project
```

2. Execute the command

```bash
gwa -b new-branch-name
```

3. This will:
    * Create a new folder at `{GW_UTILS_TARGET_DIR}/my-new-project/existing-branch-name`
    * `cd` to the new directory
    * Open VSCode to the directory

## Remove a worktree
1. Go to the relevant repo

```bash
cd ~/repos/my-new-project
```

2. Execute the command

```bash
gwr branch-name
```

3. This will call `git worktree remove` with the appropriate folder name.