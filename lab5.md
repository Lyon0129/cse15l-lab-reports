Student: I don't know why my test has 1 failure.  
![image](https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/0e7f09d6-8dbd-4209-8d12-11faa46df101)
<img width="532" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/41c1671c-7956-4df7-98ea-6839d46dc16d">
<img width="413" alt="image" src="https://github.com/Lyon0129/cse15l-lab-reports/assets/130290363/b6430108-0941-4561-9f17-53c0938286e9">

TA: In your file BugExample.java, method ''getSize'' always ```return 1``` no matter you add how many fruits. In the file BugExampleTest.java, you called method ''addFruit''twice, and you want to determine the size is equal 2. You should change method ''getSize'' to ```return list.size;``` 
