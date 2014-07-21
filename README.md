bcbio-test-data
===============
This contains test data for bcbio-nextgen. Small files are just kept in the respsitory normally. Large files are 
annexed using git-annex. To install git annex:

```
brew install git-annex
```

To add a new file that is not large, just use git normally and push to this repository. For larger files,
host the file somewhere on the web, add it to the annex and push the git-annex branch:

```
git annex addurl url-to-file --file=filename
git annex drop filename
git push origin master git-annex
```

You'll want to give it a filename because otherwise the filename is set as a long string containing a mangled version
of the URL. I think you want to drop the file at the end so your local machine is not set up to be an annex by default.
