# FragAttackTest

  clone repository
``` bash
git clone https://github.com/vanhoefm/fragattacks.git ~/github/FragAttack

```

  chdir into research directory and setup the client.conf
``` bash
cd ~/github/FragAttack/fragattacks/research/
```

  turn wifi off

``` bash
nmcli radio wifi off
```

  enable python virtual environment
``` bash
source venv/bin/activate
```

  copy commands.txt into research directory
``` bash
cp commands.txt ~/github/Fragattack/fragattacks/research
```

  execute while loop to test all possible commands ( quick and dirty :) )
``` bash
while read line; do echo $line; timeout 30 ./fragattack.py wlan1 $line | egrep "SUCC|Test timed out|rekey|manually" ; done < commands.txt | tee output.txt
```



