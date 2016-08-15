Description say he used git. Couldn't find anything on the website. Let's try to see robots.txt.<br>
```
User-Agent: *
Disallow: /.git
Disallow: /flag.php
```
Interesting.<br>
flag.php obviously gave a blank page. /.git redirected and gave 404 Not found<br>
Using <a href="https://github.com/kost/dvcs-ripper/blob/master/rip-git.pl">this</a> got the .git folder
`git log` showed this
```
commit 1746e11be489319bd8900318874b68304eb05288
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:47:49 2016 +0000

    add robots.txt

commit 6034c348380c9709715e6af60d04f684867d7234
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:45:11 2016 +0000

    remove flag

commit 541e08f75514d1caec2a62fe3a1af308da6f35d8
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:41:33 2016 +0000

    flag route

commit 97dcb30a5862aa43984b8beee84c9477a7315856
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:40:35 2016 +0000

    test flag

commit bf55633224c5c76f49d42621ace07aa705ebae6e
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:37:39 2016 +0000

    added colors

commit 6b3e1ffdc1d679c4815f08ef1d70d1b955451b36
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:27:57 2016 +0000

    enlarged text

commit d70b2e576c0f35e83d70027434050e06f729662b
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:27:04 2016 +0000

    added materialize and centered page

commit cda8cc0acc8a09153351e43c40f4abeb7a823a03
```
`git reset 6b3e1ffdc1d679c4815f08ef1d70d1b955451b36`<br>
`git show`
```
commit 6b3e1ffdc1d679c4815f08ef1d70d1b955451b36
Author: John C. Trevor Fields <john@icec.tf>
Date:   Wed Aug 10 21:27:57 2016 +0000

    enlarged text

diff --git a/index.php b/index.php
index 87c38e5..1c059ca 100644
--- a/index.php
+++ b/index.php
@@ -13,7 +13,7 @@
             height: 100%;
         }
         .hello {
-            font-size: 1.5em;
+            font-size: 2em;
             width: 100%;
         }
         .hello-wrapper {
@@ -25,7 +25,7 @@
         <div class="valign-wrapper hello-wrapper">
             <div class="hello valign center-align">
             <?php
-            echo 'Hello World!';
+                echo 'Hello World! IceCTF{secure_y0ur_g1t_repos_pe0ple}';
             ?>
             </div>
         </div>
```
<b>IceCTF{secure_y0ur_g1t_repos_pe0ple}</b>
