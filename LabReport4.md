# Lab Report 4
Junrong Chen

## Log into ieng6
![login](https://github.com/JunrongChen2004/CSE15L/assets/122309066/625ad7d9-6d15-4610-ac28-0c66466403d5)
### Keys Pressed:
`<up>` get my last command line since my last command on my local terminal is logging into the remote server `<enter>` execute the command line and take me to the remote server

## Clone your fork of the repository from your Github account (using the SSH URL)
![clone](https://github.com/JunrongChen2004/CSE15L/assets/122309066/ab996e88-459d-4126-99cc-3b244c44a9ca)
### Keys Pressed:
type `<git clone>` as it is the command for cloning `<command><v>` as I have already copy the ssh link and this command let me paste the link into the command line and then press `<enter>` in order to run the command line.

## Run the tests, demonstrating that they fail
![fail-tests](https://github.com/JunrongChen2004/CSE15L/assets/122309066/42490cc5-4fef-4f37-ac28-3d98abb1c446)
### Keys Pressed:
type:`<bash test.sh>`and press `<enter>`in order to run the jUnit test results

## Edit the code file to fix the failing test
![fix-bug](https://github.com/JunrongChen2004/CSE15L/assets/122309066/f438f299-e7e2-44e8-b9b8-f36c9f475d2d)
**Keys Pressed:**
- Type `<cd lab7>` in order to change directory to lab7
- Type `<vim ListExamples.java>` and press `<enter>` in order to open the java file in the terminal for further edit.
- Pressed `<Ctrl-D>` three times to quickly exit the current prompt.
- In the file `ListExamples.java`, located the line 44 where `index1 += 1;` is present.
- Used `<right>` arrow key six times to move the cursor to the number 1 in `index1`.
- Entered the text editor with `<i>` for insert mode, replaced the number 1 with 2, and exited with `<Esc>` to exit the insert mode, followed by `<:wq>`, which is exit the vim mode and then `<enter>` to run the `:wq` command.

## Run the tests, demonstrating that they now succeed
![succeeded test](https://github.com/JunrongChen2004/CSE15L/assets/122309066/5cc74e35-382f-4033-af66-d1fa788874ef)
**Keys Pressed:**
- press`<up><up>` since I want the command line `bash test.sh`, which is two lines above and press `<enter>` to run the command line.

## Commit and push the resulting change to your Github account
![commit](https://github.com/JunrongChen2004/CSE15L/assets/122309066/1fe5edb2-7dae-46d1-a7ba-35ec1a244f21)
**Keys Pressed:**
- type `<git add .>` to stage all changes in the current directory and its subdirectories for the next commit and `<enter>` to run the command
- type `<git commit -m "Fixed Bug">` to create a new commit with a commit message "Fixed Bug" and `<enter>` to run the command
- type `<git push origin main>` push the committed changes from your local branch (in this case, the "main" branch) to the corresponding branch on the remote repository and `<enter>` to run the command
