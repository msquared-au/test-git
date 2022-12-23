# test-git

Just exploring git features

## Process summary for signing commits

1.  Make sure your details are set from github:
    ```
    git config --global user.email 'your.git@email.address'
    git config --global user.name 'your name'
    ```

2.  Tell Git to use ssh when signing (second line contains id_rsa.pub):
    ```
    git config --global gpg.format ssh
    git config --global user.signingKey 'ssh-ed25519 AAAAC3(...)qiXsb user@host'
    ```

3.  If you want all commits signed by default (so you don't need to
    use '-S' to sign):
    ```
    git config --global commit.gpgsign true
    git config --global tag.gpgsign true
    ```

If you want to use ssh for `git push`, change the URL of your origin
repo from https to ssh.  For example: to change
from `https://github.com/yourusername/reponame`
to `git@github.com:yourusername/reponame`,
check the current origin with `git remote get-url origin`
then change it
with `git remote set-url origin git@github.com/yourusername/reponame`.

### Troubleshooting

*   You can test that ssh to github is working like so:
    ```
    ssh -T git@github.com
    ```

## References

I used these pages to work this stuff out:

* https://blog.dbrgn.ch/2021/11/16/git-ssh-signatures/

