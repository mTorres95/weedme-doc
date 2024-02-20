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

# Add the "How To" flows

1. Start hugo

```
hugo server
```

2. On your browser, go to `localhost:1313/weedme-doc/` -> the previous
command will indicate that, showing you something like this:
```
Web Server is available at http://localhost:1313/weedme-doc/ (bind 
address 127.0.0.1) 
```

3. Open the `weedme-doc` folder in Visual Studio code
```
code .
```

4. Before starting to modify, try a `git pull` in case someone else
has pushed some new changed. Do this each time!

4. Go to `PMD > How To` and create a new folder with the name like
the PDF you're going to add to the tutorial.

    *Example:* To add [this PDF](https://drive.google.com/file/d/1IPe4rNCSi-XoQx8OHmUmL9QL3A-5560q/view?usp=drive_link)
    titled *"3.1. Create a Component"*, create a folder called 
    `CreateaComponent` and ***in*** this folder, save the images 
    taken as screenshoots from the PDF and create a new file called 
    `_index.md`, that needs this header:

    ```
    +++
    title = 'Create a Component'
    date = 2024-01-08T15:26:41-03:00
    draft = false
    weight = [a integer indicating it's position on the menu]
    +++
    ```

5. In the just created `_index.md`, add the steps and the images

    * Add the image: `![](nameOfPicture.png)`

6. Once you've *finished* and like how the page looks, update GitHub.
It is **very important** to pull before pushing.

    * `git add .`
    * `git commit -m "How To - Create a Component"` <- replace the 
    *Create a Component* by the correct name
    * `git pull origin main` <- this will get you any changes someone
    else has made while you where working, so you don't have merge
    issues. If you do find merge issues, contact one of the devs.
    * `git push origin main`