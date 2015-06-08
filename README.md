# php5.3.10-patch

PHP is vulnerable to a remote denial of service, caused by repeated allocate memory, concatenate string, copy string
and  free memory when PHP parses header areas of body part of HTTP request with multipart/form-data. By sending multiple HTTP
multipart requests to an affected application containing malicious header raea of body part, a remote attacker could exploit
this vulnerability to cause the consumption of CPU resources.

To this problem, the PHP official releases the patch as soon as possible. However, the solution only applies to the versions
higher than PHP5.4, missing the lower versions.

As our company uses the PHP5.3.10, and PHP5.3 is widely usedin a variety of projects , this Vulnerability
might have a very bad influence.

  The folder structure as follows:

      --main
        --|rfc1867.c          ##the patch file
        --|rfc1867.c.bak      ##the previous file

This patch folder has to .c files, the `rfc1867.c.bak` stands as the previous and the `rfc1867.c` stands
as the patched file. We have already patched all our systems using PHP5.3, and the load back to normal.
What you need to do is to change the `rfc1867.c` file in the main directory and recompile your PHP from source code.

Many thanks to the **2345.com** developers'  hard work.
