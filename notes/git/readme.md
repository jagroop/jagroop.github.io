Git Snippets

Some usefull Git Snippets

Clear Git History
-----------------

    git checkout --orphan latest_branch # Checkout
    git add -A # Add all the files
    git commit -am "first commit" # Commit the changes
    git branch -D master # Delete the branch
    git branch -m master # Rename the current branch to master
    git push -f origin master # Finally, force update your repository
