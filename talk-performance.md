% How to succeed in reproducible research without really trying
% Dr. Geoffrey Oxberry
% Lawrence Livermore National Laboratory

# Computational science has culture problems
- **Lack of verification**: Where's the bug?
    + My method?
    + Its implementation?
    + Its dependencies?
- **Lack of transparency**
    + No public code & data = tough for others to debug
    + Do results only show "good" case studies?
- **Efficiency**
    + Costly to implement everything from scratch
    + Bad record-keeping makes research, revision, collaboration harder
<!--Above slide establishes need -->

<!--Before first non-title slide: Pandoc metadata, after percentages-->
<!--Title-->
<!--Author(s) separated by semicolons or white space-->
<!--Date (replaced here by affiliation for now)-->

<!--Originally, 1st slide was attention getter; no attention getter -->
<!--here due to restrictions on image use by LLNL-->

<!--Task-->

# We can fix these problems...<br />we have the technology
- Tools available to automate:
    + Record-keeping
    + Testing
    + Building paper
- Services available for storing research outputs

<!--Main message-->

# Reproducible research practices: a solution
- Reproducibility of work yields:
    + **Verification**: easier to find and fix bugs
    + **Transparency**: leads increased citation count, broader impact
    + **Efficiency**: via de-duplication of effort
- In this talk, I ignore restrictions due to:
    + Classified or sensitive material
    + Nondisclosure agreements
    + Software licensing issues
- Partial reproducibility may still be possible despite restrictions  

<!--Preview/Outline-->

# How to succeed in reproducible research <br /> without really trying
- State of reproducible research to-date
    + Defining "reproducible research"
    + Motivating reproducible research
- Tools and services to do reproducible research at reasonable cost
    + How and where to host code & data
    + Automate verification
    + Where to host everything else, and getting credit for it
- Challenges still exist
    + Objections, and overcoming them
    + Needed policies, tools, cultural changes
  
<!--Point 1: State of reproducible research to-date-->

# Reproducibility has long history
- Mathematical proof is one form of reproducibility
    + First: Greek mathematicians (_ca._ 400 BC)
    + Modern rigorous proof: 1800s
- Notable experimental examples
    + Galileo (1620s) built several copies of his telescope
    + Pasteur added "Materials and Methods" sections to his journal
    articles[@Buckheit1995]
- Modern scientific movements
    + Structural and protein biology (1980s)[@Morin2012]
    + Political science (1990s)[@King1995]
    + Genomics and genetics (2000s)[@Schofield2009; @Morin2012; @Birney2009]
    + Statistics (2010s)[@Peng2009a]

# Reproducible research =<br /> "post paper and all supporting materials"
- Reproducible research has many definitions[@Vandewalle2009a]
- In this presentation, "reproducible research" means submitting _at minimum_:
    + the paper
    + all code & data to reproduce results under open source licenses[@Stodden2009]
    + README files describing code & data
- Minimum standard chosen to minimize cost
- Can be helpful to do more

# Most computational science <br /> **not** reproducible currently
- People do not post the code & data with their work[@Merali2010a; @Barnes2010; @Morin2012]
- Even reproducible research gurus have published papers without code
  & data
- They recount those experiences as cautionary tales[@Buckheit1995; @Vandewalle2009a; @LeVeque2009a; @LeVeque2006]

# Lack of reproducibility causes problems
- Typical anecdotes[@Buckheit1995; @Vandewalle2009a; @LeVeque2009a; @LeVeque2006; @Price1986; @Merali2010a]:
    + Which version of code goes with paper?
    + Where's the bug: method or implementation?
    + Easy to forget research set aside for months
    + Results can depend on "magic parameter settings"
    + New person in lab can't repeat former grad student's work
- Reproducible research helps avoid these issues

# Doing reproducible research has benefits
- Reproducible research tends to be cited more[@Vandewalle2009a; @Piwowar2007a]
- In addition, reproducible research has the following anecdotal benefits[@Buckheit1995; @Vandewalle2009a; @LeVeque2009a; @LeVeque2006]:
    + Enhanced knowledge transfer 
    + Easier to resume projects after hiatus
    + Easier to train new researchers
    + Decreases time to revision
    + Attracts collaborators
    + Decreases debugging time

<!--Transition from Point 1 to Point 2-->

# Reaping benefits of reproducible research <br /> reduces to habits and practices
- Basic principles of reproducibility in computational science like
  those in experimental sciences
- Like experimentalists, computational scientists need to:
    + Keep good records: notebooks and version control!
    + Include code, data, proofs, derivations
    + Use tests as control experiments
    
<!--Point 2: Tools and services to do reproducible research at reasonable cost-->

# Tools enable adopting these practices <br /> at reasonable cost
- Automating habits with tools and services reduces their cognitive burden
    + Version control systems
    + Repository hosting web sites
    + Unit testing frameworks
    + Build systems
    + Figure, data, preprint archives
- Examples, payoffs, and estimated costs (to learn basics) given

# Version control systems <br /> track all code changes in repositories
- **Examples**: [Git](http://git-scm.com/), [Mercurial](http://mercurial.selenic.com/), [SVN](http://subversion.apache.org/), [CVS](http://cvs.nongnu.org/), etc.
- **Payoffs**
    + Eases collaboration
    + Can track changes in any file type, and who made them
    + Can revert file to any point in its tracked history
- **Costs**
    + [2-3 days to learn](http://fperez.org/tmp/Version%20Control.html); learn by using on _everything you can_
    + SVN, CVS require their own server (Git & Mercurial don't)
    + Takes a long time to master (much like LaTeX, MATLAB)
  
# Repository hosting sites available
- **Examples**: [GitHub](https://github.com/), [BitBucket](https://bitbucket.org/), [Google Code](https://code.google.com/), [SourceForge](http://sourceforge.net/), etc.
- **Payoffs**:
    + Eases collaboration
    + Free backup of project files
    + Publicity
    + [Academics: free private space on BitBucket](https://bitbucket.org/plans)
- **Costs**:
    + 1 hr to register, sync up files
    + Private space usually costs money
    + Space is limited (usually 1 GB or so)
    + Limited by terms of service
  
# Unit testing frameworks <br /> ease debugging, verification
- **Examples**: [MATLAB xUnit](http://blogs.mathworks.com/steve/2010/06/27/matlab-xunit-301/), [Python Nose](http://nose.readthedocs.org/en/latest/), [GoogleTest](http://code.google.com/p/googletest/), etc.
- **Payoffs**:
    + Automates verification
    + Easier to write tests
    + Reduce software development time costs; get papers faster[@Wilson2012]
- **Costs**:
    + 1-2 days to work through examples
    + Each language has its own framework
    + Most frameworks use [xUnit standard](https://en.wikipedia.org/wiki/XUnit)

# Build systems automate <br /> running tests, generating results
- **Examples**: [GNU make](http://www.gnu.org/software/make/), [SCons](http://www.scons.org/), [CMake](http://www.cmake.org/), [GNU autotools](http://www.gnu.org/software/autoconf/), etc.
- **Payoffs**:
    + Build code, test, run, all in one command
    + Build presentations, papers from LaTeX (or other) source
    + Avoid mistake-prone long chains of commands
- **Costs**:
    + 1-3 days to work through basic examples
    + Takes a long time to master
    + Tough to debug

# Services host and track pre-prints, data, etc.
- **Examples**:
    + _Pre-prints_: [arXiv](http://arxiv.org/), [Optimization Online](http://www.optimization-online.org/), [FigShare](http://figshare.com/), etc.
    + _Data, Figures, Presentations_: FigShare, [DataDryad](http://datadryad.org/), [ORCID](http://orcid.org/), etc.
- **Payoffs**:
    + Free space for hosting
    + Assignment of persistent DOIs
    + Tracking citation metrics (FigShare, ORCID)
- **Costs**:
    + Registration: 1 hour
    + Sometimes, [license restrictions placed on posted material](http://figshare.com/cc_license)
    + Limited or no private storage space

<!--Transition from Point 2 to Point 3-->

# Tools reduce costs of reproducible research
- Recall that reproducibility of work yields:
    + **Verification**: easier to check and debug work
    + **Transparency**: increased citation count, broader impact
    + **Efficiency**: de-duplication of effort
- These benefits map to tools as follows:
    + **Verification**: download hosted code, build it, run tests
    + **Transparency**: hosting sites store research record, tracked
    with FigShare & ORCID
    + **Efficiency**: releasing code promotes reuse, testing speeds
    debugging, versioning helps collaboration

# Despite reducing costs, challenges remain
- Tools make it easier to do reproducible research, but...
- Reproducible research is uncommon, and resisted[@Drummond2012]
- Policies requiring reproducibility have not been
  effective[@Ioannidis2009; @Savage2009]
- Technical challenges still exist (big data, supercomputing)

<!--Point 3: Challenges still exist-->

# Reproducible research practices: <br /> a solution _resisted_
- Most computational science research is not done reproducibly
    + Viewed as costing too much
    + Cost-benefit tradeoff considered unfavorable
- It **shifts costs from research _producers_ to research _consumers_**
    + Consumers re-implement, then check
    + Computational science community reputation also suffers[@Quirk2005b]
    + Contradicts the tradition that burden of proof is on producers
- Unreproducible research is a **false economy**
    + Producer savings: time spent making research reproducible
    + Consumer costs: time spent making _others'_ research reproducible
    + Producer costs: citations, reputation, wasted time redoing work
        
# Policies requiring reproducibility <br /> have not been effective
- Some journals and funding agencies require some form of reproducibility
    + [PLoS](http://www.plosone.org/static/policies.action), [_Science_](http://www.sciencemag.org/site/feature/contribinfo/prep/gen_info.xhtml#dataavail), others require sharing of code and data
    + [NIH](http://grants.nih.gov/grants/policy/data_sharing/), [NSF](http://www.nsf.gov/bfa/dias/policy/dmp.jsp), [DOE](http://genomicscience.energy.gov/datasharing/index.shtml) require sharing of data
- Despite policies, researchers still don't share data or code[@Savage2009; @Ioannidis2009]
- ...because policies aren't enforced
- Even if code and data provided, research still may not be
  reproducible[@McCullough2007; @McCullough2008; @Ioannidis2009; @Manolescu2009];
  better than no code at all 
- Better policies must align community and personal incentives[@Morin2012]
 
# Technical challenges also still exist
- Reproducing big data and supercomputing research is hard
    + Scarcity of resources (big storage, big supercomputers)
    + Best practices: cache intermediate data and
    results[@Freire2012a], cloud computing
- Making sure that source code works on other people's computers is hard
    + Installing software is tedious and hard
    + To run someone's code, need their whole development
    environment[@LeVeque2006; @LeVeque2009a; @Buckheit1995; @Vandewalle2009a; @Stodden2009; @Freire2012a]
    + Best practices: use virtual machines, provisioning software, reproducibility software
- Keeping detailed enough records -- provenance -- is hard
    + Provenance software: [VisTrails](http://www.vistrails.org/), [Madagascar](http://www.ahay.org/wiki/Main_Page), [Sumatra](http://software.incf.org/software/sumatra), etc.
    + Electronic notebooks like [Carl Boettiger's](http://carlboettiger.info/) tackle day-to-day record-keeping

<!--Review-->
<!--Summarize definition of reproducibility-->
<!--Tie definition to verification, transparency, and efficiency-->
<!--Tie these qualities to tools-->

# Ultimately, reproducible research is about <br /> verification, transparency, and efficiency
- Reproducible research is about sharing data & code with papers
- **Verification**
    + Publicly posted code & data makes checking work easier
    + Use tools like version control, unit testing, file hosting
- **Transparency**
    + Concerns and questions addressed by looking at code & data
    + GitHub and BitBucket list record of all changes to code, data, paper
    + FigShare used to share data publicly, track its citations
- **Efficiency**
    + Others do not necessarily have to redo existing work
    + Get more citations per paper
    + Easier to remember what you did after a long break
    + Easier to build upon, collaborate, transfer knowledge

<!--Conclusion-->

# Available tools let you do <br /> reproducible research without really trying
- Learning tools requires small investments to automate record-keeping
- Good record-keeping protects investments in scholarship
- Get more citations, save time later
- Posting code much better than not

<!--Acknowledgments-->

# Acknowledgments
- Victoria Stodden (posted a
  [literature review](http://wiki.stodden.net/ICERM_Reproducibility_in_Computational_and_Experimental_Mathematics:_Readings_and_References))
- ICERM (hosted [reproducibility workshop](http://icerm.brown.edu/tw12-5-rcem))
- Jaydeep Bardhan, Ahmed E. Ismail, Matthew Reuter, and friends (helpful discussions)
- Matt McNenly, Dan Flowers, Russell Whitesides, and LLNL colleagues (helpful discussions)
- Lawrence Livermore National Laboratory (funding via postdoc account)
- Gurpreet Singh (program manager)

<!--Colophon-->

# Colophon
- Presentation written in [Markdown](http://daringfireball.net/projects/markdown/)
- Compiled into [LaTeX](http://www.latex-project.org/)/[Beamer](http://bitbucket.org/rivanvx/beamer) using Pandoc
- Custom LaTeX/Beamer template
- Bibliography:
    + Content: [BibTeX](http://www.bibtex.org/) generated by [Mendeley](http://www.mendeley.com/) (manually curated)
    + Style: custom [CSL](http://citationstyles.org/) hacked from
    existing styles (attribution in comments)
- Source code hosting: [github/goxberry/siam-cse-2013-presentation](http://github.com/goxberry/siam-cse-2013-presentation)
- FigShare DOI: 
- ORCID:
  [orcid.org/0000-0001-7451-8097](http://orcid.org/0000-0001-7451-8097)
- Licensing: Reproducible Research Standard-like
    - Presentation: [CC-BY-3.0 licensed](https://creativecommons.org/licenses/by/3.0/us/)
    - Source code: BSD (except for CSL file, which is
      [CC-BY-SA-3.0](http://creativecommons.org/licenses/by-sa/3.0/))
      
<!--References/Bibliography-->

# References
\tiny

