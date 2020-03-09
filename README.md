# Commands
Productivity Commands List

[Bash Commands](bash.md)

[Brew Commands](brew.md)

[Curl Commands](curl.md)

[macOS Commands](mcos.md)

[NPM Commands](npm.md)


## Find


```shell script
# Find and Replace
find . -name "*.java" -print0 | xargs -0 sed -i '' -e 's/packtpub/appkubos/g'

# Find and du
find . -name "node_modules" -type d -prune | xargs du -chs
```


## sed & awk

```shell script
sed -i -e 's/<first>true<\/first>/<first>false<\/first>/' /Users/psrivastava/scripts/config/settings.xml

# print 5-12 lines of file
sed -n '5,12p;12q' ~/a.txt

# Replace the first occurrence of a string in a file, and print the result:
sed 's/find/replace/' filename

# Replace all occurrences of an extended regular expression in a file:
sed -E 's/regex/replace/g' filename

# Replace all occurrences of a string in a file, overwriting the file (i.e. in-place):
sed -i '' 's/find/replace/g' filename

# Replace only on lines matching the line pattern:
sed '/line_pattern/s/find/replace/' filename

# Print only text between n-th line till the next empty line:
sed -n 'line_number,/^$/p' filename

# Apply multiple find-replace expressions to a file:
sed -e 's/find/replace/' -e 's/find/replace/' filename

# Replace separator / by any other character not used in the find or replace patterns, e.g., #:
sed 's#find#replace#' filename

history | awk '{print $2}'

```

## Database Related

Export to Single csv file
```sql
@set maxrows 10000000;
@export on;
@export set filename="/Users/pujan/result.csv" CsvIncludeColumnHeader=false CsvColumnDelimiter=",";

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


## Miscellaneous Commands

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
