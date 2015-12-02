This is a smaller-out, parallel-focused version of Pricetx's script.

The easiest way to call this script from a bash shell is:
ruby xiv_stats.rb <Chunk_start> <Chunk_end> <database number> &

You can run multiple instances of the script to process the
Lodestone in parallel.  Increasing the number of databases
seems to alleviate the locking issue the original script had
above a certain number of instances on the same database.

By running multiple instances of the effectively unmodified script,
I was able to get the time down to around 80 hours on a modest VPS,
using 30 500k ID chunks.

With the modifications for a database append, I was able to run
six separate databases, with 75 175k ID chunks, and take less than
thirty hours to compile the data.  In theory, this can go higher.

This version also cuts out the parts of the script that I do not need
for my XIV_Census package.

The original version of the script can be found at:
https://github.com/Pricetx/XIVStats