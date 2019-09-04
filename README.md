Lambda shell - a lambda-backed Linux shell
------------------------------------------

Execute commands hosted and executed by AWS Lambda
via an interactive shell / terminal.

![VideoGif](https://raw.githubusercontent.com/iopipe/lambda-shell/master/contrib/demo.gif)

Requirements:
 - Serverless (https://serverless.com/)
 - Amazon AWS account

# Installation

1. Install npm modules: `npm install`
2. Deploy to AWS with `sls deploy`.

# Usage

Execute `lambda-shell`:

```
$ ./lambda-shell
```

This will create a REPL (shell) where commands will be
sent to Lambda and returned to your console.

## Example

```
$ ./lambda-shell
$ uname -a
Linux ip-10-11-194-19 4.1.19-24.31.amzn1.x86_64 #1 SMP Tue Mar 15 23:41:50 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux
```

# Exiting the shell

Exit the shell using Ctrl-C.

# Limitations

* No TTY is allocated. You cannot use `vim`, `emacs`, or even `ex`. Try `ed` or `sed` instead.
* The working path ($PWD) is never modified. (`cd` is not very effective...)A
* No guarantee that commands will land onto the same machine/container. (FEATURE!)
* Writes are ephemeral except to /tmp. (FEATURE!)

# License

Apache-2.0

Copyright 2016  IOpipe, Inc.
Ported to Serverless 2019, Paul Ridgway