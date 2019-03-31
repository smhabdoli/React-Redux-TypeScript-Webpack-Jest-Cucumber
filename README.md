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
          
     If you're installing on windows there's the option of WSL but be warned, 
     [WSL](https://docs.microsoft.com/en-us/windows/wsl/install-win10) crashes a lot when installing npm 
     libraries. Other options would be using [cygwin](https://cygwin.com/install.html), or using virtual machines. You 
     will have different optinos. Here are a few:
     
     1. [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/quick-create-virtual-machine)
     2. [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
     3. [VMWare](https://www.vmware.com/support/ws5/doc/install_ws.html)
     4. [Virtual PC](https://www.microsoft.com/en-us/download/details.aspx?id=3702)

2. (Optional but highly recommended) Install a version control system (VCS). I recommend 
   [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), and creating a 
   [github](https://github.com) account. Alternatively, you can host your own local repsoitory using solutions like
   [gitlab](https://docs.gitlab.com/ce/install/). You do not need Enterprise edition necessarily, you can just use the 
   free community edition.

3. Install yarn and typescript globally.

  ```bash
  npm i -g yarn typescript 
  ```
