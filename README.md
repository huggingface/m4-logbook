# m4 Training Experiments Logbook

Besides the usual experiment entries at https://github.com/huggingface/m4/ this repo is for detailed logs with reproduction steps and potentially multiple log files, core dumps, graphs, etc. We use it to keep the m4 repo small and not bloated with transient data.

But since there are multiple instructions on how debug and analysis of problems was done these logs can be invaluable to some people.

## What to log

Try to log as much pertinent information as possible, including relevant snippets of log files - so that if 6 months later you need to come back to understand an old experiment all the essential bits of information ideally would be here.

Feel free to organize and name the sub-folders in any way you like, grouping experiments that try to resolve a single issue together and if there multiple sub-experiments giving a common README that helps the reader navigate the multitude of entries and/or showing the critical successful entries. e.g. for a possible approach see [tr_141-hanging](./tr_141-hanging).
