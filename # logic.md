# logic

git clone template

create repo

set remote url to push

Then create gh-pages branch
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initializing gh-pages branch"
git push origin gh-pages
git checkout master



generate website public folder content using hugo server

git checkout gh-pages

git ignore /resources and /assets

commit changes

 git subtree push --prefix public/ origin gh-pages