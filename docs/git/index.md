## learn git 
##### Useful commands:

* `push : git remote_url <branch>`
* `git push https://bitbucket.org/teamge/learngit master`

* `git push <remote> --tags`
* `git add <filename>`
* `git add * `
* `git commit -m "Commit message"`


##### რეპოზიტორის მისამართის დამატება
* `git remote add vobi https://bitbucket.org/vobi-io/learngit master`
* `git push vobi master `

##### სრული სია რეპოზიტორის მისამართების
`git remote -v`
   
##### კონკრეტული რეპოზიტორის მისამართის ნახვა
`git remote show vobi`

##### ახალი ბრენჩის შექმნა "feature_x" & შეცვლა
* `git checkout -b beka_dev`

#####   ბრენჩის ჩვლილება
* `git checkout master `
##### ბრენჩის წაშლა
* `git branch -d beka_dev`

##### ბრენჩის ატვირთვა
* `git push origin beka_dev`

##### განახლება ლოკალური რეპოზიტორის ახალი კომიტ ცვლილებებით
* `git pull`

##### აქტიურ (მიმდინარე) ბრენჩთან სხვა ბრენჩის დამერჯვა
* `git merge <branch>`

   
#####  დამერჯვამდე ცვლილებების ნახვა (preview)
`git diff <source_branch> <target_branch>`

##### კომიტამდე ცვლილებების ნახვა
* `git diff test.js .`


##### ტაგების დადება .
* `git tag` 
* `git tag 1.0.0 1b2e1d63ff` 
* `git tag -l 'v1.8.5* '`   ტაგის ძებნა
* `git tag -a v1.4 -m 'my version 1.4'`  ტაგის ანოტაცია
* `git show v1.4`

#####  ლოკალური ტაგების ატვირთვა სერვერზე
* `git push origin 1.0`
* `git push --tags` 

##### კონკრეტულ ტაგზე (ჭდეზე) დაბრუნება
* `git checkout -b [branchname] [tagname]`
* `git checkout -b version2 v2.0.0`

##### ლოგირების ბრძანენები 
* `git log`
* `git log -p -2`  ბოლო 2 კომიტის ნახვა ცვლილებებით
* `git log --stat`
* `git log --pretty=format:"%h - %an, %ar : %s"`
* `git log --pretty=oneline`
* `git log --pretty=format:"%h %s" --graph`
* `git log --since=2.weeks`
* `git log --autho=btomashvili`

##### ASCII გრაფი ისტორიის 
* `git log --graph --oneline --decorate --all`

##### See only which files have changed: 
* `git log --name-status`
* `git log --help`

##### Roll back file ,can replace local changes using the command
* `git checkout <filename>`
* `git checkout -f   check out all files` 
* `git reset --HARD`


##### ყველა ლოკალური კომიტის დადროვპა (drop all you local changes and commits, fetch the latest hustoru from the server and point your local master branch at it like this )
* `git reset`
* `git fetch origin` 
* `git reset --hard origin/master`

#####  გიტის გრაფიკული ინტრეფეისის (gitk) გამოძახება
* `gitk`

##### git interactive
* `git add -i`

##### გიტიდან ფაილის წაშლა
* `git rm <filename>`
* `git rm log/\* .log`

##### ფაილის გადაადგილება ან დასახელების შეცვლა
* `git mv <filename>`

##### დროებით როცა გვინდა რომ ფაილი არ დაკომიტდეს / არ აიტვირთოს.

* `git update-index --assume-unchanged <file>`
* `git update-index --no-assume-unchanged <file>`

##### მიმდიარე ბრენჩის ჩვენება რომელზეც ვდგავართ

* `git branch`

##### როცა გვინდა წინა კომიტს თავზე გადავაწეროტ ახალი კომიტი / განახლება გავაკეთოთ წინა არსებული კომიტის

* `git commit --amend`
*  `git commit --amend -am "remove files"`

##### ან ასე 
*  `git add *`
*  `git commit --amend -m "remove files"`

##### "Changes not staged for commit" და გაქმება გვინდა ამ ფაილების კომიტიდან 

* `git stash save --keep-index`
* `git checkout -f`
* `git checkout <file>`

##### ლოკალური ბრენჩის წაშლა 

* `git branch -d the_local_branch`

##### ბრენჩის წაშლა რემოუთზე
* `git push origin --delete <your_branch>`

##### რემოუთზე ბრენჩის წაშლა

* `git push origin :the_remote_branch`

##### როცა ფაილები არ გადადის unstaged ში 

* `git ls-files -m | xargs -i git update-index --assume-unchanged "{}"`

##### ბოლო კომიტების წაშლა  ~10 არის კომიტების რაოდენობა რამდენით დახიოს უკან
* `git rebase -i HEAD~10`

##### სინქრონზიაცია რემოუტის ლოკალზე
* `git remote prune origin`

##### კონკრეტული კომიტის გაუქმება
`git revert --strategy resolve <commit>`

##### კოკრეტული კომიტიდან ბრენჩის გაკეთება
``` git branch branchname <sha1-of-commit> ```
