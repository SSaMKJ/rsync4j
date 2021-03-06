On first execution, these binaries will get placed in the following directory
(on a per user basis):
```
%USERPROFILE%\rsync4j
```

Below that directory there are `home/%USERNAME%/.ssh` and `bin`.

### SSH keys
You can place your ssh key pairs in the following directory:

```
%USERPROFILE%\rsync4j\home\%USERNAME%\.ssh
```

### Binaries (32-bit)
*rsync4j* uses the `rsync.exe` and `ssh.exe` executables and their dependencies
from the 32-bit version of [cywgin](https://cygwin.com/).

The dependencies, as of 2018-02-25, are as follows:

* cygcom_err-2.dll
* cygcrypto-1.0.0.dll
* cyggcc_s-1.dll
* cyggssapi_krb5-2.dll
* cygiconv-2.dll
* cygintl-8.dll
* cygk5crypto-3.dll
* cygkrb5-3.dll
* cygkrb5support-0.dll
* cygpopt-0.dll
* cygssp-0.dll
* cygwin1.dll
* cygz.dll

You can easily determine the dependencies by running the executables. Windows
will automatically pop up a dialog mentioning any DLLs that are missing. Place
any missing DLLs in the following directory:

```
rsync4j-windows-x86/src/main/resources/com/github/fracpete/rsync4j/windows-x86
```

And list the DLLs in the following text file:

```
rsync4j-windows-x86/src/main/resources/com/github/fracpete/rsync4j/windows-x86/libraries.txt
```


### Binaries (64-bit)
*rsync4j* uses the `rsync.exe` and `ssh.exe` executables and their dependencies
from the 64-bit version of [cywgin](https://cygwin.com/).

The dependencies, as of 2018-02-25, are as follows:

* cygcom_err-2.dll
* cygcrypto-1.0.0.dll
* cyggcc_s-seh-1.dll
* cyggssapi_krb5-2.dll
* cygiconv-2.dll
* cygintl-8.dll
* cygk5crypto-3.dll
* cygkrb5-3.dll
* cygkrb5support-0.dll
* cygssp-0.dll
* cygwin1.dll
* cygz.dll

You can easily determine the dependencies by running the executables. Windows
will automatically pop up a dialog mentioning any DLLs that are missing. Place
any missing DLLs in the following directory:

```
rsync4j-windows-x86_64/src/main/resources/com/github/fracpete/rsync4j/windows-x86_64
```

And list the DLLs in the following text file:

```
rsync4j-windows-x86_64/src/main/resources/com/github/fracpete/rsync4j/windows-x86_64/libraries.txt
```

### Paths
Since cygwin is being used, local paths get converted to cywgin notation.

For example:
```
C:\some\path\blah.txt
```
Will get automatically get converted to:
```
/cygdrive/c/some/path/blah.txt
```

### Custom location

It is possible to use another location than `%USERPROFILE%\rsync4j`. You only
have to set up the `RSYNC4J_HOME` environment variable to point to the top-level
directory (doesn't have to exist) where you want to house the binaries and keys. 
