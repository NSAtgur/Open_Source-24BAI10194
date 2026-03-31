# The Open Source Audit: Git

**Course:** Open Source Software (NGMC) | VIT Bhopal University | AY 2025-26
**Student:** Nishant Shriram Atgur | Registration No. 24BAI10194
**License:** GNU General Public License v2.0
**Submission Date:** 24th March 2026

---

## Table of Contents

- [What's This Project About?](#whats-this-project-about)
- [What's Inside the Report?](#whats-inside-the-report)
- [The Shell Scripts](#the-shell-scripts)
- [Before You Run Anything](#before-you-run-anything)
- [How to Run the Scripts](#how-to-run-the-scripts)
- [Project Structure](#project-structure)
- [References](#references)
- [License](#license)

---

## What's This Project About?

This is a full audit of **Git** — the version control system that almost every developer on the planet uses without a second thought. But this project goes beyond just "here's how Git works." It digs into *why* Git matters as a piece of open source software: where it came from, what license governs it, the ethical questions it raises, how it lives on a Linux system, and how it stacks up against its closest proprietary competitor.

The deliverables are two things: a written audit report and five Bash shell scripts that show real, hands-on Linux and scripting skills. Think of the scripts as the practical side of everything the report argues for.

---

## What's Inside the Report?

**1. Origin and History**
Git was born out of a crisis. In 2005, Linus Torvalds and the Linux kernel team lost access to BitKeeper overnight after a licensing dispute. Torvalds responded by writing the first working version of Git himself — in about ten days. The goals were simple but demanding: fast, fully distributed, and cryptographically secure. Those goals stuck. Today, over 93% of professional developers use Git.

**2. The GPL v2 License**
Git is released under the GNU General Public License version 2. This isn't just a legal formality — it's what makes Git *actually* open. GPL v2 gives every user four freedoms: run it for any purpose, study and modify it, redistribute copies, and distribute modified versions. That last freedom comes with a condition: your changes have to stay open too. This is the copyleft clause, and it's what stops someone from quietly forking Git, improving it, and releasing a locked-down proprietary version.

**3. Ethics of Open Source**
Is it ethical to build billion-dollar businesses on software maintained by a community of volunteers? This section takes that question seriously, using GitHub's $7.5 billion acquisition by Microsoft as the central case study. It also argues a broader point: tools that an entire industry depends on shouldn't be owned by any single vendor. Shared infrastructure probably should stay shared.

**4. Git on Linux**
This section gets into the nuts and bolts — how Git installs across major Linux distributions, what its directory structure looks like, how it handles user permissions using the principle of least privilege, how it integrates with existing system services without spinning up its own daemon, and how security patches are disclosed and distributed through a fully public and auditable process.

**5. Git vs Perforce Helix Core**
A side-by-side comparison across cost, security, freedom to modify, community governance, handling of large binary files, and vendor lock-in risk. The short version: Git is the right choice for almost any software development workflow. Perforce has a genuine edge only when your entire pipeline revolves around very large binary assets — think game studios working with multi-gigabyte art files.

---

## The Shell Scripts

All five scripts sit right in the root of the repo — no subfolders. Here's what each one does:

**Script 1 — System Identity Report**
Prints a summary of your Linux environment: distro name, kernel version, architecture, hostname, logged-in user, uptime, and current date/time. It also prints the Linux kernel's license and walks through the four GPL freedoms. A good starting point if you want to see basic Bash in action — variables, command substitution, conditional file checks, formatted output.

**Script 2 — FOSS Package Inspector**
Give it a package name and it'll tell you whether it's installed, plus version and maintainer details. It handles both Debian/Ubuntu systems (via `dpkg`) and Fedora/RHEL systems (via `rpm`), and throws in a short philosophy note about the package using a `case` statement. Nice demonstration of if/else logic, command detection, nested conditionals, and pattern matching.

**Script 3 — Disk and Permission Auditor**
Loops through a set of key Linux system directories and prints a formatted table showing disk usage, permissions, owner, and group for each one. It also checks Git-specific installation paths and detects whether the current directory is a Git repository. Good example of Bash arrays, for loops, disk usage commands, and column-aligned output.

**Script 4 — Log File Analyzer**
Takes a log file path and a search keyword as arguments, then reads through the file line by line, counts how many lines match the keyword, calculates the match percentage, and prints the last five matching lines. If the file path is invalid, it'll ask you to try again. Covers while-read loops, command-line arguments, parameter expansion, integer arithmetic, and a do-while style retry mechanism.

**Script 5 — Open Source Manifesto Generator**
An interactive one. It asks you three questions about your relationship with open source, then composes a personalized philosophy statement and saves it to a text file named after your username. Covers interactive input with `read`, input validation, string interpolation, and writing output to files. The most fun of the five.

---

## Before You Run Anything

You'll need:

- A Linux system — Ubuntu, Debian, Fedora, Arch, or openSUSE all work fine
- A Bash shell (it's almost certainly already there)
- Standard core utilities: `grep`, `awk`, `sed`, `df`, `ls`, `stat`, `uptime`, `whoami`, `date`

No extra packages to install. If you're on a reasonably modern Linux system, you're good to go.

---

## How to Run the Scripts

Start by cloning the repo and stepping into it:

```bash
git clone -b main https://github.com/NSAtgur/Open_Source-24BAI10194.git
cd Open_Source-24BAI10194
```

Then make the scripts executable:

```bash
chmod +x *.sh
```

Then run whichever script you want:

```bash
# System identity and license info
bash script1_system_identity.sh

# Inspect a package — pass the package name as an argument
bash script2_package_inspector.sh git

# Audit system directories and Git paths
bash script3_disk_permission_auditor.sh

# Analyze a log file — pass the file path and a keyword
bash script4_log_analyzer.sh /var/log/syslog "error"

# Run the interactive manifesto generator
bash script5_manifesto_generator.sh
```

Each script has comments at the top explaining what it does and what arguments it expects — worth a quick read before you run it.

---

## Project Structure

```
Open_Source-24BAI10194/
|
|-- script1_system_identity.sh
|-- script2_package_inspector.sh
|-- script3_disk_permission_auditor.sh
|-- script4_log_analyzer.sh
|-- script5_manifesto_generator.sh
|-- project_report.pdf
|-- README.md
|-- LICENSE
```

---

## References

1. GNU Project. *The Free Software Definition.* https://www.gnu.org/philosophy/free-sw.html
2. Open Source Initiative. *The Open Source Definition.* https://opensource.org/osd
3. Raymond, E.S. *The Cathedral and the Bazaar.* http://catb.org/~esr/writings/cathedral-bazaar/
4. Git Source Repository and COPYING file. https://github.com/git/git
5. Software Freedom Conservancy. https://sfconservancy.org/
6. Git Reference Manual. https://git-scm.com/docs
7. SPDX License List. https://spdx.org/licenses/
8. Shotts, W. *The Linux Command Line.* https://linuxcommand.org
9. GNU Bash Manual. https://www.gnu.org/software/bash/manual/
10. Stack Overflow Developer Survey 2023. https://survey.stackoverflow.co/2023/

---

## License

All shell scripts and report content in this project are licensed under the **GNU General Public License v2.0**.

Full license text: https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html

---

*VIT Bhopal University | School of Computer Science and Engineering | Open Source Software (NGMC) | AY 2025-26*
