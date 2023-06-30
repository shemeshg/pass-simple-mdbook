# Windows specific

Because application using `gpgme` library, it is not possible to run native on windows. and `wsl2` is required.

1. install wsl (ubuntu linux)

    <https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps>

1. fix passphrase prompt

    Unlike standard `ubuntu`, the `Pinatery` in `wsl2` is set to `terminal mode` by default. therefore this step is mandatory

    <https://stackoverflow.com/questions/63440623/no-gpg-passphrase-prompt-in-visual-studio-code-on-windows-10-for-signed-git-comm>

1. Continue with [install_linux](install_linux.md).

    