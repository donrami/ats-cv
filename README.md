This repository is a personal fork of the original ats-cv project. I've adapted it for my own use, customizing the structure and templates to better fit my résumé style and needs.

The templates are based on simple yet effective LaTeX layouts that require minimal setup. The original BASE ROVER template, for example, needs only about 10 lines of code to create a clean, minimal résumé. No need for custom résumé classes — just standard LaTeX using the article class and preinstalled fonts.

These templates are also ATS (Applicant Tracking System)–friendly, using a single-column layout and standard commands to ensure easy parsing by both software and recruiters. It’s a balance of clean design and high compatibility.


## Getting Started
1. **Get the Repository**: Fork or Download this repository to your local machine.   
2. **Fill in Your Details**: Personalize the template by filling in your information.


### Tips for Using LaTeX Commands
- **Sectioning**: Use `\section` for major sections like Education, Experience, Certifications, Awards, Skills & Interests, etc.
- **Subsectioning**: Employ `\subsection{}` and `\subsubsection` for primary and secondary titles such as Institution Name, Position Title, Duration, etc.
- **Bullet Points**: Use `itemize` lists for creating bullet points.


## Known Issue

<details>

<summary>Package hyperref Warning:</summary>

This occurs because `hyperref` package creates clickable texts for both internal and external links. When generating a PDF, certain elements like bookmarks, metadata, and hyperlinks are encoded as **PDF strings**. Since `\section{}`, `\subsection{}` etc. are used in the *Table of contents* (i.e. bookmarks), certain LaTeX commands (like `\hfill`) or control sequences doesn't make sense in this context.

When `hyperref` encounters the `\hfill` command while processing a piece of text that needs to be converted into a PDF string, it cannot include this command in the output PDF string. As a result, it removes the command and issues a warning to notify you of this action. 

We can circumvents this issue by disabling the creation of bookmarks as shown below.


```latex
    \usepackage[bookmarks=false]{hyperref}
```

</details>


> [!CAUTION]
> To avoid generating warnings, the `bookmarks` option in the `hyperref` package must be set during package loading with `\usepackage[bookmarks=false]{hyperref}`. You can use `\hypersetup{}` for everything else.

## License

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><br><a property="dct:title" rel="cc:attributionURL" href="https://github.com/subidit/rover-resume">Rover Resume</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://github.com/subidit/">Subidit</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0</a></p>
