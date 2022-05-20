```{figure}  ../../figures/healthy-research-tree.jpg
---
name: Data-science-feeds-research
alt: Researchers are pouring water on a tree. The water represents data science principles and tooling, the tree represents the research. The tree is big and beautiful, on its branches are specific outcome written: more outputs, reproducibility, et cetera
---
_The Turing Way_ project illustration by Scriberia. Used under a CC-BY 4.0 licence. DOI: [10.5281/zenodo.3332807](https://doi.org/10.5281/zenodo.3332807).
```

(rr-vcs-git4research)=
# Git for research projects

Because each research project has a data science component,
there are clear advantages to use data science practices for 
the management of all the data produced during research.
In particular, the use of git and github is very appealing.
However, Github is not enough to handle all research projects:
- Data versioning needs special care {ref}`section on data version control<rr-vcs-data>`
- Specific {ref}`folder structure<rr-rdm-storage-organisation>` help in the workflow
- They may be some legal issue to use an american tool for your data.

You may refer to a carpentry workshop related to this topic: https://github.com/carpentries-incubator/managing-computational-projects

(rr-vcs-research-plus)=
## Potential


Here is a non-exhaustive list of features that 
a git/github workflow bring to data science projects,
and that would be useful for research projects:

- Backup data by pushing the data to a git platform, toward a public or private repository
- Easily use different computers to work on the same project (with yourself of with collaborators).
- Keep track of contributions.
- Facilitate the use of folder templates to help with files organisation, see {ref}`rr-rdm-storage-organisation`
- Use git platforms tools for project management
- Use git platforms for outreach, even when the repository is private (using the wiki)
- Create an associated website under the same organisation on the git platform


(rr-vcs-research-minus)=
## Issues

As described in the  {ref}`general section about git<rr-vcs-git-limitations>`,
git does not work well when there are a lot of data, or when the data are large.
When you expect the project to get large, one needs to set a different tooling
to avoid creating unpractical repositories, see the {ref}`section on data version control<rr-vcs-data>` for a detailed explanation. 

**Briefly, in order to use git when there are lots or large files, one needs to split the data in different repositories,
and have these repositories use the git-annex technology.**

(rr-vcs-research-tools)=
## Tools

We encourage you to use a git platform that is provided as an open infrastructure.
In many university, you will have access to a gitlab platform (which works very similarly to GitHub).
Alternatively, you may want to install your own instance of one of the more lightweight open source git platform (gogs, gitlea, GIN)

If you have many or large files,
you will need to use the git submodules and git-annex technologies. 
If you do, we encourage you to look into {ref}`rr-vcs-data-tools-datalad` and follow the prgresses of the [GIN-Tonic project](https://gin-tonic.netlify.app).


(rr-vcs-research-story)=
## Fictive exemple
 
Max has created a folder following a standard structure,
they uses datalad to create submodules for each experiment,
where they will save their datasets.
Using datalad, the git-annex technology is used to save
the file content outside of the git repository at every push.
They got their own GIN platform where the git repository and git-annexed content
is saved, and backed up.
Their collaborators have access to the whole data, either via the browser interface or using some command line tool.
The GIN repositories are linked to a gitlab issue, 
so that the team is using advanced project management tools offered by gitlab.
The data analysis code is also set in a submodule,
where git-annex is not allowed. 

After working for a couple of years on the project,
together with their collaborators, 
Max has written a paper where they could link both the data and the analysis code, 
which was made public by archiving the git repositories 
and the git-annexed data on the university library service.


While this use case is already possible,
it requires to use the command line (to use datalad),
and get a GIN instance installed 
(the public GIN instance is meant only for neuroscience data). 


