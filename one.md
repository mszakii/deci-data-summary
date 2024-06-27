# DECI LEVEL 3 DATA TRACK SUMMARY 2024

By <span style="color: #009688; font-weight: bold">Mohamed Elsayed</span> © 2024

<h2 style="color: #3f51b5">1️⃣ Basic SQL</h2>

- `ERD` Entity Relation Ship Diagram. Is the relation between spreadsheets.

- `NoSQL` = not only SQL

### Why Businesses Like Databases

- Data integrity is ensured
- Data can be accessed quickly
- Data is easily shared

### Statments

- `CREAT TABLE` Creates new table in DB
- `DROP TABLE` Removes a table in DB
- `SELECT` Allows you to read the data and display it. **Most Common!**. This is called a qurey
- `LIMIT 10` return first 10 rows

<h2 style="color: #3f51b5">2️⃣ SQL Conditions</h2>

- `ORDER BY`
  - between `FROM` and `LIMIT`
  - It's from a to z or from earliest to latest

```sql
SELECT *
FROM demo.orders
ORDER BY occured_at
LIMIT 1000
```

You can add `DESC` to reverse order

```sql
SELECT *
FROM demo.orders
ORDER BY occured_at DESC
LIMIT 1000
```

- `WHERE` for filtering data numeric and strings

```sql
SELECT *
FROM demo.orders
WHERE accound_id = 4251
ORDER BY occured_at DESC
LIMIT 1000
```

- `LIKE` it will find `https://www.`**`google`**`.com` as an example

```sql
SELECT *
FROM demo.web_events_full
WHERE referrer_url LIKE '%google%'
```

- `NOT` used to get the opposite if we used it in the last example it will returns all sites except google

```sql
SELECT sales_rep_id, name
FROM demo.accounts
WHERE sales_rep_id NOT IN(321500, 321570)
ORDER BY sales_rep_id
```

- `AND` and `BETWEEN`

```sql
WHERE column >= 6 AND column <= 10
```

Is the same as

```sql
WHERE column BETWEEN 6 AND 10
```

<h2 style="color: #3f51b5">3️⃣ Version Control</h2>

- `Git`, `Subversion`, `Mercurial` are examples of **VCS**
- `Git` is a distributed version control system

- There are two main models:

  - `the centralized model` all users connect to a central, master repository
  - `the distributed model` each user has the entire repository on their computer

- `Working Directory` ==> `Staging Index` ==> `Repo`

<h2 style="color: #3f51b5">4️⃣ Create A GIT Repo</h2>

```bash
$ git init # create new brand new repos
$ git clone # clone or copy an existing repo
$ git status # check the status of a repo
```

If the directory is empty

```bash
$ git status
  > On branch master
  > Initial commit
  > nothing to commit (create/copy files and use "git add" to track)
```

```bash
$ git log
  > fatal: your current branch 'master' does not have any commits yet
```

- to scroll down, press
  - `j` or `↓` to move down one line at a time
  - `d` to move by half the page screen
  - `f` to move by a whole page screen
- to scroll up, press
  - `k` or `↑` to move up one line at a time
  - `u` to move by half the page screen
  - `b` to move by a whole page screen
  - press `q` to quit out of the log (returns to the regular command prompt)

```bash
$ git log
  > commit 40e2199a4b2fe59e5690311d15e9d7df4da82d6e
  > Author: Richard Kalehoff <richardkalehoff@gmail.com>
  > Date:   Fri Dec 2 12:37:39 2016 -0500

    Add starter files
```

```bash
$ git log --oneline
  > a2ec9ea Create CODEOWNERS
  > 00dca03 Fix the JIRA ticket title
  > 566ab7f Update manual.yml
  > 57e6291 Update manual.yml
  > 7279ecb Update .gitignore
```

```bash
$ git log --stat # statistics flag

  > Author: Richard Kalehoff <richardkalehoff@gmail.com>
  > Date:   Fri Dec 2 12:36:04 2016 -0500

    Initial commit

  > README.md | 27 +++++++++++++++++++++++++++
  > 1 file changed, 27 insertions(+)
```

- The git log command has a flag that can be used to display the actual changes made to a file. The flag is `--patch` which can be shortened to just `-p`:

```bash
$ git log -p
```

![OutPut Image From Udacity](https://video.udacity-data.com/topher/2017/February/58a37ea6_ud123-l3-git-log-p/ud123-l3-git-log-p.png)

- `git log -p --stat` It displays both with the stats info above the patch info

- `git log -p -w` It will not display whitespace changes

- `git log -p fdf5493` == `$ git show fdf5493`
