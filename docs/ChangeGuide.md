# How to do changes in .md files
Markdown (filetype .md) is a markup language for virtual documents. HTML can also be used in this filetype. 

## Folder structure for GitHubs pages
* docs
    * index.md (homepage)
    * MedComLogo.png (used in the _config.yml file)
    * _config.yml (the configuration of the page, theme, logo ect.)
    * assets
        * documents
            * all the markdown files used in this project.
        * images
            * all the images used in this project.

## Lists
You can make different kinds of lists (enumerated, dot). See here: https://www.markdownguide.org/basic-syntax/#lists-1

## Formatting
_Italic_ use single underscore on each side of the text '_' (some uses '*') <br> 
__Bold__ use double underscore on each side of the text '__' (some uses '**') <br> 
> note: use single '>' in the beginning of the line <br> 
Read more here: https://www.markdownguide.org/cheat-sheet/#basic-syntax

## Tables
Recommends to use this table converter for markdown tables: https://www.tablesgenerator.com/markdown_tables# <br> 
If the above doesn't work, try making the table in html: https://www.tablesgenerator.com/html_tables 

## Table of content
To make a table of context, this generator can be used: https://ecotrust-canada.github.io/markdown-toc/

## Headlines 
The more #, the smaller does the headline become. See examples here: https://www.markdownguide.org/basic-syntax/#headings

## Text
Write like you would in a word-document.  <br> 
For linebreak < br > (without spaces inside the <>) can be used. Put a space _' '_ om each side. <br> 
It is also possible to use double enter.

## Images and Links
### Images
Using _'!'_ before the reference entails that the images is shown on the webpages. It is not neccesary to have a text in the squared parenthesis, but will be presented as 'Alternative text'. Ensure that you use the correct folder path.  
![Profile Content](/assets/images/ProfileContent.png)

### Links 
It is agreed, that links to external websites, shall open a new window, why the following html-form must be used. 
<a href="https://medcomdk.github.io/MedCom-FHIR-Communication/" target="_blank">Tab here to get more information about the Communication Rules.</a>

### Internal references
References within the file. The text in the squared parenthesis will be the text shown on the webpages. Writing the # will help you choosing the headline.
[5 Support or Contact](#5-support-or-contact)

References within the project, but outside the file. The text in the squared parenthesis will be the text shown on the webpages. Ensure that you use the correct folder path.  
[ENG-guideline](/documentation/NonTechnicalGuidelines_1.0.1.md)

## Release Notes
Every time you make a change, ensure to write a short comment in the ReleaseNote.md. 