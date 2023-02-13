You can use the file command recursively to determine the type of all files in a directory and its subdirectories.

Here's an example of how you can use this combination to determine the type of all files in the current directory and its subdirectories:

```bash
find . -type f -exec file {} +
```
This command does the following:

`find .`: starts the search from the current directory `.`

`-type f`: specifies that we only want to search for files (not directories)

`-exec file {} +`: the `-exec` option allows you to run the `file` command on each file found by `find`. The `{}` placeholder is replaced with each filename found by find. The `+` at the end specifies that the file command should be executed with as many filenames as possible, rather than once for each file.

This will produce output that looks something like this:

```bash
./file1: ASCII text
./dir1/file2: ASCII text
./dir2/file3: data
```
This tells you the type of each file in the current directory and its subdirectories. You can use the same approach to recursively search through other directories as well.

![image](https://user-images.githubusercontent.com/72671239/218415478-d51b1211-a2e2-45bd-986d-b37907d12076.png)
