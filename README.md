# IRE 2023: Don't be afraid of the command line (Macs)

### 🔗 [bit.ly/ire23-cli](https://bit.ly/ire23-cli)

This repo contains materials for a one-hour workshop at the IRE 2023 conference in Orlando on using the command line on a Mac.

The session is scheduled for Saturday, June 24, from 3-4 p.m. in room `Coral A` on the first floor.

Also check out "Finding needles in haystacks," an introduction to using the command-line software `csvmatch`, immediately following this class in the same room.

### Course outline
- What, would you say, are we doing here? Some command-line workflow pros and cons
- What if you work on a PC?
    - [See this comparison chart](https://docs.google.com/document/d/1zAzcXbTCt4JvS_P2dZNefsmNH6aMBOQ5MENGTo-Ujv8/edit?usp=sharing)
    - My recommendation: [Activate the Windows subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install)
    - You can also use [Powershell](https://learn.microsoft.com/en-us/powershell) or similar
- Get yourself a good text editor like [Sublime](https://www.sublimetext.com/) or [VS Code](https://code.visualstudio.com/)
- Introduction to `Terminal`
- Navigating the file system starts at home: `~`
- Where am I? `pwd`
- Printing text with `echo`
- Moving around with `cd`
- Using `.` and `..` as you move around
- Using tab completion
- Listing a directory's contents with `ls`
- Using command flags
- Copy, move and rename files: `cp` and `mv`
- Editing your command
    - `Ctrl + a`: Move to the beginning of the line
    - `Ctrl + e`: Move to the end of the line
    - `Ctrl + c`: Stop running process
- Reading files with `cat`
- Making directories with `mkdir`
- Creating files with `touch`
- Opening files or directories with `open`
- Getting a sneak peek at files with `head` and `tail`
- Searching inside files with `grep`
- Piping, redirecting and appending: `|`, `>`, `>>` (can also use `<<` etc.)
- Reading and writing to your clipboard: `pbcopy` and `pbpaste`
- Issuing multiple commands with `&&`
- Counting lines with `wc` (with the `-l` flag to count rows)
- Unzipping archives with `unzip`
- Getting help with `man`
- Using CLI software (installed separately)
    - [`curl`](https://curl.se/) (HTTP client)
    - [`pdftotext`](https://www.xpdfreader.com/index.html) and other `xpdf` tools (working with PDFs)
        - `pdftotext -table kristi-noem-campfin.pdf`
    - [`youtube-dl`](https://youtube-dl.org/) (archiving YouTube videos)
    - [`csvkit`](https://csvkit.readthedocs.io/en/latest/) (working with tabular data files)
        - `in2csv MLB2018.xlsx | head`
        - `in2csv MLB2018.xlsx > mlb2018.csv`
        - `in2csv MLB2018.xlsx | csvcut -c TEAM | sort | uniq`
    - [`csvmatch`](https://github.com/maxharlow/csvmatch) (fuzzy matching between tabular data files)
        - `csvmatch data1.csv data2.csv --fields1 name --fields2 'Person Name'`
    - [`ffmpeg`](https://ffmpeg.org/) (audio and video editing)
    - [`imagemagick`](https://imagemagick.org/index.php) (image manipulation)
    - [`git`](https://git-scm.com/) (version control)
    - [`exiftool`](https://exiftool.org/) (image metadata)
- Running scripts
    - Bash/Zsh (c.f. changing file permissions with [`chmod`](https://en.wikipedia.org/wiki/Chmod#Numerical_permissions))
    - Python
    - Node.js
    - ... etc.
- Working with databases (postgres, sqlite, etc.)
- A more complicated example putting a few things together -- download 2023 Congressional financial disclosure and get some stats: `curl https://disclosures-clerk.house.gov/public_disc/financial-pdfs/2023FD.ZIP > congress_disclosures_2023.zip && unzip congress_disclosures_2023.zip && csvstat -t 2023FD.txt`

### Practice
- Use `youtube-dl` to download a video, but pipe the output to `ffmpeg` to cut all but the first 10 seconds and redirect the output to file
- Use `curl` and `csvkit` to download a file from an open data registry of your choice and cut out just the columns of interest, then write to file ([here's a good collection](https://data.cms.gov/))
- Use `pdftotext` and a good text editor to clean up messy data tables in a PDF (bonus: Use [regular expressions](https://www.regular-expressions.info/) to help clean it up!)

### Highly recommend
- [Oh My Zsh](https://ohmyz.sh/)
- [iTerm2](https://iterm2.com/)
- [A.J. Vicens' command-line tutorial](https://github.com/AJVicens/command-line-for-reporters)
