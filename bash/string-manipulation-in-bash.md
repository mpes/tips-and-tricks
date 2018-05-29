## String manipulation in bash
[Advanced Bash-Scripting Guide: Chapter 10. Manipulating Variables](http://www.tldp.org/LDP/abs/html/string-manipulation.html)

`f=/home/mpes/extras.sh_123 ; `

String Length
`${#string}` or 
`expr length $string` or
`expr "$string" : '.*'`
> echo ${#f}

`${string%%substring}`
Deletes longest match of $substring from back of $string.
`${string%substring}`
Deletes shortest match of $substring from back of $string.

Show filename without extension 
> echo ${f%.*}
> ~/mpes/extras.sh_123

`${string#substring}`
Deletes shortest match of $substring from front of $string.

`${string##substring}`
Deletes longest match of $substring from front of $string.

Shows just the filename (equivalent to `basename $f`)
> echo ${f##*/}

Substring Replacement

`${string/substring/replacement}`
Replace first match of $substring with $replacement.

`${string//substring/replacement}`
Replace all matches of $substring with $replacement.

> echo ${f/\/home/"~"}
> ~/mpes/extras.sh_123

#### Print all variables starting with string and their values
`for f in ${!BASH*}; do  echo ${f} :  ${!f}; done;`

#### Set to default value if not set
`echo "${VARIABLE-default_value}"`

#### Read multiple separated values from one into multiple variables
```
x="A B C D"
read a b c d <<<  ${x}
echo $b
B 
```
#### Remove the trailing path name from a word using *:h*
```
ll something/subshell.sh
echo !!:$:h
> something
```
#### Remove all leading path name from a word using *:t*
```
ll something/subshell.sh
echo !!:$:t
> subshell.sh
```
#### Print expansion using *:p*
```
ll something/subshell.sh
!!:$:t:p
> subshell.sh
```
#### Insert last command onto commandline
<kbd>alt+\.<kbd/>

#### Insert nth argument  onto commandline
<kbd>alt+\<num\><kbd/>
