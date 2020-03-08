# Commands
Productivity Commands List for macOS Software Development

[Brew Commands](brew.md)

[Bash Commands](bash.md)

[Curl Commands](curl.md)

[macOS Commands](mcos.md)

[NPM Commands](npm.md)


## Db

Export to Single csv file
```sql
@set maxrows 10000000;
@export on;
@export set filename="/Users/pujan/workspace_RSC/ps-smartfeed-timezone-service/manual-update/query_result.csv" CsvIncludeColumnHeader=false CsvColumnDelimiter=",";

SELECT
    * 
FROM
    TABLE
WHERE
    CONDITIONS
;

@export off;
```
[Exporting Query Results](http://confluence.dbvis.com/display/UG100/Exporting+Query+Results)


## Mis Commands

```bash
tldr split # Too Long dont read

date +'%Y-%m-%d %H:%M:%S.%s'

pgrep -i plex

aws sts assume-role --profile xyz

dig my.net
dig my.net @8.8.8.8
dig my.net +trace
dig my.net NS

history | grep -v "cd\|ls\|vi\|sudo\|cat\|open\|touch\|cp\|mv\|git\|rm\|npm\|ack\|pwd\|node\|code\|mkdir\|tsc"
```

## Convert Commands

```bash
# Horizontal combine pictures
convert +append a.png b.png out.png


# Vertical combine
convert -append name-*.jpg op.jpg
```

## Jar Commands

```bash
# Diff two jars
pkgdiff ~/EAFCore.jar workspace_ERP/LibsProj/EAFCore.jar

# Find text inside jar
zipgrep "setAuthType" some.jar
for file in *.jar; do unzip -c "$file" | grep "1.1-SNAP"; done

# Directory to jar
jar cvf hackapp.jar -C classes .

# Extract war/jar
unzip package.war -d mydir

# View jar
jar tvf MavenwebappwithTomcat-1.war
```

## Most Used Commands
```bash
split -l 5000 query.sql file_part_

history | tr -s ' ' | cut -d ' ' -f3 | sort | uniq -c | sort -n | tail | perl -lane 'print $F[1], "\t", $F[0], " ", "▄" x ($F[0] / 12)'

mvn	219     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
cp	241     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
rm	314     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
vi	360     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
git	367     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
cat	379     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
npm	566     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
ls	687     ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
ack	1405    ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
cd	1487    ▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄

ack # most used command for finding files use -i for ignore case in PWD

aws-shell # autocomplete aws command line

mac XYZ # various useful mac commands i.e. mac lock

tree -I 'node_modules|test-coverage|*.js|*.png|*.sh|*.json' # listing of files in PWD

export LC_ALL=en_US.UTF-8 && export LANG=en_US.UTF-8 # Incase utf-8 missing from macOS terminal

redis-server /usr/local/etc/redis.conf # redis

history | grep -v "cd\|ls\|vi\|sudo\|cat\|open\|touch\|cp\|mv\|git\|rm\|npm\|ack\|pwd\|node\|code\|mkdir\|tsc\|switcher\|curl\|sleep\|ssh\|find\|which\|chmod\|assume.sh\|sed\|dig\|aws\|export\|brew\|history\|make\|history\|ps"

zipgrep "Initial WSDL" some.jar

du -a * | sort -r -n | head -20

ngrok http 8000

test -f xxx.txt || echo "File does not exist"
```


## Personal Bash Commands

```bash
remindme                    # Remind if command is completed. To be submitted CMD && remindme
passwordGenerator           # Password generator 
mysplit 1000 query.sql      # Split query.sql by lines 1000 and will generator query_1.sql, query_2.sql etc
```

## Bash

### Colors

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
