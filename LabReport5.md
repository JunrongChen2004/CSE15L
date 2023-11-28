# Lab Report 5
Junrong Chen

## Original Post
### Strange Output in Java Program
Hi everyone,
I'm having a weird issue with my Java program, and I can't figure out what's going wrong. 
I've attached a screenshot of the output below. The program is supposed to take user input for two numbers and then print their sum, but the output is not what I expected. 
I've double-checked my code, and it seems fine to me. Can someone help me figure out what might be causing this?
<img width="541" alt="屏幕快照 2023-11-27 下午9 40 14" src="https://github.com/JunrongChen2004/CSE15L/assets/122309066/df375971-5b78-43e4-8b3a-86086df451bf">
<img width="445" alt="屏幕快照 2023-11-27 下午10 26 29" src="https://github.com/JunrongChen2004/CSE15L/assets/122309066/6e34bf20-28c0-4762-bf4f-94c64351ebac">
<img width="546" alt="屏幕快照 2023-11-27 下午10 27 03" src="https://github.com/JunrongChen2004/CSE15L/assets/122309066/b2fd74c3-83a0-40e1-a14b-4c9aa206f194">
I appreciate any help you can provide!

## TA Response
Hi there!

Thanks for reaching out. It looks like there might be a small mistake in your code. 
Take a look at the line where you calculate the sum. I see a potential issue there. 
Can you try modifying that line and see if it resolves the problem?

## Student FollowUp
Thank you! The bug is fixed. Now my code looks like this. It worked well. The bug seems like to be I accidentally wrote minus where it should be plus!
<img width="496" alt="屏幕快照 2023-11-27 下午9 54 34" src="https://github.com/JunrongChen2004/CSE15L/assets/122309066/f43e6654-1977-4683-a76c-c6564f35c3ef">

## Setup Information
**File & Directory Structure:**
- SumCalculator
  - SumCalculator.java
**Contents of SumCalculator.java (before fixing the bug):**
```java
import java.util.Scanner;

public class SumCalculator {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the first number: ");
        int num1 = input.nextInt();

        System.out.print("Enter the second number: ");
        int num2 = input.nextInt();

        int sum = num1 - num2;  // incorrect sum calculation

        System.out.println("Sum: " + sum);
    }
}
```
```bash
javac SumCalculator.java
java SumCalculator
```

**Command lines to trigger this bug**
- Type `cd Downloads` where the java file and the bash script is located
- Type `bash LabReport5.sh` to run the bash script
- Enter the first number (for the one in the screenshot, I typed `1`), and then press `enter`
- Enter the second number (for the one in the screenshot, I typed `2`), and then press `enter`

**Description of what to edit to fix the bug**
Running the command of `bash LabReport4.sh` will run the script inside the bash script, which is compile and run the java file. 
Entering number 1 and 2 will get the result of -1, which is actually the difference between the two numbers.
So there should be something wrong in the calculation part.
Change the minus sign in Line 13 to plus sign since it is calculating sum. 
