# Bash Commands

When you run another script in bash like below

```bash
./myscript arg1 arg2
```

This script run in its shell and exported variables inside this script will not propagate to calling script
In order to solve this problem you can run like this

```shell script
source ./myscript arg1 arg2

# OR
. ./myscript arg1 arg2
```

But above is valid for Bash shell. sh shell wont allow arg1 and arg2 to pass to script. To solve
this problem you can do like below

```bash
set -- set arg1 arg2;. ./myscript arg1 arg2
```

## Existence & Matching

```bash
if [ ! -f ~/scripts/abc.jar ]; then
     echo -e "[INFO] File not found!"
 else
     echo -e "[INFO] File found"
fi


if [[ $var1 == "secondary" ]]; then
    echo -e "[INFO] Variable matches"
fi


if [ -z "$environment" ]; then
	echo -e "[INFO] environment variable is NOT set"
fi


if [[ -z $1 ]]; then
    echo "[INFO] 1st argument does not exist"
fi
```

## Check Value is in Array

```
environments=("develop" "staging" "production")

if ! [[ " ${environments[@]} " =~ " $env " ]]; then echo "env should be one of :${environments[@]}"; help; fi
```


## Array Iteration

```shell script
arr=(action confluence transformer)
pwd=$(pwd)

for item in "${arr[@]}"
do
	echo "${pwd}/${item}"
done
```


## Getting Command Line values

```
for ARGUMENT in "$@"
do
    KEY=$(echo $ARGUMENT | cut -f1 -d=)
    VALUE=$(echo $ARGUMENT | cut -f2 -d=)

    case "$KEY" in
            -arn| --role-arn) arn=${VALUE} ;;
            -r| --region) region=${VALUE} ;;
            -h | --help | ?) help ;;
            *)
    esac
done
```


## Number of argument

```
if ! [[ ("$#" -eq 0 || "$#" -eq 4) ]]; then
    help
    exit 1
fi
```


## Read Y/n or y/N

```bash
read -p "Are you sure ... ? " -n 1 -r
echo    # (optional) move to a new line
if [[ $REPLY =~ ^[Yy]$ ]]
then
    DO SOMETHING
fi
```



## Select from dropdown

```shell script
select_option() {
    ESC=$( printf "\033")
    cursor_blink_on()  { printf "$ESC[?25h"; }
    cursor_blink_off() { printf "$ESC[?25l"; }
    cursor_to()        { printf "$ESC[$1;${2:-1}H"; }
    print_option()     { printf "   $1 "; }
    print_selected()   { printf "  $ESC[7m $1 $ESC[27m"; }
    get_cursor_row()   { IFS=';' read -sdR -p $'\E[6n' ROW COL; echo ${ROW#*[}; }
    key_input()        { read -s -n3 key 2>/dev/null >&2
                         if [[ $key = $ESC[A ]]; then echo up;    fi
                         if [[ $key = $ESC[B ]]; then echo down;  fi
                         if [[ $key = ""     ]]; then echo enter; fi; }

    for opt; do printf "\n"; done

    local lastrow=`get_cursor_row`
    local startrow=$(($lastrow - $#))

    trap "cursor_blink_on; stty echo; printf '\n'; exit" 2
    cursor_blink_off

    local selected=0
    while true; do
        local idx=0
        for opt; do
            cursor_to $(($startrow + $idx))
            if [ $idx -eq $selected ]; then
                print_selected "$opt"
            else
                print_option "$opt"
            fi
            ((idx++))
        done

        case `key_input` in
            enter) break;;
            up)    ((selected--));
                   if [ $selected -lt 0 ]; then selected=$(($# - 1)); fi;;
            down)  ((selected++));
                   if [ $selected -ge $# ]; then selected=0; fi;;
        esac
    done

    cursor_to $lastrow
    printf "\n"
    cursor_blink_on
    return $selected
}

## if $stage is not set

stages=("develop" "staging" "production")

if [ -z "$stage" ] ; then
   echo -e ""
   echo -e "[INFO] Select STAGE using up/down keys and enter:"
   select_option "${stages[@]}"
   choice=$?
   stage=${stages[$choice]}
fi
```

## Personal Bash Commands

```bash
remindme                    # Remind if command is completed. To be submitted CMD && remindme
passwordGenerator           # Password generator 
mysplit 1000 query.sql      # Split query.sql by lines 1000 and will generator query_1.sql, query_2.sql etc
```


## Bash Colors

```bash
echo -e "\\033[0mCOLOR_NC (No color)"
echo -e "\\033[1;37mCOLOR_WHITE\\t\\033[0;30mCOLOR_BLACK"
echo -e "\\033[0;34mCOLOR_BLUE\\t\\033[1;34mCOLOR_LIGHT_BLUE"
echo -e "\\033[0;32mCOLOR_GREEN\\t\\033[1;32mCOLOR_LIGHT_GREEN"
echo -e "\\033[0;36mCOLOR_CYAN\\t\\033[1;36mCOLOR_LIGHT_CYAN"
echo -e "\\033[0;31mCOLOR_RED\\t\\033[1;31mCOLOR_LIGHT_RED"
echo -e "\\033[0;35mCOLOR_PURPLE\\t\\033[1;35mCOLOR_LIGHT_PURPLE"
echo -e "\\033[0;33mCOLOR_YELLOW\\t\\033[1;33mCOLOR_LIGHT_YELLOW"
echo -e "\\033[1;30mCOLOR_GRAY\\t\\033[0;37mCOLOR_LIGHT_GRAY"
```

## Crontab

```shell script
# Create crontab file

touch ~/.crontab

# Add content to this file e.g.
*/10 7-17 * * 1-5 /Users/pujan/Shell/plex_kill.sh

# Crontab apply
crontab ~/.crontab
```
