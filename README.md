# Commands
Productivity Commands List for macOS Software Development

## macOS Specific

App is damaged and can't be opened. You should move it to the trash.

```sh
sudo xattr -rd com.apple.quarantine /Applications/Some.app
```

Launch Boot Utility OR Reinstall MAC etc

```sh
CMD + R > Press POWER Buttun
```

When BOOTing you see cross sign -> press CMD+R+ POWER button > Repair disk will solve problem


### Enable at command

```sh
launchctl load -w /System/Library/LaunchDaemons/com.apple.atrun.plist
```

killall -KILL SystemUIServer

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
![Exporting Query Results](http://confluence.dbvis.com/display/UG100/Exporting+Query+Results)


## Mis Commands

```sh
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

```sh
# Horizontal combine pictures
convert +append a.png b.png out.png


# Vertical combine
convert -append name-*.jpg op.jpg
```

## Curl Commands

```sh
curl --form "file=@/Users/pujan/filename.txt" -F file=@2.jpg  http://host/api/

curl -X GET http://localhost/api

curl -X POST -F files=@/Users/pujan/1.png -F files=@/Users/pujan/2.png http://host/api/upload -v

curl -X POST -d 'job={"imageurl":["http://localhost/2.tiff"], "jobtype":"new"}' http://localhost/a/api/job/insert

curl -X POST -H "Accept:application/json" -H "Content-Type: application/json" -d '{"method":"ping", "client": {"version":"1.0", "platform":"fibble/1.0"}, "id":"id-01"}' "http://54.191.112.207:8080/ial/remote/jsonrpc"

curl -H "Content-Type: application/json" -X PUT -d '{"name":"Pujan S.","gender":"M"}' http://host/api/

curl --head --compressed quora.com
```

## Jar Commands

```sh
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
```sh
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

## NPM

```sh
tsc         # typescript
n           # Version manager for node
ng          # Angular
npkill      # Search subdirectory for deletes selected node_modules directory 
tldr        # tldr;
```

## Personal Bash Commands

```sh
remindme            # Remind if command is completed. TO submitted CMD && remindme
passwordGenerator   # Password
```