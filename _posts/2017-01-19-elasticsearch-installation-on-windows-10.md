---
layout: default
title: Elasticsearch installation on windows 10
---

This tutorial is for **bash on windows 10**, to enable it on your system follow this tutorial <http://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/>

Step by step copy paste tutorial:

## 1. Java installation
 - default ubuntu on windows installation doesn't have java so we need to install it.
 
```bash
sudo apt-add-repository ppa:webupd8team/java
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install oracle-java8-installer
```

```bash
export JAVA_HOME=/usr/lib/jvm/java-8-oracle
```

```bash
java -version
```

Last command should return something like this

```
java version "1.8.0_121"
Java(TM) SE Runtime Environment (build 1.8.0_121-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.121-b13, mixed mode)
```

## 2. Elastic installation

Go to home directory.
```
cd 
```

Download elasticsearch, in time of article version 5.1.2 is lastest.

```
curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.1.2.tar.gz
```

Extract elasticsearch.

```
tar -xvf elasticsearch-5.1.2.tar.gz
```

Go to extracted directory.

```
cd elasticsearch-5.1.2/bin
```

And run elasticsearch

```
./elasticsearch
```

### Posible errors

- _unable to install syscall filter_ this message is OK, as described in link linux version is old for this security feature, but it is not essential.
[https://discuss.elastic.co/t/elasticsearch-warn-unable-to-install-syscall-filter/42819](https://discuss.elastic.co/t/elasticsearch-warn-unable-to-install-syscall-filter/42819)

- In case of wrong permissions 
```
cd
chmod 777 -R elasticsearch-5.1.2/logs/
```


<p>
	<a href="http://spameri.cz">Back to index</a>
</p>
<p class="meta">{{ page.date | date_to_string }}</p>
