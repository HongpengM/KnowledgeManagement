# remove files exists before gitignore 

Stack Overflow Answer

https://stackoverflow.com/questions/7527982/applying-gitignore-to-committed-files/7532131#7532131

After editing `.gitignore` to match the ignored files, you can do `git ls-files -ci --exclude-standard` to see the files that are included in the exclude lists; you can then do `git ls-files -ci --exclude-standard -z | xargs -0 git rm --cached` to remove them from the repository (without deleting them from disk).

**Edit**: You can also add this as an alias in your .gitconfig file so you can run it anytime you like. Just add the following line under the [alias] section:

```
apply-gitignore = !git ls-files -ci --exclude-standard -z | xargs -0 git rm --cached

```

(The `-r` flag in `xargs` prevents `git rm` from running on an empty result and printing out its usage message, but may only be supported by GNU findutils. Other versions of `xargs` may or may not have a similar option.)

Now you can just type `git apply-gitignore` in your repo, and it'll do the work for you!