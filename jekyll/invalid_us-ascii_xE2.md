# Invalid US-ASCII character "\xE2". 
If you get the following error when using jekyll, this is an encoding problem.  

```
$ bundle exec jekyll serve -H 127.0.0.1 -P8080
Configuration file: /home/kssim/kssim.github.io/_config.yml
            Source: /home/kssim/kssim.github.io
       Destination: /home/kssim/kssim.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
  Conversion error: Jekyll::Converters::Scss encountered an error while converting 'assets/css/style.scss':
                    Invalid US-ASCII character "\xE2" on line 5
jekyll 3.6.2 | Error:  Invalid US-ASCII character "\xE2" on line 5
```

To fix this, change the encoding setting in the shell as shown below.  

```
$ export LC_ALL=en_US.utf-8
$ export LANG=en_US.utf-8
```
