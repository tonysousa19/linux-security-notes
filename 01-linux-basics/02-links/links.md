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
