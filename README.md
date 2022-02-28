# common-problems
This is a cheatsheet for common Problems that I had and their solutions. For problems more related to Hacking see my Repository <a href="https://github.com/Youheng-Lue/art-exploit">art-exploit</a>.
## Bash

* Symbolic link `ln -s [path of the target file] [symbolic name]`
* Redirect stdin to file `[command] | tee [target file]`
* Get only first word of line `awk '{print $1;}'`

### sed
* Replace deadbeef with \xde\xad\xbe\xef:
```bash
echo deadbeef|sed -E 's/(..)/\\x\1/g'
```

### Script usage
```bash
if [ "$#" -ne 1 ]
then
    echo "Usage: $0 arg1"
    exit 1
fi
```

### prettify things
* format xml: `xmllint --format -`
* cat with coloring `pygmentize -g <file>`

### grep
* Grep without: `grep -v`
* Grep next 20 lines `grep -A20`
* Grep any char `grep .`

### Tmux

* Show all sessions `Ctrl+B + S`
* Return to main `Ctrl+B + D`
* Kill all sessions `tmux kill-server`

## Check MD5 Hash on Windows
**Problem:** You downloaded a file and want to know how to check the MD5 hash on Windows


**Solution:**
- Run cmd
- Enter: `CertUtil -hashfil %name of file% MD5`. This will return the MD5 Checksum

## Remove first word of each line in Bash
**Problem:** You copy pasted code from a pdf and need to remove the incices

**Solution:**
- Run bash
- Enter: `cut -f 2- -d ' ' file.txt > new_file.txt`


## Python
### IDLE

* Comment a line `alt+3`
* Uncomment a line `alt+4`


### Some of my function should run a function first
**Problem:** Some of my functions should always run something else first (e.g. check if key is in ID)

**Solution:**
Use decorators:
```python
def pretty_sumab(func):                                                                                     
    def inner(a,b):                                                                                         
        print(str(a) + " + " + str(b) + " is ", end="")                                                     
        return func(a,b)                                                                                    
                                                                                                            
    return inner                                                                                            
                                                                                                            
@pretty_sumab                                                                                               
def sumab(a,b):                                                                                             
    summed = a + b                                                                                          
    print(summed)                                                                                      
                                                                                                            
if __name__ == "__main__":                                                                                  
    sumab(5,3)   
```

### I need to mock the input and output for unittesting
**Solution:**
In Progress. 

https://code-maven.com/mocking-input-and-output-for-python-testing#:~:text=That%20means%20every%20time%20input%20is%20called%20inside,collects%20any%20text%20typed%20in%20on%20the%20keyboard.

## R

### Comment out selection
Use `CTRL + SHIFT + C`

### Prettify Code
Use `CTRL + I`


## Latex

### Figure
Example:

```latex
\begin{figure}
    \includegraphics[width = \linewidth]{Path to graphic}
    \label{fig:label}
    \caption{Caption}
\end{figure}
```
