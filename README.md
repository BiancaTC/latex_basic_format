# Latex basic format

This repository sums up the template for using latex. 
One can copy the file article (or book) and config, 
and then write inside the template `.tex` file in order to get an already configured latex file!

The configuration can be found inside config folder, and the names should not be changed.
The dependency is such that a minimal working example would require to have such directory tree:

```
Project
├── Config
│  └── the required config files
├── Project
│   └── project.tex
├── images_schools
└── page_de_garde.tex
```

In example, one can find some older projects where some pieces are interesting to understand how to use certain libraries.

Respect the structure of the project as there are some imports that needs to be updated if the directories' organisation
is changed.

# Difference Article / Book

Book are "book" style, while article are "amsart" style. 
In the later, there is neither "part" nor "chapter", as well as no presentation page.
Both support biblatex.
In order to compile correctly the document, it should be compiled a few times and with the additional bibtex reading if using it.



# Type Paper: a report or publication type?

explain_abstract and acknowledgment environment defined inside `configuration.tex`. The environment is called
explain_abstract and not abstract because abstract already exists.
In order to have a more colorful presentation, though it  is not the classical formatting for publication, it is possible to set the variable

`\ColorfulFormattrue`

which is set by default to `false`, corresponding to a more classical style.
In that situation, one cne can also write: `\ColorfulFormatfalse`.

The line should be added at the top of the `.tex` before importing the configuration files.

    \ColorfulFormattrue % Setting the state of the boolean variable \ifReportFormat` to true, 
    % otherwise it's false already. Or you could write %\ColorfulFormatfalse

### ColorfulFormattrue
Then, in `config_font.tex` and `config_boxes.tex`, the environment is changed to put a specific formatting.
In particular, if the formatting is set to `true`, the following environments are defined:

    \begin{definition}[my def]
    \end{definition}
    
    \begin{theoreme}[label = thrm:X]{my theo} 
    \end{theoreme}
    
    \begin{demo}{}{} 
    \end{demo}
    
    \begin{ajoutationV}{}{} 
    \end{ajoutationV}
    
If one wants to disable such formatting, just replace the variable by:  `\ColorfulFormatfalse`.

The formatting is undergone inside `config_font` and inside `config_boxes`. 

### ColorfulFormatfalse
When the variable is set to `false`, the following more classical definitions are made:

    \numberwithin{equation}{section}
    \newtheorem{theorem}{Theorem}[section]
    \newtheorem{corollary}[theorem]{Corollary}
    \newtheorem{lemma}[theorem]{Lemma}
    \newtheorem{proposition}[theorem]{Proposition}
    \newtheorem{conjecture}[theorem]{Conjecture}
    
    \theoremstyle{definition}
    \newtheorem{definition}[theorem]{Definition}
    \newtheorem{remark}[theorem]{Remark}
    \newtheorem{assumption}[theorem]{Assumption}

