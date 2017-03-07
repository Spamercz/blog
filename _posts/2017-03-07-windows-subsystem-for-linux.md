---
layout: default
title: Windows Subsystem for Linux - Sync Issues
----

<style>
	{% include styles.css %}
</style>

<h1>Windows Subsystem for Linux - Sync Issues</h1>

<hr>

<h3>
  Situation
</h3>
<p>
  You have php application in WSL `/var/www/application` and you want edit it from windows with IDE (ie. PHPStorm).
</p>

<hr>

<h3>
  Issues
</h3>
<p>
  <ul> 
    <li>Modified files does not update in WSL command line</li>
    <li>New files does not show in WSL command line</li>
    <li>Modified files behave badly - can not mv, ls, rm, applications refuse to use them and not found messages</li>
    <li>WSL uses file system cache</li>
  </ul>
</p>

<hr>

<h3>
  Why
</h3>
<p>
  I found question with reasonable answers
  <a href="http://superuser.com/a/1078032">answer</a> and <a href="http://superuser.com/a/1115727">answer</a>
  TL:DR - Sharing/synchronizing of WSL files to windows is not supported.
</p>

<hr>

<h3>
  Solution
</h3>
<p>
  It's recommended to `cd` to windows folder and work there.
  Move files from `/var/www/application` to `C:/Users/VBoss/Projects/application`. 
  Then set paths and configs to use this path `/mnt/c/Users/VBoss/Projects/application`. 
  And done, in my case i can run `composer install` in application folder using php from WSL.
</p>

<p>[Back to index](http://spameri.cz)</p>
<p class="meta">Posted: {{ page.date | date_to_string }}</p>
