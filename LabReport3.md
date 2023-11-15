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
```Bash
grep -i "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
```Bash
        the clear inequalities in science between developing and developed countries and to the
        importance of reducing the inequalities in science between developed and developing
        serious problems not only for the scientific community in the developing countries, but for
        development itself.” Indeed, Mr. Annan's sentiments have also been echoed recently by
        output between the developing and already developed countries (Gibbs 1995; May 1997;
        developed countries accounted for some 84% of the global investment in scientific research
        and development, had approximately 72% of the world researchers, and produced approximately
        2001). But is the disparity in scientific contributions between the developed and
        developing worlds actually remaining unchanged or even increasing, as Mr. Annan has
        developing countries. For example, Latin America and China, although representing,
        publications between the developed world and the developing world from 1990 until 2000,
        and development (May 1997). The proportional change in the number of publications, using
        invested in research and development for each region, also show that, in contrast to both
        cheaper in the developing world due to relatively low researcher salaries, overhead and
        of publications per amount of money allocated to research and development in Latin America,
        demonstrate that such developing regions as Latin America are making substantial
        of its resources in scientific research and development. Latin American investment in
        research and development represented only 0.59% of the regional GDP in 1998, a very weak
        development investment in the 10 years studied, which is notoriously high compared with
        research and development than the other countries of this region (Albornoz 2001).
            development been increasing in Latin America while decreasing in United States and
        is that scientific development during the 1990s was particularly strong for many countries
        research and development has been increasing in Latin America while decreasing in the
        funding to the most productive scientists from the national science development programs
        What, exactly, is the relative impact of such developing regions as Latin America on the
        with 4% in the top 10). These findings suggest that publications from such developing
        (Swinbanks et al. 1997) and thus could be a general phenomenon in the developing world.
        Although there are outstanding scientific researchers in the developing world who
        and that the top journals, which are published in the developed world, respond more to the
        scientific mainstream of the developed regions. This is not to suggest any sort of
        developed regions are listed by the SCI than similar journals from developing regions
        available to scientists from the developed region, whereas much of the research published
        locally in the developing world is overlooked. But it takes more than publishing good
        meetings for researchers in the developing compared with the developed world.
        developing world (Goldemberg 1998; Annan 2003). One is that science, as a discipline, would
        readily with the cooperation and scientific insight of scientists from developing regions.
        from those developing regions that are so important for these global processes. It is also
        critical for the developing world to promote, through research and publications, those
        them. There are now examples in which research on priority areas for the developing nations
        examples are important not only for those regions of the developing world, but are also in
            input from those developing regions that are so important for global processes.
        developing countries contribute a more equitable share to the international scientific
        development, demonstrates that many developing countries are heading in the right
        direction. The extremely high scientific productivity of many developing nations, corrected
        to the sciences will be an excellent investment by developing nations in terms of
```
![grep -i files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/aec42645-e728-4a7a-943b-a17c1155d68d)
Displays all lines in journal.pbio.0020001.txt containing "develop" ignoring case.

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

#### directory
```Bash
grep -ir "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
![grep -ir directories](https://github.com/JunrongChen2004/CSE15L/assets/122309066/b1f7b8d6-9c65-471f-b891-6afbaf819f4b)
Recursively searches for "develop" in all files in the plos directory ignoring case.

Source: https://www.geeksforgeeks.org/grep-command-in-unixlinux/

### -n
#### files
```Bash
grep -n "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
![grep -n files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/fe780e42-7b38-4341-a049-23de970ee798)
Displays line numbers for lines containing "develop" in journal.pbio.0020001.txt.

Source: https://linuxize.com/post/how-to-use-grep-command-to-search-files-in-linux/#grep-command-syntax

#### directory
```Bash
grep -nr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
![grep -nr directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/24478f44-99c8-4aa8-9e6a-50c7db3fc561)
Displays line numbers for matches in files within the plos directory.

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
```Bash
grep -v "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
![grep -v files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/6f5ffafa-26f3-41ce-a647-a053bea35323")
Displays lines not containing "develop" in journal.pbio.0020001.txt.

Source: https://www.linfo.org/grep.html

#### directory
```Bash
grep -vr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
![grep -v directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/0e0f4658-5d97-4c6e-a3e9-a553b0bea87a)
Displays lines not matching "develop" in files within the plos directory.

Source: https://linuxhandbook.com/grep-search-all-files-directories/#:~:text=You%20can%20make%20grep%20search,grep%20%2Dr%20search_term%20.
https://www.linfo.org/grep.html

### -c
#### files
```Bash
grep -c "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos/journal.pbio.0020001.txt
```
![grep -c files](https://github.com/JunrongChen2004/CSE15L/assets/122309066/3bc55af7-3cf7-434b-8a30-f056a1c801ce)
Displays the count of lines containing "develop" in journal.pbio.0020001.txt.

Source: https://ss64.com/bash/grep.html

#### directory
```Bash
grep -cr "develop" /Users/chenjunrong/Downloads/docsearch/technical/plos
```
![grep -c directory](https://github.com/JunrongChen2004/CSE15L/assets/122309066/acfaf464-6e78-4c44-b2ca-d30dc72bcd98)
Counts the occurrences of "develop" in files within the plos directory.

Source: https://ss64.com/bash/grep.html
https://linuxhandbook.com/grep-search-all-files-directories/#:~:text=You%20can%20make%20grep%20search,grep%20%2Dr%20search_term%20.
