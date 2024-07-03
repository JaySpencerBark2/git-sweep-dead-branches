# git-sweep-dead-branches


Uses a git sweep alias as seen bellow to remove all remote merged in branches
This will just clean down the branches you have to edit this edit the files paths to be the ones that hold your
Projects and run this as a cron job which is its intended way but running it normally works fine

# git sweep alias

# ~/.gitconfig file, put the following:
 
[alias]
        sweep = ! git fetch -p && git for-each-ref --format '%(refname:short) %(upstream:track)' | awk '$2 == \"[gone]\" {print $1}' | xargs -r git branch -D
