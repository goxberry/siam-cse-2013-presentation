% How to succeed in reproducible research without really trying
% Dr. Geoffrey Oxberry
% Lawrence Livermore National Laboratory

# How to succeed in reproducible research <br /> without really trying

<!--Pandoc metadata after percentages, before first non-title slide: 
<!--Title-->
<!--Author(s) separated by semicolons or white space-->
<!--Date (replaced here by affiliation for now)-->
<!--"How to succeed in business without really trying" promotional poster goes in this slide-->
<!-- Notes: 500px by 500px is too big for Beamer; so is 799px by 354px, but 150px by 200px works -->
<!-- However, 150px by 200px is small for S5 and HTML-based slides -->

![Promotional poster for "How to succeed in business without really trying"](how-to-succeed-150x200.jpg)\ 

<!--Establish need -->

# Computational science has culture problems
- **Lack of verification**
    + "Is it a bug in my method, or its dependencies?"
    + "Is the bug in my method, or its implementation?"
- **Lack of transparency**
    + Can publish unreproducible research; tough for others to debug
    + Selective use of case studies can distort results
- **Efficiency**
    + Developing new research harder if dependencies implemented from scratch
    + Revising our own papers harder without reproducibility and good record-keeping

<!--Task-->

# We can fix these problems... <br /> We have the technology

<!--Six million dollar man picture and reference-->

![Opening credits image of "The Six Million Dollar Man"](six-million-dollar-man-220x172.jpg)\ 

<!--Main message-->

# Reproducible research practices: a solution
- Reproducibility of work yields:
    + **Verification**: easier to find and fix bugs
    + **Transparency**: leads increased citation count, broader impact
    + **Efficiency**: via de-duplication of effort
- In this talk, I am ignoring restrictions on sharing research due to
    + Classified or sensitive material
    + Nondisclosure agreements
    + Software licensing issues
- Partial reproducibility may still be possible in these situations
    + Requires working with stakeholders
    + Content of this talk still applies
  
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

# Idea of "reproducibility" has long history
- Mathematical proof is one form of reproducibility
    + Originated with Greek mathematicians (_ca._ 400 BC)
    + More modern rigorous proof dates to around 1800s
- Notable experimental examples
    + Galileo (1620s) built several copies of his telescope so that others could verify his results
    + Pasteur added "Materials and Methods" sections to his journal articles
- Modern scientific movements
    + Structural and protein biology (1980s)
    + Political science (1990s)
    + Genomics and genetics (2000s)
    + Statistics (2010s)

# Reproducible research means <br /> "post paper and all supporting materials"
- Reproducible research has many definitions
- In this presentation, "reproducible research" means submitting _at minimum_:
    + the paper
    + all code to reproduce results, figures, and tables
    + all of the data to reproduce results, figures, and tables
    + README files on how to execute code, what data represents
- Minimum standard chosen to make reproducibility cost as little as possible
- Beyond the minimum listed, it can be helpful to have:
    + clean, well-documented code
    + tests of the code, example test cases
    + executable code
    + executable tests and examples
    + code that runs on multiple platforms

# Most computational science <br /> is **not** reproducible currently
- People do not post the code with their work
    + My first paper in graduate school did not include code
    + Code does not accompany many articles in SIAM journals
- Even reproducible research advocates cite cases where they published research without code
- These experiences are then recounted as cautionary tales

# Lack of reproducibility causes problems
- Anecdotes of Professor David Donoho are typical:
    + Which version of the research codes generated results for a paper?
    + Are research obstacles encountered due to a bad method or a bad implementation of the method?
    + It's easy to forget what you've done after not working on it for a year
    + Results can depend on "magic parameter settings" that are not recorded, and thus forgotten
    + New person in lab cannot replicate what former grad student has done
- Reproducible research helps avoid these issues

# Doing reproducible research has benefits
- Reproducible research tends to be cited more
- In addition, reproducible research has the following anecdotal benefits:
    + Enhanced knowledge transfer due to more complete and immediately useful research record
    + Easier to pick up where you leave off in a project, and remember what you did
    + Easier to train new graduate students and postdocs in a lab (or in classes)
    + Decreases time to revise papers and PhD theses
    + Can attract collaborators
    + Decreases time needed to find problems in code and algorithms

<!--Transition from Point 1 to Point 2-->

# Reaping benefits of reproducible research <br /> reduces to habits and practices
- Basic principles of reproducibility in computational science are like those in experimental sciences
- Keep good records
    + Experimentalists and theoreticians use lab notebooks
    + Computational scientists should use notebooks and version control
- Include these records as supplemental material to papers
    + Experimentalists include data and statistical analyses as supplemental material
    + Theoreticians include mathematical proofs and derivations
    + Computational scientists should include code, data, and any proofs or derivations
- Use tests to guard against error
    + Experimentalists use positive and negative controls
    + Computational scientists should test their codes as much as reasonably possible
    
<!--Point 2: Tools and services to do reproducible research at reasonable cost-->

# Tools enable adopting these practices <br /> at reasonable cost
- Automating habits with tools and services reduces their cognitive burden
    + Version control systems track code changes in repositories
    + Web sites exist that host these repositories
    + Unit testing frameworks ease debugging, verification
    + Build systems automate running tests, generating results
    + Services exist to host and track non-software research outputs
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
  
# Web sites exist to host <br /> version control repositories
- **Examples**: GitHub, BitBucket, Google Code, SourceForge, etc.
- **Payoffs**:
    + Eases collaboration
    + Free backup of project files in cloud
- **Costs**:
    + 1 hour to register, sync up files
    + Limiting access costs money, unless:
        - you have an academic e-mail address (even alumni): use BitBucket
        - you are an academic and contact GitHub
    + Space is limited (usually 1 GB or so)
    + Not really for large data sets or binaries (except SourceForge)
    + Limited by terms of service (example: SourceForge requires open source)
  
# Unit testing frameworks <br /> ease debugging, verification
- **Examples**: MATLAB xUnit, Python Nose, GoogleTest, etc.
- **Payoffs**:
    + Automates the testing of code; use for verification!
    + Reduces amount of boilerplate code needed for testing
    + Shown to reduce software development time costs; get papers faster
- **Costs**:
    + 1-2 days to work through examples
    + Each language has its own framework...
    + ...but most frameworks look very similar (follow xUnit standard)

# Build systems automate <br /> running tests, generating results
- **Examples**: GNU make, SCons, CMake, GNU autotools, etc.
- **Payoffs**:
    + Build source code, test, and run, all in one command
    + Can also build presentations from LaTeX (or other) source
    + Avoid mistake-prone long chains of commands
- **Costs**:
    + 1-3 days to work through basic examples
    + Can take a long time to master
    + Tough to debug

# Services exist to host and track <br /> non-software research outputs
- **Examples**:
    + _Pre-prints_: arXiv, Optimization Online, FigShare, etc.
    + _Data, Figures, Presentations_: FigShare, DataDryad, ORCID, etc.
- **Payoffs**:
    + Free space for hosting
    + Assignment of Uniform Research Identifiers, useful for citing research outputs
    + Helps with tracking citation metrics for posted material (mainly FigShare)
- **Costs**:
    + Most services: registration requires 1 hour
    + License restrictions may be placed on posted material (like CC-BY, or CC-0)
    + Limited or no private storage space

<!--Transition from Point 2 to Point 3-->

# Tools reduce costs of reproducible research
- Recall that reproducibility of work yields:
    + **Verification**: easier to find and fix bugs
    + **Transparency**: leads to increased citation count, broader impact
    + **Efficiency**: via de-duplication of effort
- These benefits map to tools as follows:
    + **Verification**: download hosted source code, build it, run tests
    + **Transparency**:
        - transparent research record downloaded from hosting sites
        - services like FigShare and ORCID enable and track citation of research outputs
    + **Efficiency**:
        - Version control makes it easier to collaborate, experiment, undo changes
        - Testing frameworks reduces development time and time spend debugging
        - Readers of papers need not re-implement reproducible research from scratch

# Despite reducing costs, challenges remain
- Tools make it easier to do reproducible research, but...
- Reproducible research is uncommon, and resisted
- Policies requiring reproducibility have not been effective
- Technical challenges still exist

<!--Point 3: Challenges still exist-->

# Reproducible research practices: <br /> a solution _resisted_
- Most computational science research is not done reproducibly
    + Viewed as costing too much (time, money, resources)
    + Benefits viewed as too little for costs
- These views **shift costs from research _producers_ to research _consumers_**
    + Consumers have to re-implement, then verify accuracy and credibility
    + Computational science community reputation also suffers
    + Contradicts the tradition that burden of proof is on producers
- Unreproducible research ends up being a **false economy**
    + Producer savings: time spent making research reproducible
    + Consumer costs: time spent making _others_ research reproducible
    + Producer costs:
        - citations and collaborations; research becomes less trustworthy, comprehensible
        - bookkeeping: time spent matching version of code to figures in paper (if you can!)
        - new group members redo existing work
        
# Policies requiring reproducibility <br /> have not been effective
- Some journals and funding agencies require some form of reproducibility
    + PLoS, _Science_, and others require sharing of code and data
    + NIH, NSF, DOE require sharing of data
- Despite these policies, researchers still don't share data or code <!--Provide examples here-->
- Even if code and data are provided, research still may not be reproducible <!--Provide examples here-->
- These policies are not enforced with penalties, which may be why they are ineffective
- Opportunities exist to craft better policies, align community and personal incentives
 
# Technical challenges also still exist
- Reproducing big data and supercomputing research is hard
    + Obstacles are scarcity of resources (large storage, large supercomputers)
    + Best practices: cache intermediate data and results; use independent teams on same resources
- Making sure that source code works on other people's computers is hard
    + Installing software is time-consuming and fragile
    + To run someone's source code, need their whole development environment
    + Best practices: use virtual machines, provisioning software, reproducibility software
- Keeping detailed enough records -- provenance -- is hard
    + Many software packages tackle this problem: VisTrails, Madagascar, Sumatra, etc.
    + Electronic notebooks, such as Carl Boettiger's, tackle day-to-day record-keeping

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

<!--"How to succeed in business without really trying" promotional poster goes here-->
<!-- Notes: 500px by 500px is too big; so is 799px by 354px, but 150px by 200px works -->

![Promotional poster for "How to succeed in business without really trying"](how-to-succeed-150x200.jpg)\ 

<!--Acknowledgments-->

# Acknowledgments
- Victoria Stodden (posted a literature review)
- Jaydeep Bardhan, Ahmed E. Ismail, and friends (helpful discussions)
- Matt McNenly, Dan Flowers, Russell Whitesides, and LLNL colleagues (helpful discussions)
- Lawrence Livermore National Laboratory (funding via postdoc account)
