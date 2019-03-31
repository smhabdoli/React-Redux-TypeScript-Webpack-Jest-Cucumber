# Reaction Repository

This is a repository for the following setup:

1. TypeScript as the language extension
2. Babel as the script compiler
2. React as the framework
3. Webpack for serving
4. Redux for storehouse
5. Jest-Cucumber for bdd

## Preparation:

1. Install nodejs if not installed.

   1. If you want a version controller, I recommend using [nvm](https://github.com/creationix/nvm).
  
   2. You can simply install node by downloading it from the [website](https://nodejs.org/en/download/) or using the 
      os's [package manager](https://nodejs.org/en/download/package-manager/).
          
      If you're installing on windows there's the option of 
      [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) but be warned, WSL crashes a lot when 
      installing npm libraries. Other options would be using [cygwin](https://cygwin.com/install.html), or using 
      virtual machines. You will have different options. Here are a few:
     
       1. [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine)
       2. [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
       3. [VMWare](https://www.vmware.com/support/ws5/doc/install_ws.html)
       4. [Virtual PC](https://www.microsoft.com/en-us/download/details.aspx?id=3702)

2. (Optional but highly recommended) Install a version control system (VCS). I recommend 
   [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), and creating a 
   [github](https://github.com) account. Alternatively, you can host your own local repsoitory using solutions like
   [gitlab](https://docs.gitlab.com/ce/install/). You do not need Enterprise edition necessarily, you can just use the 
   free community edition.

3. Choose an Integrated Development Environment (Highly recommended) or text editor. Here are a few options:
    
   ### IDEs:
    
    1. [Visual Studio Code](https://code.visualstudio.com/)
    2. [Eclipse](https://www.eclipse.org/ide/)
    3. [NetBeans](https://netbeans.org/downloads/8.0.2/)
    4. One of [JetBrain](https://www.jetbrains.com/)'s IDEs like [WebStorm](https://www.jetbrains.com/webstorm/). I 
       chose this one.
    5. [Komodo Edit](https://www.activestate.com/products/komodo-edit/)
    
   ### Text Editors:
   
    1.  [Sublime Text](https://www.sublimetext.com/3)
    2.  [Atom](https://atom.io/)
    3.  [Notepad++](https://notepad-plus-plus.org/download/v7.6.4.html)
    4.  [Vim](https://www.vim.org/)
    5.  [Emacs](https://www.gnu.org/software/emacs/)
    6.  [UltraEdit](http://www.ultraedit.com/?gclid=EAIaIQobChMI64fKhfms4QIVRbnACh3BZwceEAAYASAAEgKfavD_BwE)
    7.  [TextMate](https://macromates.com/download)
    8.  [TextWrangler](https://www.barebones.com/products/textwrangler/)
    9.  [Geany](https://www.geany.org/download)
    10. [Bluefish](http://bluefish.openoffice.nl/index.html)
    

4. Create Folder Structure as follows:

    1.  Main project directory. eg. **"reaction"**
    2.  A sub-directory for static public assets
    3.  A sub-directory for sources
    4.  A sub-directory under sources, for components
    5.  A sub-directory under sources, for types
    6.  A sub-directory under sources, for constants
    7.  A sub-directory under sources, for api
    8.  A sub-directory under sources, for redux
    9.  A sub-directory under redux, for actions
    10. A sub-directory under redux, for reducers
    
    The final structure will be something like this:
    
    ```Script
    reaction/
    ├─ .gitignore *
    ├─ .babelrc *
    ├─ .quokka *
    ├─ images.d.ts *
    ├─ node_modules/ *
    ├─ public/
    │  ├─ fav.ico *
    │  ├─ index.html *
    │  └─ manifest.json *
    ├─ src/
    │  ├─ api
    │  ├─ components
    │  ├─ constants
    │  ├─ redux
    │  │ └─ actions
    │  │ └─ reducers
    │  └─ types
    ├─ package.json *
    ├─ README.md *
    ├─ tsconfig.json *
    ├─ tsconfig.prod.json *
    ├─ tsconfig.test.json *
    └─ tslint.json *
    ```
    
    '*' will be added later.
    

5. (Optional) Create repository and add credentials.

    1. Create a github repository and follow instructions.
    
       ```bash
       cd reaction
       git init
       git config user.name "Your Name"
       git config user.email "Your Email"
       echo "Hello World!" > README.md
       ```

    2. Prepare credentials for remote project
    
        1. If you do not have multiple github user accounts:

           ```bash
           ssh-keygen -t rsa -b 4096
           ```
        
           Copy the contents of the id_rsa.pub file under ~/.ssh/ directory and add it to your github user's ssh keys.

        2. If you have multiple github accounts:

           ```bash
           ssh-keygen -t rsa -b 4096
           mv ~/.ssh/id_rsa ~/.ssh/id_rsa_your_github_user
           mv ~/.ssh/id_rsa.pub ~/.ssh/id_rsa.pub_your_github_user
           ```
           
           And create a file named config in ~/.ssh with the following contents:
           
           ```Script
           Host github.com-your_github_user
                Hostname github.com
                User git
                IdentityFile ~/.ssh/id_rsa_your_github_user
           ```

           Then you need to change permissions on the config file
           
           ```bash
           chmod 600 ~/.ssh/config
           ```
           
           Finally copy the contents of the id_rsa.pub_your_github_user file and add it to your github user's ssh keys.

    3. Add remote repository to local git setup:

        1. If you do not have multiple github user accounts:

           ```bash
           git remote add origin git@github.com:your_github_user/your_project_name.git
           ```

        2. If you have multiple github user accounts:

           ```bash
           git remote add origin git@github.com-your_github_user:your_github_user/your_project_name.git
           ```

    4. Create the **.gitignore** file in the root directory of the project and populate it with files and directory 
       patterns you do not want to include in version control. This usually includes but is not limited to:
        
        1. IDE files
        2. Node Modules
        3. Debug logs
        4. Process ID files
        5. Grunt file
        6. Compiled Addons
        7. Packs
        
       For simplicity, you can just use the **.gitignore** file provided in this project and modify it as you wish.

4. Install yarn and typescript globally.

   ```bash
   npm i -g yarn typescript 
   ```
