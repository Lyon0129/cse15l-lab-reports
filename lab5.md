# step 1
Student: I don't know why my test has 1 failure.  
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/0e7f09d6-8dbd-4209-8d12-11faa46df101)
<img width="532" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/41c1671c-7956-4df7-98ea-6839d46dc16d">
<img width="413" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/b6430108-0941-4561-9f17-53c0938286e9">
# step 2
TA: Maybe you should check your ''getSize'' method.
# step 3 & 4
Student: I found that the "getSize" method always return 1, no matter how many "addFruit" method I use.  
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/b98c0d13-da07-4eda-ae8f-f2c2723b0fb6)
I try to use ``` vim BugExample.java``` to edit my file. I changed the ```return 1``` to ```return list.size();``` So I can always get the correct Arraylist size.  
use command ```:12``` to go to line 12. ```i``` to edit the file, change ```1 ```to ```list.size();``` ```<esc>:wq``` save the file and eixt.  
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/216ab97b-e068-4847-b9c3-93e7c69976cc)
```bash BugExampleTest.sh``` test the file.  
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/1b61e089-dddf-4eaf-bd3e-98e8ed4ca390)


# reflection
In the labs, I know how to use Vim to edit my file.
Efficiency: Vim's keybindings are designed to keep your fingers on the home row, which can make editing much faster once you've learned the commands.
Powerful Search and Replace: Vim's search and replace capabilities are very powerful and can handle complex patterns and text manipulations with ease.
I also know how to login to my ieng6 account without enter paassword and how to git push my file to github.




