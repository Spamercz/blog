---
layout: default
comments: true
title: PHPStorm, WSL, remote PHP and debugging
---
<style>
	{% include styles.css %}
</style>

# PHPStorm instalovaný a spouštěný přímo z WSL2

Pro začátek potřebujeme dvě věci. První je nainstalovaný XServer, zdarma appku najdeš tady https://apps.microsoft.com/store/detail/gwsl/9NL6KD1H33V3 . Druhá je temp složka uvnitř WSL2 kde začneme s návodem.

1. Stáhneme phpstorm (lze upravit verzi v odkazu až vyjde nová).
```
wget https://download.jetbrains.com/webide/PhpStorm-2022.1.2.tar.gz
```

2. Rozbalíme stažený archiv.
```
sudo mkdir -p /opt/phpstorm
sudo tar -xzvf PhpStorm-2022.1.2.tar.gz -C /opt/phpstorm
```

3. Spustíme PHPStorm, pokud máme novější verzi je třeba upravit cestu.
```
/opt/phpstorm/PhpStorm-221.5787.33/bin/phpstorm.sh
```

4. Pro příště si uděláme alias, pokud máme novější verzi je třeba upravit cestu.
```
alias phpstorm='/opt/phpstorm/PhpStorm-221.5787.33/bin/phpstorm.sh > /dev/null 2>&1 &'
```

5. Pro lepší výkon a případné stěžování PHPStormu kvůli synchronizaci, spustíme nálsedující.
```
sudo apt install inotify-tools
sudo sh -c "echo \"fs.inotify.max_user_watches = 524288\" >> /etc/sysctl.conf"
sudo sysctl -p
```

Extrahováno z https://www.pimwiddershoven.nl/entry/lightning-speed-development-on-windows-10-with-wsl-2-docker-terminal-and-jetbrains-intellij-pycharm-phpstorm

{% include footer.html %}

{% include disqus.md %}