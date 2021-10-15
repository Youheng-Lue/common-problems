# common-problems
This file is a summary of common Problems and solutions

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

### Some of my function should run a function first
**Problem:** Some of my functions should always run something else first (e.g. check if key is in ID)
**Solution:**
Use decorators:
```
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
