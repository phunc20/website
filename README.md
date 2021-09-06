## Q&A
01. How to examine whether there are people visiting your website?
  - There exist several ways to do this. Here we only introduce a quite standard one --
    Generally, you may be interested in looking into the folder `/var/log/`. Depending on what you use,
    - If you use `nginx`, then check the files under the names of `/var/log/nginx/access.log*`
    - If you use `apache`, then check the files under the names of `/var/log/apache2/access.log*` or `/var/log/httpd/access_log*`
    - The entries in these files will look like
      ```
      79.156.76.89 - - [06/Sep/2021:15:49:56 +0000] "GET /blog/maths/definitions/functions/linear/norm.jl.html HTTP/1.1" 200196079 "https://phunc20.xyz/blog/" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.121 Safari/537.36"
      ```
      One can then combine various Linux commands, e.g. `sed, awk, sort, wc, crontab`, etc. to do whatever one
      may think of doing.
    - It seems that these log files will not record indefinitely, so, if one needs the entire history, one had better
      devise ways (e.g. `crontab`) to automatically or manually save all of them.
