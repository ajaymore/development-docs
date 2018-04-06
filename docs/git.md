# Git status
git status
# To checkout already committed file and remove current changes
git checkout -- yarn.lock
# check current branch
git branch
# switch to branch
git checkout branch_name

$ git checkout -b myFeature dev
Creates MyFeature branch off dev. Do your work and then

$ git commit -am "Your message"
Now merge your changes to dev without a fast-forward

$ git checkout dev
$ git merge --no-ff myFeature
edit

Now push changes to the server

$ git push origin dev
$ git push origin myFeature
And you'll see it how you want it.