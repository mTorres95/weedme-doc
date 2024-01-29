# Preconditions

Have 
[`git`](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
and [`hugo`](https://gohugo.io/installation/) installed in your 
system.   
I also recommend having 
[`Visual Studio Code`](https://code.visualstudio.com/download).   
Basic knowledge of the terminal. 


# How to clone the project

First, decide where you want your projet to be and navigate to that 
location:

> **mkdir:** make directory command   
> `mkdir weedme`

> **cd:** change directory command   
> `cd weedme`

1. Clone the project
```
git clone git@github.com:torresmia/weedme-doc.git
```

You'll get a new folder called `weedme-doc`, which is the name of the 
repo

2. Navigate to the new folder
```
cd weed-me
```

3. Get the submodules (in order to get the theme 
[Relearn](https://github.com/McShelby/hugo-theme-relearn))
```
git submodule update --init --recursive
```

4. Start hugo

```
hugo server
```

5. On your browser, go to `localhost:1313/weedme-doc/` -> the previous
command will indicate that, showing you something like this:
```
Web Server is available at http://localhost:1313/weedme-doc/ (bind 
address 127.0.0.1) 
```

6. Open the `weedme-doc` folder in Visual Studio code
```
code .
```

