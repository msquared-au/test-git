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

## References

I used these pages to work this stuff out:

* https://blog.dbrgn.ch/2021/11/16/git-ssh-signatures/

