# [Demo Command]

git co -b 1-implement-main-feature
git co -b 2-implement-support-feature

## step 1 default process

git co 1-implement-main-feature

test.txt > main-feature-1

git commit -m "feat: implement main feature"
git push origin 1-implement-main-feature

create PR and merge to master from feature
create PR and merge to release from master
create PR and merge to production from release

## step 2 hotfix process

git co production
git pull

git co -b 3-hotfix-main-feature

test.txt > main-feature-1.5

git commit -m "fix: update main feature"
git push origin 3-hotfix-main-feature

create PR and merge to release from 3-hotfix-main-feature

test.txt > main-feature-1.8

git commit -m "fix: resolve issue"
git push origin 3-hotfix-main-feature

create PR and merge to release from 3-hotfix-main-feature
create PR and merge to production from release

## step 3 update hotfix and merge process

create PR and merge to master from production

git co master
git pull
git co 2-implement-support-feature
git merge master

test.txt > support-feature-1

git commit -m "feat: implement support feature"
git push origin 2-implement-support-feature

create PR and merge to master from feature
create PR and merge to release from master
create PR and merge to production from release
