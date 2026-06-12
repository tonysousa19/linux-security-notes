# Linux Terminal

The terminal is a command-line interface used to interact with the system through commands.

## Basic Navigation

### pwd: Shows the current directory

```bash
pwd
```

Example output:

```bash
/home/tony
```

---

### ls: Lists files and folders

```bash
ls
```

A useful option is:

```bash
ls -la
```

It lists all files and folders, including hidden files.

----

### cd: Changes directory
```bash
cd Documents
```

go back:
```bash
cd ..
```

----

## Folders and archives management

### touch: creates an empty file
```bash
touch notes.txt
```

----

### cat: Displays file contents
```bash
cat notes.txt
```
It shows the content of a file in the terminal, it is useful for quickly reading:
- configuration files
- logs
- text files

Example: 
```bash
cat /etc/passwd
```

----
### cp: Copies files and directories
Copy a file
```bash
cp notes.txt backup.txt
```

Copy to another directory:
```bash
cp notes.txt Documents/
```

Copy a folder:
```bash
cp -r folder backup/
```

The `-r` option copies directories recursively.

----

### mv: Moves or renames files

Move a file:
```bash
mv notes.txt Documents/
```

Rename a file:
```bash
mv oldname.txt newname.txt
```

----

### rm: Removes files and directories

Remove a file:

```bash
rm notes.txt
```

Remove a directory:

```bash
rm -r folder
```

Observation: removed files are not moved to the trash.

----

## File Links
Linux supports two type of links:

- Hard links
- Symbolic (soft) links

----

### Hard link

Creates another name for the same files
```bash
ln file.txt hardlink.txt
```
Both files point to the same inode, a data structure used by Linux file systems to store metadata about a file or directory

If the original file is deleted, the hard link still works.
----


### Symbolic link (Soft Link)
Creates a shortcut that points to another file.

```bash
ln -s file.txt softlink.txt
```

A symbolic link stores the path to the original file. If the original file is deleted, the link becomes broken
