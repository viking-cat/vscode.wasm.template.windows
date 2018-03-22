# vscode.wasm.template.windows
Template project for Wasm projects in VSCode for Windows with working bash shell.

Changelog:
180322 - Just added the bash part as it is in the original file for safe keeping.

<project>/.vscode/settings.json
```json
  "terminal.integrated.shell.windows": "C:\\MinaProgram\\msys64\\usr\\bin\\bash.exe",
  "terminal.integrated.shellArgs.windows": ["-c","'./.vscode/bash_path.sh'"]
```

<project>/.vscode/bash_path.sh
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
