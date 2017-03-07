---
layout: default
title: Windows Subsystem for Linux - Sync Issues
---

<style>
	{% include styles.css %}
</style>

<h1>Windows Subsystem for Linux - Sync Issues</h1>

<hr>

<h3>
  Situation
</h3>
<p>
  You have php application in WSL <code>/var/www/application</code> and you want edit it from windows with IDE (ie. PHPStorm).
</p>

<hr>

<h3>
  Issues
</h3>
<p>
  <ul> 
    <li>Modified files does not update in WSL command line</li>
    <li>New files does not show in WSL command line</li>
    <li>Modified files behave badly - can not <strong>mv, ls, rm,</strong> applications refuse to use them and not found messages</li>
    <li>WSL uses file system cache</li>
  </ul>
</p>

<hr>

<h3>
  Why
</h3>
<p>
  I found question with reasonable answers
  <a href="http://superuser.com/a/1078032">answer</a> and <a href="http://superuser.com/a/1115727">answer</a><br>
  TL:DR - Sharing/synchronizing of WSL files to windows is not supported.
</p>

<hr>

<h3>
  Solution
</h3>
<p>
  It's recommended to <code>cd</code> to windows folder and work there.<br>
  Move files from <code>/var/www/application</code> to <code>C:/Users/VBoss/Projects/application</code>. 
  Then set paths and configs to use this path <code>/mnt/c/Users/VBoss/Projects/application</code>. <br>
  And done, in my case i can run <code>composer install</code> in application folder using php from WSL.
</p>

<a href="http://spameri.cz">Back to index</a>
<p class="meta">Posted: {{ page.date | date_to_string }}</p>
