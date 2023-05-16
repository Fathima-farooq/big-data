# commands

```bash
# Feb 20th big data
bsau@bsau-V530-15ICB:~$ cd hadoop-2.9.1
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd sbin

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ ./start-all.sh
This script is Deprecated. Instead use start-dfs.sh and start-yarn.sh
Starting namenodes on [localhost]
localhost: starting namenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-namenode-bsau-V530-15ICB.out
localhost: starting datanode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-datanode-bsau-V530-15ICB.out
Starting secondary namenodes [0.0.0.0]
0.0.0.0: starting secondarynamenode, logging to /home/bsau/hadoop-2.9.1/logs/hadoop-bsau-secondarynamenode-bsau-V530-15ICB.out
starting yarn daemons
starting resourcemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-resourcemanager-bsau-V530-15ICB.out
localhost: starting nodemanager, logging to /home/bsau/hadoop-2.9.1/logs/yarn-bsau-nodemanager-bsau-V530-15ICB.out

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ jps
5010 ResourceManager
4451 NameNode
4645 DataNode
4860 SecondaryNameNode
8989 Jps
5166 NodeManager

bsau@bsau-V530-15ICB:~/hadoop-2.9.1/sbin$ cd ..
bsau@bsau-V530-15ICB:~/hadoop-2.9.1$ cd bin
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ nano map.py
------------------------------------------------------------------------------
mapper code | ctrl + x - Y - Enter
------------------------------------------------------------------------------
#!/usr/bin/env python
"""mapper.py"""

import sys

# input comes from STDIN (standard input)
for line in sys.stdin:
    # remove leading and trailing whitespace
    line = line.strip()
    # split the line into words
    words = line.split()
    # increase counters
    for word in words:
        # write the results to STDOUT (standard output);
        # what we output here will be the input for the
        # Reduce step, i.e. the input for reducer.py
        #
        # tab-delimited; the trivial word count is 1
        print ('%s\t%s' % (word, 1))
------------------------------------------------------------------------------
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ python3 map.py
sam pam ram sam
sam	1
pam	1
ram	1
sam	1
^Z
[1]+  Stopped                 python3 map.py
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ nano red.py
--------------------------------------------------------------------------------
#!/usr/bin/env python
"""reducer.py"""

from operator import itemgetter
import sys

current_word = None
current_count = 0
word = None
# input comes from STDIN
for line in sys.stdin:
    # remove leading and trailing whitespace
    line = line.strip()

    # parse the input we got from mapper.py
    word, count = line.split('\t', 1)

    # convert count (currently a string) to int
    try:
        count = int(count)
    except ValueError:
        # count was not a number, so silently
        # ignore/discard this line
        continue

    # this IF-switch only works because Hadoop sorts map output
    # by key (here: word) before it is passed to the reducer
    if current_word == word:
        current_count += count
    else:
        if current_word:
            # write result to STDOUT
            print ('%s\t%s' % (current_word, current_count))
        current_count = count
        current_word = word

# do not forget to output the last word if needed!
if current_word == word:
    print ('%s\t%s' % (current_word, current_count))
--------------------------------------------------------------------------------
bsau@bsau-V530-15ICB:~/hadoop-2.9.1/bin$ echo "cat rat mat pat rat" | python3 map.py | sort | python3 red.py
cat	1
mat	1
pat	1
rat	2
-----------------------------------------------------------------------
```