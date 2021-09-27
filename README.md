# Git troubleshooting

Git troubleshooting that we use in practice.


## git clone


It’s good for `git clone` to be bulletproof, and to track errors to the root cause, because clone errors tend to crop up later on and in worse ways, such as during production pipelines.

* What git client and version number are you using? For example, are you using GitHub Desktop, or emacs magit, or git via the command line?

* How much free disk space do you have? When you try to create a local file that’s of similar size to the repo size, such as via the command `dd` or `truncate`, what happens?

* How are you connecting to the Internet? For example, do you use any proxies or throttling, such as a VPN or router or hotspot? If so, could they be cutting out after X bytes or X time etc.?

* When you clone via SSH and/or via HTTPS, what error messages are you getting? Do both SSH and HTTPS fail? If so, so they both fail in the same way, such as the same percent complete?

* When you try to use SSH, are there any issues with your SSH key in your GitHub account? If you are adding an SSH key to your GitHub account, what happens?

* When you try to create a repository in the same organization, using GitHub via your browser (not GitHub desktop, not emacs magit, not command line, etc.), what happens?


## Example helpers


Example: create a 10g file via command `truncate`:

```sh
truncate -s 10g /path/to file
```

Example: create a 10g file via command `dd`:

```sh
dd if=/dev/zero of=/path/to/file bs=1048576 count=10240
```
