% How to succeed in reproducible research without really trying
% Dr. Geoffrey Oxberry
% Lawrence Livermore National Laboratory

# Computational science has culture problems
- **Lack of verification**: Where's the bug?
    + My method
    + Its implementation
    + Its dependencies
- **Lack of transparency**
    + Unreproducible research = tough for others to debug
    + Distort results showing only "good" figures
- **Efficiency**
    + Costly to implement everything from scratch
    + Bad record-keeping makes collaboration, revision harder
<!--Above slide establishes need -->

<!--Original first slide-->
<!--# How to succeed in reproducible research <br /> without really trying-->
<!--This slide is an attention getter (or at least, it was, until I commented it out)-->
<!--Pandoc metadata after percentages, before first non-title slide: 
<!--Title-->
<!--Author(s) separated by semicolons or white space-->
<!--Date (replaced here by affiliation for now)-->
<!--"How to succeed in business without really trying" promotional poster goes in this slide-->
<!-- Notes: 500px by 500px is too big for Beamer; so is 799px by 354px, but 150px by 200px works -->
<!-- However, 150px by 200px is small for S5 and HTML-based slides -->
<!--![Promotional poster for "How to succeed in business without really trying"](how-to-succeed-150x200.jpg)\ -->

<!--Task-->

# We can fix these problems...<br />we have the technology
- Tools available to automate
    + Record-keeping
    + Testing
    + Building paper
- Services available for storing research outputs

<!--Six million dollar man picture and reference-->

<!--![Opening credits image of "The Six Million Dollar Man"](six-million-dollar-man-220x172.jpg)\ -->

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
<!--Preview-->

# How to succeed in reproducible research <br /> without really trying
- State of reproducible research to-date
    + Defining "reproducible research"
    + Motivating reproducible research
- Tools and services to do reproducible research at reasonable cost
    + How and where to host code
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
    + Pasteur added "Materials and Methods" sections to his journal articles
- Modern scientific movements
    + Structural and protein biology (1980s)
    + Political science (1990s)
    + Genomics and genetics (2000s)
    + Statistics (2010s)

# Reproducible research =<br /> "post paper and all supporting materials"
- Reproducible research has many definitions
- In this presentation, "reproducible research" means submitting _at minimum_:
    + the paper
    + all code and data to reproduce results
    + README files describing code, data
- Minimum standard chosen to minimize cost
- Can be helpful to do more

# Most computational science <br /> **not** reproducible currently
- People do not post the code with their work
- Even reproducible research gurus have published papers without code
- They recount those experiences as cautionary tales

# Lack of reproducibility causes problems
- Anecdotes of Professor David Donoho are typical:
    + Which version of code goes with paper?
    + Where's the bug: method or implementation?
    + Easy to forget research set aside for months
    + Results can depend on "magic parameter settings"
    + New person in lab can't repeat what former grad student's work
- Reproducible research helps avoid these issues

# Doing reproducible research has benefits
- Reproducible research tends to be cited more
- In addition, reproducible research has the following anecdotal benefits:
    + Enhanced knowledge transfer 
    + Easier to resume projects after hiatus
    + Easier to train new researchers
    + Decreases time to revision
    + Attracts collaborators
    + Decreases debugging time

<!--Transition from Point 1 to Point 2-->

# Reaping benefits of reproducible research <br /> reduces to habits and practices
- Basic principles of reproducibility in computational science like those in experimental sciences
- Keep good records
    + Experimentalists and theoreticians use lab notebooks
    + Computational scientists should use notebooks and version control
- Include these records as supplemental material to papers
    + Experimentalists: include data and analyses
    + Theoreticians: include proofs and derivations
    + Computational scientists: include code, data, proofs, derivations
- Use tests to guard against error
    + Experimentalists use positive and negative controls
    + Computational scientists: test codes as much as possible
    
<!--Point 2: Tools and services to do reproducible research at reasonable cost-->

# Tools enable adopting these practices <br /> at reasonable cost
- Automating habits with tools and services reduces their cognitive burden
    + Version control systems
    + Repository hosting web sites
    + Unit testing frameworks
    + Build systems
    + Figure, data, preprint archives
- Examples, payoffs, and costs (conservative estimates) given

# Version control systems <br /> track all code changes in repositories
- **Examples**: Git, Mercurial, SVN, CVS, etc.
- **Payoffs**
    + Eases collaboration
    + Can track changes in any file type, and who made them
    + Can revert file to any point in its tracked history
- **Costs**
    + Need 2-3 days of use on your code, papers, presentations to get basics
    + SVN, CVS require their own server (Git & Mercurial don't)
    + Can take a long time to learn intricacies (much like LaTeX, MATLAB)
  
# Repository hosting sites available
- **Examples**: GitHub, BitBucket, Google Code, SourceForge, etc.
- **Payoffs**:
    + Eases collaboration
    + Free backup of project files
    + Publicity
- **Costs**:
    + 1 hr to register, sync up files
    + Limiting access costs money, unless:
        - BitBucket + academic e-mail address
        - GitHub + academic e-mail address + special permission
    + Space is limited (usually 1 GB or so)
    + Large data sets or binaries: SourceForge or data archive
    + Limited by terms of service
  
# Unit testing frameworks <br /> ease debugging, verification
- **Examples**: MATLAB xUnit, Python Nose, GoogleTest, etc.
- **Payoffs**:
    + Automates verification
    + Easier to write tests
    + Reduce software development time costs; get papers faster
- **Costs**:
    + 1-2 days to work through examples
    + Each language has its own framework
    + Most frameworks use xUnit standard

# Build systems automate <br /> running tests, generating results
- **Examples**: GNU make, SCons, CMake, GNU autotools, etc.
- **Payoffs**:
    + Build source code, test, run, all in one command
    + Build presentations, papers from LaTeX (or other) source
    + Avoid mistake-prone long chains of commands
- **Costs**:
    + 1-3 days to work through basic examples
    + Can take a long time to master
    + Tough to debug

# Services host and track pre-prints, data, etc.
- **Examples**:
    + _Pre-prints_: arXiv, Optimization Online, FigShare, etc.
    + _Data, Figures, Presentations_: FigShare, DataDryad, ORCID, etc.
- **Payoffs**:
    + Free space for hosting
    + Assignment of DOIs
    + Tracking citation metrics (mainly FigShare)
- **Costs**:
    + Registration: 1 hour
    + License restrictions placed on posted material
    + Limited or no private storage space

<!--Transition from Point 2 to Point 3-->

# Tools reduce costs of reproducible research
- Recall that reproducibility of work yields:
    + **Verification**: easier debug
    + **Transparency**: increased citation count, broader impact
    + **Efficiency**: de-duplication of effort
- These benefits map to tools as follows:
    + **Verification**: download hosted source code, build it, run tests
    + **Transparency**: hosting sites store research record, tracked
    with FigShare & ORCID
    + **Efficiency**:
        - Version control enables collaborating, experimenting, reverting changes
        - Testing frameworks reduce time spent debugging
        - Can reuse reproducible research

# Despite reducing costs, challenges remain
- Tools make it easier to do reproducible research, but...
- Reproducible research is uncommon, and resisted
- Policies requiring reproducibility have not been effective
- Technical challenges still exist

<!--Point 3: Challenges still exist-->

# Reproducible research practices: <br /> a solution _resisted_
- Most computational science research is not done reproducibly
    + Viewed as costing too much
    + Cost-benefit tradeoff considered unfavorable
- These views **shift costs from research _producers_ to research _consumers_**
    + Consumers re-implement, then check
    + Computational science community reputation also suffers
    + Contradicts the tradition that burden of proof is on producers
- Unreproducible research is a **false economy**
    + Producer savings: time spent making research reproducible
    + Consumer costs: time spent making _others'_ research reproducible
    + Producer costs: citations, reputation, wasted time redoing work
        
# Policies requiring reproducibility <br /> have not been effective
- Some journals and funding agencies require some form of reproducibility
    + PLoS, _Science_, others require sharing of code and data
    + NIH, NSF, DOE require sharing of data
- Despite these policies, researchers still don't share data or code <!--Provide examples here-->
- Even if code and data are provided, research still may not be reproducible <!--Provide examples here-->
- Policies are not enforced with penalties, probably why they are ineffective
- Better policies must align community and personal incentives
 
# Technical challenges also still exist
- Reproducing big data and supercomputing research is hard
    + Scarcity of resources (big storage, big supercomputers)
    + Best practice: cache intermediate data and results
- Making sure that source code works on other people's computers is hard
    + Installing software is tedious and hard
    + To run someone's source code, need their whole development environment
    + Best practices: use virtual machines, provisioning software, reproducibility software
- Keeping detailed enough records -- provenance -- is hard
    + Provenance software: VisTrails, Madagascar, Sumatra, etc.
    + Electronic notebooks like Carl Boettiger's tackle day-to-day record-keeping

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

<!--"How to succeed in business without really trying" promotional poster goes here-->
<!-- Notes: 500px by 500px is too big; so is 799px by 354px, but 150px by 200px works -->

<!--![Promotional poster for "How to succeed in business without really trying"](how-to-succeed-150x200.jpg)\ -->

<!--Acknowledgments-->

# Acknowledgments
- Victoria Stodden (posted a literature review)
- Jaydeep Bardhan, Ahmed E. Ismail, and friends (helpful discussions)
- Matt McNenly, Dan Flowers, Russell Whitesides, and LLNL colleagues (helpful discussions)
- Lawrence Livermore National Laboratory (funding via postdoc account)
- Gurpreet Singh (program manager)
