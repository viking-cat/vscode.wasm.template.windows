# Wasm Template for VSCode (Windows) with Bash terminal
This template was created for myself but I figured that parts of it, mostly the bash part could be of use for other users.
* Emscripten
* Msys2
* VSCode
## Changelog
180322 - Just added the bash part as it is in the original file for safe keeping. 
## Bash Shell
I prefer to work with _Bash_ over _Command_ amd _Powershell_ but it was hard to get i working properly in VSCode, mostly because of a lack of information. It is my hope that this information will save someone else the time of looking for information on how to launch a customized shell as their terminal in VSCode. The basic trick is to configure the workspace to launch a bash script that configures and launches bash in the terminal window.

_<project>/.vscode/settings.json_ 
```json
  "terminal.integrated.shell.windows": "C:\\MinaProgram\\msys64\\usr\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": ["-c","'./.vscode/bash_path.sh'"]
```

_<project>/.vscode/bash_path.sh_
```bash
  #!/bin/bash
  # Clear screen
  clear
  # Output text
  echo 'Launching Msys2(64) Bash'
  # Store laundirectory in a variable, ex 'echo $LAUNCHDIR' to print
  export LAUNCHDIR=$(pwd)
  # 'export PATH=$PATH:/my/custom/path' to set environment variable
  export PATH=$PATH:/c/minaprogram/msys64/usr/bin
  # launch bash again with settings
  bash -i -l
```
