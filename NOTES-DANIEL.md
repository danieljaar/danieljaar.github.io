# Daniel's notes

DOCUMENTATION HERE: https://pascalmichaillat.org/d5/


HUGO'S PAPER MOD: https://github.com/adityatelange/hugo-PaperMod/wiki/Variables

## Steps to Remove the Books Button and Page from Hugo Site

1. **Remove the "Books" button from the menu:**
   In the `menu` section of the configuration file, delete the entry for "Books":
   ```yaml
   menu:
       main:
           # - name: Books
           #   url: books/
           #   weight: 5
           - name: Papers
             url: papers/
             weight: 2
           - name: Courses
             url: courses/
             weight: 3
           - name: Data
             url: data/
             weight: 4 
           - name: Blog
             url: https://en.wikipedia.org/wiki/Moritz-Maria_von_Igelfeld_(character)
             weight: 6

2. **Remove the "Books" button from the profileMode section**:

```yaml
profileMode:
      enabled: true
      title: Daniel Jaar
      subtitle: "I am a Phd candidate in Economics at the University of Pennsylvania. My interests lie within macroeconomics and development. **In 2024/2025, I will be on the academic job market.**"
      imageUrl: "picture.jpeg"
      imageWidth: 160
      imageHeight: 160
      imageTitle: Daniel Jaar
      buttons:
        - name: CV
          url: cv.pdf
        - name: Job-market paper
          url: jmp.pdf
        - name: All papers
          url: papers/
        - name: Courses
          url: courses/
        - name: Data
          url: data/
        # - name: Books
        #   url: books/
        - name: Tags
          url: tags/
        - name: Archive
          url: archive/
        - name: Blog
          url: https://en.wikipedia.org/wiki/Moritz-Maria_von_Igelfeld_(character)

```
3. **Remove the "books" section from MainSections**
```yaml
params:
    description: "PhD candidate in Economics at the University of Pennsylvania."
    author: Daniel Jaar
    # googleAnalyticsID: "G-XXXXX"
    DateFormat: "January 2006"
    defaultTheme: light
    hideFooter: false
    disableThemeToggle: true
    ShowShareButtons: false
    ShowReadingTime: false
    disableSpecial1stPost: true
    disableAnchoredHeadings: true
    ShowPostNavLinks: false
    ShowBreadCrumbs: false
    ShowCodeCopyButtons: true
    ShowAllPagesInArchive: false
    # MainSections: ["books","courses","papers","data"]
    MainSections: ["courses","papers","data"]
    ShowRssButtonInSectionTermList: false
    ShowToc: false
    disableScrollToTop: true
    TocOpen: true
    ShowWordCount: false
    UseHugoToc: true
    comments: false
    math: true
```


It is not strictly necessary to delete the books folder if you only want to remove the button and links to the Books section from the navigation and profile sections. However, if the books folder remains, any content within it may still be accessible directly via its URL (e.g., https://danieljaar.github.io/books/).



## To change theme

Not many options really: dark, light or auto.

```yaml

params:
    description: "PhD candidate in Economics at the University of Pennsylvania."
    author: Daniel Jaar
    # googleAnalyticsID: "G-XXXXX"
    DateFormat: "January 2006"
    defaultTheme: light # light, dark or auto
    hideFooter: false
    disableThemeToggle: true

```


## Favicons

To change the favicon, generate them from an image here: https://favicon.io/.
For it to actually work, I had to change the default favicon in layouts/partials/head.html