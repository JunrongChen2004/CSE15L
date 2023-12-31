# Lab Report 3
Junrong Chen

## Part 1: Bugs
### Code to test:
```Java
  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
### Failure-inducing jUnit test:
```Java
@Test
public void testReverseInPlace_FailureInducing() {
  int[] input = {1, 2, 3, 4, 5};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[]{5, 4, 3, 2, 1}, input);
}
```
### Not-Failure-inducing jUnit test:
```Java
@Test
public void testReverseInPlace_NonFailureInducing() {
  int[] input = {10, 20, 30, 40, 50};
  ArrayExamples.reverseInPlace(input);
  assertArrayEquals(new int[]{50, 40, 30, 20, 10}, input);
}
```
### Symptom - Output of Running Tests
![sympton](https://github.com/JunrongChen2004/CSE15L/assets/122309066/cb66043b-b1dc-4581-a072-f1840870de2e)

### Bug Fix
#### Before:
```Java
arr[i] = arr[arr.length - i - 1];
```
#### After (Fixed code for both methods):
```Java
int temp = arr[i];
arr[i] = arr[arr.length - i - 1];
arr[arr.length - i - 1] = temp;
```
The fix swaps elements properly by using a temporary variable to hold the value before assigning it to the reversed index. This addresses the issue by correctly storing the original element to be reassigned at its respective reversed index.

## Part 2: Researching Commands
### -i
#### files
command line:
```Bash
grep -i "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
output:
```Bash
        the clear inequalities in science between developing and developed countries and to the
        importance of reducing the inequalities in science between developed and developing
...        
        direction. The extremely high scientific productivity of many developing nations, corrected
        to the sciences will be an excellent investment by developing nations in terms of
```
![grep -i files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/aec42645-e728-4a7a-943b-a17c1155d68d)
Displays all lines in journal.pbio.0020001.txt containing "develop" ignoring case.

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

#### directory
command line:
```Bash
grep -ir "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
output:
```Bash
/Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0030032.txt:        have also developed independently of the Sloan Foundation, such as the Master of Science in
/Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0030032.txt:        development overseas; however, companies are mostly moving lab scientists, not strategic
....
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:        a prototype for a fully portable handheld model, which is now under development. After some
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:        should be commended for addressing an extremely important issue and developing this novel
```
![grep -ir directories](https://github.com/JunrongChen2004/CSE15L/assets/122309066/b1f7b8d6-9c65-471f-b891-6afbaf819f4b)
Recursively searches for "develop" in all files in the plos directory ignoring case.
ps: output too long to show all

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

### -n
#### files
command line:
```Bash
grep -n "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
output:
```Bash
7:        the clear inequalities in science between developing and developed countries and to the
10:        importance of reducing the inequalities in science between developed and developing
12:        ...
222:        direction. The extremely high scientific productivity of many developing nations, corrected
224:        to the sciences will be an excellent investment by developing nations in terms of
```
![grep -n files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/fe780e42-7b38-4341-a049-23de970ee798)
Displays line numbers for lines containing "develop" in journal.pbio.0020001.txt.
ps: output too long to show all

Source: https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/#grep-command-syntax

#### directory
command line:
```Bash
grep -nr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
output:
```Bash
/Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0030032.txt:52:        have also developed independently of the Sloan Foundation, such as the Master of Science in
/Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0030032.txt:139:        development overseas; however, companies are mostly moving lab scientists, not strategic
...
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:61:        a prototype for a fully portable handheld model, which is now under development. After some
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:69:        should be commended for addressing an extremely important issue and developing this novel
```
![grep -nr directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/24478f44-99c8-4aa8-9e6a-50c7db3fc561)
Displays line numbers for matches in files within the plos directory.
ps: output too long to show all

Source: ChatGPT
Input: How do I use grep -n for a directory
Output: To use the grep -n command for a directory, you can search through all files within the directory and display the lines containing the searched pattern along with their line numbers. Here's the command:
```Bash grep -nr "pattern" /path/to/directory```
Explanation:
grep is the command for searching text.
-n option displays line numbers for the matched lines.
-r option stands for recursive, allowing grep to search through all files in the specified directory and its subdirectories.
"pattern" is the text you're searching for.
/path/to/directory is the directory in which you want to search.
For example, if you're searching for the pattern "error" in all files within the ~/Documents directory and its subdirectories, the command would be:
```Bash grep -nr "error" ~/Documents```
This command will display the lines containing "error" along with their line numbers for all files within the ~/Documents directory and its subdirectories.
Change: change it to matching path and word.

### -v
#### files
command line:
```Bash
grep -v "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
output:
```Bash
chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt

  
    
      
        
        Kofi Annan, the Secretary-General of the United Nations, recently called attention to
        challenges of building bridges across these gaps that should bring the United Nations and
        ...
        to travel, we feel optimistic that the bridges mentioned by Mr. Annan are slowly being
        built.
      
    
  
```
![grep -v files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/6f5ffafa-26f3-41ce-a647-a053bea35323")
Displays lines not containing "develop" in journal.pbio.0020001.txt.
ps: output too long to show all

Source: https://www.linfo.org/grep.html

#### directory
command line:
```Bash
grep -vr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
output:
```Bash
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020273.txt:
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020273.txt:  
...
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:    
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:  
```
![grep -v directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/0e0f4658-5d97-4c6e-a3e9-a553b0bea87a)
Displays lines not matching "develop" in files within the plos directory.
ps: output too long to show all

Source: https://linuxhandbook.com/grep-search-all-files-directories/#:~:text=You%20can%20make%20grep%20search,grep%20%2Dr%20search_term%20.
https://www.linfo.org/grep.html

### -c
#### files
command line:
```Bash
grep -c "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
output:
```Bash
45
```
![grep -c files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/3bc55af7-3cf7-434b-8a30-f056a1c801ce)
Displays the count of lines containing "develop" in journal.pbio.0020001.txt.

Source: https://ss64.com/bash/grep.html

#### directory
command line:
```Bash
grep -cr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
output:
```Bash
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020273.txt:0
/Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0030032.txt:3
...
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020281.txt:0
/Users/chenjunrong/Downloads/docsearch/technical/plos/pmed.0020242.txt:4
```
![grep -c directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/acfaf464-6e78-4c44-b2ca-d30dc72bcd98)
Counts the occurrences of "develop" in files within the plos directory.
ps:output too long to show all

Source: https://ss64.com/bash/grep.html
https://linuxhandbook.com/grep-search-all-files-directories/#:~:text=You%20can%20make%20grep%20search,grep%20%2Dr%20search_term%20.
