First of all - useful links:

- [opengroup.org - find](https://link.org/)
- [man7.org - find](https://link.org/)
- [redhat.com - 10 ways to use the Linux 'find'](https://www.redhat.com/sysadmin/linux-find-command)
- `man find`{{exec}}

<details><summary>Lesson info and tips</summary>
<pre>
  $ find / -name "foo.txt"
  $ find / -iname "*foo*txt"
  $ find . -name "*txt" -exec grep -Hi sometext {} \;
  $ find ~ -type f -empty
  $ find /var/log -iname "*~" -o -iname "*log*" -mtime +30
  $ find . -type f -perm 0777 -print
  $ find / -perm /u=r
  $ find . -type f -name "*.tmp" -exec rm -f {} \;
  $ find / -cmin -60
  $ find / -type f -name *.mp3 -size +10M -size -20M -exec rm {} \;
<br>
The find -exec command will take the following format:
  find [path] [arguments] -exec [command] [placeholder] [delimiter]
<br>
  '{}' is called a placeholder. This placeholder will hold the result found by find<br>
  Delimeter may be \; or +<br>
  \; will execute command on each result
  +  all results will be passed to command in one line
</pre>
</details>
<br>

Task list:
- Create 50 files with names like fileNN.txt 
- Delete all files with find command with -exec argument

<details><summary>Hints for the task</summary>
<pre>
<strong>Task 1:</strong>
  $ touch file{1..50}.txt
<br>
<strong>Task 2:</strong>
  $ find . -iname "file*.txt" -exec rm {} \;
</pre>
</details>
<br>
<details><summary>If You have read all and understood</summary>
<pre>
`touch IReadAllAndUndnderstood`{{exec}}
</pre>
