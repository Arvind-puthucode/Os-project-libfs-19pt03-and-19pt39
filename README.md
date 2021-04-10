# Os-project-libfs-19pt03-and-19pt39

Video explanation link:
https://drive.google.com/file/d/1GfgZGbXPhvAKfDMzFN334vBpJPOHbzhZ/view?usp=sharing


Objective:
Building a user level lbrary libFS that implements, a good portion of file system.
This file system links to an application through which we can access files and directories.
This library will inturn link with a layer that implements a disk.

Implementation Details:
We will make a file system API that has 3 parts. Two of them are generic file system calls that deals with file access and a set of calls that deals with directories.

File Access APIs
int File_Create(char *file)
This creates a new file of the name pointed to by file. If the file already exists, you should return -1 and set
osErrno to E_CREATE.
int File_Open(char *file)
This opens a file and return an integer file descriptor, which can be used to read and write from and to the file.
int File_Read(int fd, void *buffer, int size)
This should read size bytes from the file referenced by the file descriptor fd.
The data should be read into the buffer pointed to by buffer.
int File_Write(int fd, void *buffer, int size)
This should write size bytes from buffer and write them into the file referenced by fd.
int File_Seek(int fd, int offset)
This should update the current location of the file pointer.
int File_Close(int fd)
This closes the file referred to by file descriptor fd.
int File_Unlink(char *file)
This should delete the file referenced by file, including removing its name from the directory it is in.
Directory APIs
int Dir_Create(char *path)
This creates a new directory as named by path.
int Dir_Size(char *path)
This returns the number of bytes in the directory refereed to by path.
int Dir_Read(char *path, void *buffer, int size)
This can be used to read the contents of a directory refered by path.
int Dir_Unlink(char *path)
This removes a directory referred to by path, freeing up its inode and data blocks, and removing its entry from the parent directory.
