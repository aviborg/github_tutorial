# github DevOps Tutorial
![devops-loop](https://github.com/user-attachments/assets/a1ab7fdc-2dc6-4b83-ab5f-7d0520d5a630)

## Create the repo (Plan)
1. Give it a name
2. Check the **Add a README file**
3. Click **Create repository**

## Create the first source file (Code)
1. Add file -> +Create new file -> hello.cpp
```C++
#include <iostream>

int main() {
    std::cout << "Hello World!";
    return 0;
}
```
2. Commit changes...

## Create workflow to build the file (Build)
1. Add file -> +Create new file -> .github/workflows/build.yaml
```yaml
name: Build 
on: 
 push: 
 workflow_call:

jobs:
 build_cpp:
   name: Build C++
   runs-on: ubuntu-latest
   steps:
     - name: Check out repository code
       uses: actions/checkout@v4
     - name: Build the file
       run: g++ hello.cpp -o hello
```



