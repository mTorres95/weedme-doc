+++
title = 'How To'
date = 2024-01-08T15:26:41-03:00
draft = false
weight = 2
+++

### Creating this tutorials

The objective is to convert the Scribe's PDFs into markdown files

1. Start by creating a folder for each "tutorial" according to the
[Scribe PDFs](https://drive.google.com/drive/u/0/folders/1RlThL1C-CQTR0bWSAStBjraZ7T4qaj3u)

2. Take the screenshoots from the PDF (or the app itself if you think
that'd look better) and save them in the just created folder

3. Create a new file `_index.md` <- MUST have this title

4. Write the header of `_index.md`. Replace the variables `[]`

```
+++
title = '[title of the page]'
date = [today in ISO 8601 format]
draft = false
weight = [integer of the order in the menu]
+++
```

5. Write the content of `_index.md`

    Example for instruction: 

    > If you write `**1.** Navigate to "Components" tab`   
    > You'll see **1.** Navigate to "Components" tab

    Adding picture:

    > `![First step](1.png)`