# Log Analysis

# Command Breakdowns

1. sort
   
Purpose: Arranges lines of text in a file alphabetically or numerically.

Basic Usage:

```
sort filename.txt

```

Options:
-r: Reverses the order of sorting.

-n: Sorts numerically (useful for numbers).

-u: Outputs only unique lines.

-k: Sorts by a specific column or "key."


Examples:

Reverse Sorting:

```
sort -r filename.txt

```
Sorting by Second Column:

```
sort -k 2 filename.txt

```

4. uniq

Purpose: Filters out consecutive duplicate lines, usually used after sort.

Basic Usage:

```
uniq filename.txt

```

Options:
-c: Counts each unique line’s occurrences.

-d: Shows only duplicate lines.

-u: Shows only unique lines.


Examples:

Counting Duplicates:


```

sort filename.txt | uniq -c

```

Sorts first (required for uniq to work correctly), then counts each unique line.

Showing Only Duplicates:

```

sort filename.txt | uniq -d

```

7. grep
   
Purpose: Searches for text patterns in files.

Basic Usage:


```

grep "pattern" filename.txt

```

Options:
-i: Ignores case, matching both uppercase and lowercase.

-o: Only shows the matching parts of each line, not the whole line.

-v: Inverts the match, showing lines that don’t match the pattern.

-c: Counts the number of lines that match.

-r: Recursively searches all files in a directory.

-A n: Shows n lines after each match.

-B n: Shows n lines before each match.

-E (or egrep): Uses extended regular expressions for complex patterns.

Examples:

Case-Insensitive Search:


```

grep -i "error" filename.txt

```

Finds lines with "error," ignoring case.

Count Matches:

```

grep -c "pattern" filename.txt

```

Counts how many times "pattern" appears.

Show Matching Parts Only:

```

grep -o "pattern" filename.txt

```

Only shows "pattern" without the rest of the line.

Recursive Search in a Directory:


```

grep -r "error" /path/to/directory

```

Searches for "error" in all files within the directory.

Extended Regex with grep -E:


```

grep -E "error|warning" filename.txt

```

Finds lines containing "error" or "warning."

9. awk
     
Purpose: Processes and manipulates text, especially by breaking it into fields (columns).

Basic Usage:

```

awk '{print $1}' filename.txt

```

Options:
-F "delimiter": Sets a custom delimiter to separate fields.

{print $n}: Prints a specific field ($1 is the first field, $2 is the second, etc.).

Examples:

Extracting the First Field:

```

awk '{print $1}' filename.txt

```

Prints the first column of each line.

Custom Delimiter:

```

awk -F "," '{print $2}' filename.csv

```

Uses a comma as the delimiter and prints the second field.

Filtering and Printing Fields:

```

awk '$3 == 200 {print $1, $4}' access.log

```

Filters lines where the third field is 200 and prints the first and fourth fields.

12. cut
    
Purpose: Cuts out specific fields from each line, commonly used to extract columns in structured text.

Basic Usage:

```

cut -d "delimiter" -f field_number filename.txt

```
Options:
-d "delimiter": Defines the delimiter, like a space, comma, or tab.

-f field_number: Specifies which field(s) to extract.

Examples:

Extracting a Single Field:

```

cut -d " " -f 1 filename.txt

```

Uses a space as the delimiter and extracts the first field.

Extracting Multiple Fields:


```

cut -d "," -f 1,3 filename.csv

```

Uses a comma as the delimiter and extracts the first and third fields.

Combined Command Example

Here’s a practical example of combining these commands for log analysis:

```

cat access.log | awk -F '"' '{print $2}' | cut -d " " -f 2 | sort | uniq -c | sort -rn

```
cat access.log: Outputs the entire access.log file.

awk -F '"' '{print $2}': Splits each line by double quotes, selecting the middle section with HTTP method and path.

cut -d " " -f 2: Uses space as a delimiter to extract the second field (the HTTP status code).

sort: Sorts the list of status codes.

uniq -c: Counts each unique status code.

sort -rn: Sorts by frequency in reverse numerical order, showing the most common status codes at the top.

# SQL

[SQLite Viewer](https://inloop.github.io/sqlite-viewer/)
