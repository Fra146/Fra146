<img src="https://raw.githubusercontent.com/Fra146/Fra146/output/snake.svg" alt="Snake animation" />

## Useful Git, GitHub and Linux-related commands

### Delete all workflow runs from a GitHub repository (clear the history of workflow runs) ([SOURCE](https://stackoverflow.com/questions/57927115/delete-a-workflow-from-github-actions))
~~~
user=YOUR_USERNAME_HERE repo=YOUR_REPO_HERE; gh api repos/$user/$repo/actions/runs \
--paginate -q '.workflow_runs[] | select(.head_branch != "master") | "\(.id)"' | \
xargs -n1 -I % gh api repos/$user/$repo/actions/runs/% -X DELETE
~~~

### Reinstate the Microsoft extensions marketplace in VSCodium ([SOURCE](https://github.com/VSCodium/vscodium/issues/519#issuecomment-711469237))
~~~
mkdir -p ~/.config/VSCodium && cat > ~/.config/VSCodium/product.json <<EOF
{
  "nameShort": "Visual Studio Code",
  "nameLong": "Visual Studio Code",
  "extensionsGallery": {
    "serviceUrl": "https://marketplace.visualstudio.com/_apis/public/gallery",
    "cacheUrl": "https://vscode.blob.core.windows.net/gallery/index",
    "itemUrl": "https://marketplace.visualstudio.com/items"
  }
}
EOF
~~~

### Git Yolo ([SOURCE](https://github.com/atongen/yolo/blob/main/install.sh))
~~~
git config --global alias.yolo '!git add --all && git commit -m "$(curl -s https://whatthecommit.com/index.txt)" && git push then git yolo
~~~

