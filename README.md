# OverTheWire---Bandit-completion
Completed 25 levels on OverTheWire Bandit wargame, it has a total of 33 levels, gaining practical hands-on experience with Linux command-line operations, file and directory navigation, file permissions and ownership, text processing utilities, SSH access, compression formats, and basic security concepts.
Level 0 → Level 1

Goal: Find the password stored in a file called readme.

Command Used:
cat readme

Output: Password retrieved successfully

Concept: Logged in using SSH and used the cat command to read a text file from the home directory.

Level 1 → Level 2

Goal: Find the password in a file named -.

Command Used:
cat ./-

Output: Password retrieved successfully

Concept: Filenames beginning with - are treated as options. Using ./ forces Linux to treat it as a file.

Level 2 → Level 3

Goal: Find the password in a file named spaces in this filename.

Command Used:
cat "spaces in this filename"

Output: Password retrieved successfully

Concept: Filenames containing spaces must be escaped or wrapped in quotes.

Level 3 → Level 4

Goal: Find the password in a hidden file inside the inhere directory.

Command Used:
ls -a inhere/
cat inhere/.hidden

Output: Password retrieved successfully

Concept: Files starting with . are hidden. The -a flag lists hidden files.

Level 4 → Level 5

Goal: Find the password in the only human-readable file.

Command Used:
file ./*
cat ./-file07

Output: Password retrieved successfully

Concept: The file command identifies file types. ./ avoids option misinterpretation.

Level 5 → Level 6

Goal: Find a file with specific size and permissions.

Command Used:
find . -type f -size 1033c ! -executable

Output: Password retrieved successfully

Concept: The find command filters files by size, type, and permissions.

Level 6 → Level 7

Goal: Find a file owned by a specific user and group.

Command Used:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

Output: Password retrieved successfully

Concept: Searching system-wide requires permission filtering and error redirection.

Level 7 → Level 8

Goal: Find the password next to the word “millionth”.

Command Used:
grep millionth data.txt

Output: Password retrieved successfully

Concept: grep searches for specific patterns inside files.

Level 8 → Level 9

Goal: Find the unique line.

Command Used:
sort data.txt | uniq -u

Output: Password retrieved successfully

Concept: Sorting is required before using uniq to isolate unique entries.

Level 9 → Level 10

Goal: Find the password in human-readable strings.

Command Used:
strings data.txt | grep =

Output: Password retrieved successfully

Concept: Binary files can contain readable strings extracted using strings.

Level 10 → Level 11

Goal: Decode a Base64 encoded password.

Command Used:
base64 -d data.txt

Output: Password retrieved successfully

Concept: Base64 is a common encoding format for text data.

Level 11 → Level 12

Goal: Decode ROT13 encrypted text.

Command Used:
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

Output: Password retrieved successfully

Concept: ROT13 is a simple substitution cipher.

Level 12 → Level 13

Goal: Decompress multiple compressed files.

Command Used:
xxd -r data.txt > file
Then used gzip, bzip2, and tar.

Output: Password retrieved successfully

Concept: Hex dumps and nested compression formats.

Level 13 → Level 14

Goal: Use SSH private key to login.

Command Used:
ssh -i sshkey.private bandit14@localhost

Output: Logged in successfully

Concept: SSH authentication using private keys.

Level 14 → Level 15

Goal: Retrieve password via localhost service.

Command Used:
nc localhost 30000

Output: Password retrieved successfully

Concept: Basic networking using Netcat.

Level 15 → Level 16

Goal: Use SSL encryption to retrieve password.

Command Used:
openssl s_client -connect localhost:30001

Output: Password retrieved successfully

Concept: Secure communication using SSL/TLS.

Level 16 → Level 17

Goal: Find open SSL ports.

Command Used:
nmap localhost
openssl s_client -connect localhost:31790

Output: Password retrieved successfully

Concept: Port scanning and encrypted services.

Level 17 → Level 18

Goal: Compare files to find differences.

Command Used:
diff passwords.old passwords.new

Output: Password retrieved successfully

Concept: File comparison using diff.

Level 18 → Level 19

Goal: Read a file despite forced logout.

Command Used:
ssh bandit18@bandit.labs.overthewire.org "cat readme"

Output: Password retrieved successfully

Concept: Executing commands remotely via SSH.

Level 19 → Level 20

Goal: Use a SUID binary.

Command Used:
./bandit20-do cat /etc/bandit_pass/bandit20

Output: Password retrieved successfully

Concept: Set-UID binaries run with owner privileges.

Level 20 → Level 21

Goal: Exploit a listening service.

Command Used:
nc -lvp 1234
./suconnect 1234

Output: Password retrieved successfully

Concept: Client-server interaction using Netcat.

Level 21 → Level 22

Goal: Analyze cron jobs.

Command Used:
cat /etc/cron.d/*

Output: Password retrieved successfully

Concept: Scheduled jobs can expose credentials.

Level 22 → Level 23

Goal: Understand script-generated filenames.

Command Used:
cat /usr/bin/cronjob_bandit23.sh

Output: Password retrieved successfully

Concept: Predictable temporary file creation.

Level 23 → Level 24

Goal: Exploit writable cron script.

Command Used:
Created a script to copy the password.

Output: Password retrieved successfully

Concept: Privilege escalation via cron jobs.

Level 24 → Level 25

Goal: Brute force a 4-digit PIN.

Command Used:
Loop with nc.

Output: Password retrieved successfully

Concept: Automation and brute forcing.

Level 25 → Level 26

Goal: Escape restricted shell.

Command Used:
Used vim shell escape.

Output: Password retrieved successfully

Concept: Escaping restricted environments.

Level 26 → Level 27

Goal: Execute a binary with SUID.

Command Used:
./bandit27-do

Output: Password retrieved successfully

Concept: Privilege execution.

Level 27 → Level 28

Goal: Clone a Git repository.

Command Used:
git clone ssh://bandit27-git@localhost/...

Output: Password retrieved successfully

Concept: Git over SSH.

Level 28 → Level 29

Goal: Find hidden data in Git history.

Command Used:
git log
git checkout

Output: Password retrieved successfully

Concept: Git commits and version control.

Level 29 → Level 30

Goal: Inspect Git branches.

Command Used:
git branch -a

Output: Password retrieved successfully

Concept: Branch exploration.

Level 30 → Level 31

Goal: Inspect Git tags.

Command Used:
git tag
git show

Output: Password retrieved successfully

Concept: Git tagging.

Level 31 → Level 32

Goal: Bypass Git push restrictions.

Command Used:
Removed pre-commit hooks.

Output: Password retrieved successfully

Concept: Git hooks.

Level 32 → Level 33

Goal: Escape an uppercase-only shell.

Command Used:
Used $0 and shell tricks.

Output: Password retrieved successfully

Concept: Shell behavior and environment variables
