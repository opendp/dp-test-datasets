## Differential Privacy Datasets


# Git management
To add datasets to a parent project:  
```git submodule add -b master https://github.com/privacytoolsproject/datasets.git /```  

To clone an existing repository that uses datasets, init submodule after clone:  
```git submodule init```  

To update datasets in an existing project:  
```git submodule update --remote```  

Alternatively, `cd` into the submodule and `git pull`

If git warns about "detached head" when inside submodule, then:  
- from the submodule root:  
    ```git checkout master```  
- from the parent project root:  
    ```git config -f .gitmodules submodule.<submodule-path>.branch master```  

To commit changes to datasets from the parent project, then:  
1. from the submodule, `commit` and `push`  
2. from the parent project, `commit` and `push`  

Note that the .gitmodule is configured to use https, which prompts for passwords every time.  
To switch to ssh key authentication, then from the submodule root:  
```git remote set-url origin git@github.com:privacytoolsproject/datasets.git```  