## compression schemes

In Linux, some of the most commonly used compression schemes are:

**gzip**: one of the most popular compression formats in Linux. It uses a **lossless** compression, making it a good choice for _compressing text-based files_ such as log files, source code, and documents. The compressed files are usually saved with a `.gz` extension.
```bash
gzip -d file.gz
```

**bzip2**: uses a **lossless** compression. It is known for its high compression ratio, making it a good choice for compressing large files such as disk images, backups, and software packages. The compressed files are usually saved with a `.bz2` extension.
```bash
bzip2 -d file.bz2
```

**tar**: tar is not a compression format in itself, but it is often used in combination with other compression formats, such as **gzip** and **bzip2**, to _archive multiple files into a single compressed file_. The `tar` command is used to create and extract tar archives, and the compressed files are usually saved with a `.tar.gz` or `.tar.bz2` extension, depending on the compression format used.
```bash
tar -xvf file.tar
```

**xz**:relatively new compression format that uses the **LZMA2** algorithm to achieve a high compression ratio. It is becoming increasingly popular in Linux for compressing large files such as software packages, disk images, and backups. The compressed files are usually saved with a `.xz` extension.

**zip**: a widely used compression format that is also supported in Linux. It is used primarily on Microsoft Windows and MacOS systems, but it is also supported in Linux. The compressed files are usually saved with a `.zip` extension. The zip and unzip commands are used to compress and decompress files in this format.
```bash
unzip file.zip
```
