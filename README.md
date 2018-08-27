# caffeine-git
A tool to help you with the caching git repositories. Clone off-line and set a remote cache path for better collaboration locally.

> The script will automatic install `Git` for you, if not don't have any.

### Set Up

```bash
$ git clone https://github.com/loouislow81/caffeine-git.git
$ cd caffeine-git
$ chmod +x caffeine-git
$ sudo cp $PWD/caffeine-git /usr/local/bin/
```

### Usage

Note: A generated special URL you can use to normally clone the cached repository off-line.

```bash
$ caffeine-git help
```

```text
caffeine-git help                      display this information
caffeine-git init <cache_path>               initialize the cache directory
caffeine-git add <repo_name>           add a cached Git repository
caffeine-git delete --force            delete the cache directory
caffeine-git rm --force <repo_name>    remove a cached Git repository
caffeine-git show <repo_name>          show all cached Git repositories
caffeine-git fetch                     update all cached Git repository
```

### Tutorial

#### Step 1

You need to create a cache directory whether is newly set up `caffeine-git` or change to a new cache path. By default, `caffeine-git` use the cache path located at `/var/cache/caffeine-git`. You can specify your own cache path with an extra option put after the `init` option. Which looks like this, `init <cache_path>`

```bash
$ sudo caffeine-git init
```

Or,

```bash
$ sudo caffeine-git init /path/to/your/new/cache/directory
```

###### Example Output

```text
---->> Git >>-------------------------------------------------------------------
Initialized empty Git repository in /var/cache/caffeine-git/
---->> Git >>-------------------------------------------------------------------
```

---

#### Step 2

Normally we giving command `git clone` to clone a repository, but in **caffeine-git** we need to add a `sudo` and a `add` option.

```bash
$ sudo caffeine-git add Caffeine https://github.com/loouislow81/caffeine-git.git
```
###### Example Output

```text
[caffeine-git] adding Caffeine to cache /var/cache/gitd
---->> Git >>-------------------------------------------------------------------
warning: no common commits
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
From https://github.com/loouislow81/caffeine-git
 * [new branch]      master     -> Caffeine/master
---->> Git >>-------------------------------------------------------------------
[caffeine-git] type: caffeine-git help
[caffeine-git] [success] you can now use the cached repository with special URL.

---->> Copy >>------------------------------------------------------------------
git clone --reference /var/cache/gitd https://github.com/loouislow81/caffeine-git.git
---->> Copy >>------------------------------------------------------------------
```

> `Copy` the generated special URL to clone the repository from cache directory.

### Just that...

---

MIT License

Copyright (c) 2018 Loouis Low

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
