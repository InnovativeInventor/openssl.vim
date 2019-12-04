
## openssl.vim
This originated from a mirror of
http://www.vim.org/scripts/script.php?script_id=2012, but now has some
modifications (https://github.com/dperelman/openssl.vim), mainly ensuring that
no data leaks to backup.

```
NOTE: I have not audited this code, and I do not provide any assurances that
openssl was properly used. I have not used this plugin. Use at your own peril. If there are any
implementation mistakes, please let me know by opening up an issue.
```

## Edit OpenSSL encrypted files and turn Vim into a Password Safe!

This plugin enables reading and writing of files encrypted using OpenSSL.
The file must have the extension of one of the ciphers used by OpenSSL. For
example:

   .des3 .aes .bf .bfa .idea .cast .rc2 .rc4 .rc5

This will turn off the swap file and .viminfo log. The `openssl` command
line tool must be in the path.

## Install

Put this in your plugin directory and Vim will automatically load it:

   ~/.vim/plugin/openssl.vim

You can start by editing an empty unencrypted file. Give it one of the
extensions above. When you write the file you will be asked to give it a new
password.

## Simple Vim Password Safe

If you edit any file named '.auth.aes' or '.auth.bfa' (that's the full name,
not just the extension) then this plugin will add folding features and an
automatic quit timeout.

Vim will quit automatically after 5 minutes of no typing activity (unless
the file has been changed).

This plugin will fold on wiki-style headlines in the following format:

    == This is a headline ==

Any notes under the headline will be inside the fold until the next headline
is reached. The SPACE key will toggle a fold open and closed. The q key will
quit Vim. Create the following example file named ~/.auth.aes:

    == Colo server ==

    username: maryjane password: esydpm

    == Office server ==

    username: peter password: 4m4z1ng

Then create this bash alias:

    alias auth='view ~/.auth.aes'

Now you can view your password safe by typing 'auth'. When Vim starts all
the password information will be hidden under the headlines. To view the
password information put the cursor on the headline and press SPACE.

Thanks to Tom Purl for the des3 tip.

## License
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>
