# Learning
A list of topics which I will be documenting for ease of access and reusability.

# Creating a C Shell

What is a Shell?
A Shell is a Command Line Interpreter
Bascially it acts as an intermediate between the USER and the KERNEL

Example of what a shell does:
USER --> I want to delete a file 
SHELL --> Searches for the requested file 
SHELL --> Requests the KERNEL to Execute a command via System Call 
KERNEL --> Checks permissions and sends request to FILE SYSTEM DRIVER to delete the file 
FILE SYSTEM DRIVER --> Deletes the file by updating metadata and freeing disk space 
KERNEL --> Returns status to SHELL 
SHELL --> Displays the Status and awaits for next Instruction

Types of SHELLs
1. C Shell (CSh)
--> ends with a percent sign (%)
   
3. Bourne Shell
--> ends with a dollar sign ($)
--> Linux supported systems

What is Shell Script?
--> Shell commands are stored in a file called Shell Script

What is a Terminal?
--> It is a Interface to interact with the Shell via commands

Basic Lifetime of a Shell
--> Basically how a Shell operates or functions during its lifetime

1. Initalize
--> A typical shell reads and Executes its configuration files
--> The configuration files changes the aspects of the shells behaviour

2. Interpret
--> The shell reads commmands from stdin and executes them
--> The commands could be interactive or a file

3. Terminate
--> After execution of the commands, the shell executes any shutdown commands
--> Then it frees up any memory and terminates

These # steps form the basis of many programs. We will try to make a SHELL that does not need
any sort of configuration files and no need for any shutdown commandl to keep it simple.
Instead, we will just call the looping function and terminate.

int main(int argc, char **argv)
{
  // Load config files, if any.

  // Run command loop.
  lsh_loop();

  // Perform any shutdown/cleanup.

  return EXIT_SUCCESS;
}

Here is a function, lsh_loop() that will loop, interpreting commands.

Basic Loop of a Shell

