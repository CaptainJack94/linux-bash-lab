cd $HOME\Projects\linux-bash-lab\01_defensive_scripting

@"
#!/bin/bash

TARGET_FILE=`$1

# Defensive guard clause: check for empty argument or missing file
if [ -z "`$TARGET_FILE" ] || [ ! -f "`$TARGET_FILE" ]; then
    echo "[ERROR] Target file missing or does not exist!"
    echo "Usage: `$0 <target_list_file>"
    exit 1
fi

echo "[OK] Target file verified: `$TARGET_FILE"
"@ | Out-File -Encoding utf8 batch_scan.sh