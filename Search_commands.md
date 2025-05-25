📁 Directory Listing

ls                    # List files in current directory
ls -l                 # Long listing with permissions, size, timestamp
ls -a                 # Include hidden files
ls -lh                # Human-readable sizes
ls -R                 # Recursively list all files
ls -d */              # Show only directories

🔎 File Search with find

find . -name "file.txt"                    # Find file.txt in current dir and subdirs
find / -name "passwd"                      # Find file named 'passwd' starting from root
find /home -iname "*.jpg"                  # Case-insensitive search for .jpg files
find . -type f -name "*.log"               # Find all log files
find . -type d -name "config"              # Find directories named config
find . -type f -empty                      # Find empty files
find . -type d -empty                      # Find empty directories
find . -size +10M                          # Files greater than 10MB
find . -size -1k                           # Files smaller than 1KB
find . -mtime -2                           # Modified in last 2 days
find . -ctime +10                          # Changed more than 10 days ago
find . -user username                      # Files owned by a user
find . -perm 777                           # Files with 777 permissions
find . -exec rm {} \;                      # Find and delete files (⚠️ careful)

🔍 File Search with locate

sudo updatedb                               # Update database (run first)
locate passwd                               # Quick search for files containing "passwd"
locate "*.conf" | grep nginx                # Combine with grep for filtering


🧾 Text Search in Files with grep

grep "root" /etc/passwd                    # Search for 'root' in a file
grep -i "error" *.log                      # Case-insensitive search in log files
grep -r "main()" .                         # Recursively search in all files
grep -Ril "password" /home/user            # Find files containing 'password' (case-insensitive)
grep -n "TODO" *.py                        # Show line numbers with matches
grep -v "DEBUG" log.txt                    # Invert match (show lines not containing DEBUG)

🧠 Advanced Grep Variants

egrep "error|fail|critical" logfile.log    # Multiple patterns
grep -A 3 -B 2 "Error" app.log             # Show 3 lines after and 2 before match

📂 Search Using find + grep Together
find . -type f -name "*.conf" -exec grep "Listen" {} \;   # Search for "Listen" in all .conf files

🕵️ Other Useful Tools
which python                              # Find full path of an executable
whereis bash                              # Locate binary, source, and man page for bash
type ls                                   # Show how command would be interpreted

🧹 Cleaning Up
find . -name "*.tmp" -delete              # Delete all .tmp files

📌 Examples
find / -name "passwords.txt" 2>/dev/null          # Suppress permission errors
grep -R "api_key" ~/projects                      # Search for API keys in codebase
find . -iname "*report*" -type f -mtime -7        # Files containing "report" modified last 7 days
