# regex

Construct a regular expression that matches:
1. at least one a followed by 2 to 5 b’s followed by a c.
2. one or more of backslashes, ‘\’, followed by one or more plus signs, ‘+’.
3. any potential C++ identifier name that starts with a letter or underscore but may contain any number of letters, underscores, and/or digits (all letters may be upper or lower case).
    For example, your regular expression should match the following text strings:  “_”, “x2”, and “This_is_valid”  It should not match these text strings: “2days”, or “invalid_variable%”.
4. any date of the form:  mm/dd/yyyy, where mm and dd may be 1 or 2 digit numbers, but yyyy always contains 4 digits and the slashes are required. The mm field must be a value that corresponds to a valid month (1 through 12); however, your expression should allow for an optional leading zero, for example ‘05’.  The dd field must be a value that corresponds to a valid date (1 through 31).  Again, your expression should allow for an optional leading zero, such as ‘03’.  The first two digits in the yyyy field must either be a ‘19’ or a ‘20’.
    For example, your expression should match the following dates: 05/03/1952, 10/3/2004, and 02/31/1900
    It should not match these dates: 1/32/2006, 13/13/1313, 1/0/2006, 11/3/04, 3/3/3000.
5. any word that contains each of the five vowels (a, e, i, o, and u) once and in alphabetic order.  There may be any number of consonants in the word; however, there should be no other vowels other than the 5 listed above.  For example, the word “sacrilegious” should not match because, although it contains the five vowels in alphabetical order, there is an extra ‘i’ vowel located between the ‘a’ and the ‘e’.  Hyphenated words are not allowed.  In fact, your regular expression should not match any ‘word’ that contains any character other than the upper and lower case letters.  You may test your regular expression by entering and running the Perl program named wordsearch on TAZ, which asks for a regular expression and then uses it to search for matching words in an English dictionary.  However, only the regular expression should be turned in with this assignment.


The Perl script, wordsearch, is available on Easel.  If you prefer to type in the program yourself, the code is listed here:
#! /usr/bin/perl -w
 
$wordfile = $ARGV[0] || "/usr/share/dict/words";
open(DICT,$wordfile) || die "dictionary not found.";
 
print "Regular Expression? ";
$regexpr = <STDIN>;
chomp($regexpr);
 
while ($word=<DICT>)
{
   chomp($word);
   if ($word =~ /$regexpr/) {print "$word\n";}
}
close(DICT);
