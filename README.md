<img src="https://avatars.githubusercontent.com/u/25052038?s=200&v=4" alt="Netology" width="50" height="50">

# "Assignment for the 'Git Tools' lesson." - Sergey Mikhalev

### The goal of the assignment.

As a result of completing the assignment, you will:

* Learn how to work with Git utilities.
* Practice solving typical tasks that arise when working in a team.

### Assignment instructions.

1. Clone this: [repository](https://github.com/hashicorp/terraform) with Terraform source code.
2. Create a file for the assignment answers in your repository. After completing the task, attach the link to the .md file with the answers in your personal account.
3. Feel free to ask any questions about solving the tasks in the chat of the study group.

------

## Task

In the cloned repository:

1. Find the full hash and comment of the commit whose hash starts with aefea..

**Solution**</br>
  I used the command ```git show --pretty="%H: %s" --name-only aefea``` instead of ```git show aefea``` to shorten the output.</br></br>
  ![Task_1](images/Task_1.png)

2. Answer the questions.

* Which tag corresponds to the commit `85024d3`?

**Solution**</br>
  I used the command ```git tag --contains 85024d3 | sort | head -n1```, but ```git log -1 85024d3```  will also work.</br></br>
  ![Task_2](images/Task_2.png)
  
* How many parents does the commit  `b8d720`? Write their hashes.

**Solution**</br>
  I can find information about parents in the output of the command ```git log -1 b8d720```. I used the command ```git show --pretty=format:%P b8d720``` for more accurate information. There are two parents, their hashes are:</br>56cd7859e05c36c06b56d013b55a252d0bb7e158 </br>9ea88f22fc6269854151c571162c5bcf958bee2b</br>
  ![Task_3](images/Task_3.png)</br>
  
* List the hashes and comments of all commits made between the tags  v0.12.23 и v0.12.24.

**Solution**</br>
  I used the command ```git log v0.12.23..v0.12.24 --pretty=format:"%H: %s"```</br></br>
  ![Task_4](images/Task_4.png)</br>
* Find the commit in which the function `func providerSource`, was created. Its definition in the code looks like this: `func providerSource(...)` (arguments are listed instead of ellipsis).

**Solution**</br>
  I used the command ```git log -S'providerSource' --pretty=format:"%H %cd" | tail -n 1```</br>
  ![Task_5](images/Task_5.png)</br>
  I can get the full information about the function using the command ```git log -S 'func providerSource'```</br></br>
  ![Task_5_1](images/Task_5_1.png)</br>
* Find all commits where the function `globalPluginDirs` was changed.

**Solution**</br>
  The most comprehensive answer will be found in the output of the command ```git log -GglobalPluginDirs --stat```, but I used the command ```git log -S'globalPluginDirs' --pretty=format:"%H"```  to output a list of commits without extra information.</br></br>
  ![Task_6](images/Task_6.png)</br>
* Who is the author of the function `synchronizedWriters`?

**Solution**</br>
  This function has two authors:  James Bardin and Martin Atkins. ```git log -S synchronizedWriters --pretty=format:"%h %an"```</br></br>
  ![Task_7](images/Task_7.png)</br>
