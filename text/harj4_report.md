# Harjoitus 4

Tähän harjoitukseen valitsin kohdan "B" suorittamisen, eli asentaisin 6 saltin tilaa/modulia.

Harjoitusta varten loin uuden orja-koneen 'e006', mutta tavallisesta poiketen säädin asetukset luomani skriptin avulla. En mene tässä tarkemmin skriptin toimintaan, mutta voit tarkastella sitä [täältä.](https://github.com/rootElmo/Agent-Setter)

Kokeilin aluksi yhteyttä orja-koneeseen ajamalla perinteisen 'whoami':n

	master $ sudo salt 'e006' cmd.run 'whoami'

Saltille saapui vastaus:

	e006:
		root

Seuraavaksi tarvitsi valita jokin ohjelma asennettavaksi. Olen asentanut omalle koneelleni joskus muinoin OpenTTD-pelin, joka on avoimen Transport Tycoon-peliin perustuva avoimen lähdekoodin uudelleenkirjoitus. Muistan kuitenkin, että asensin sen silloin käsin ja että se ei ollut hirveän intuitiivinen prosessi.

Kokeilin ajaa seuraavan komennon katsoakseni, voisiko OpenTTD:n asnetaa apt-getin kautta:

	master $ apt-cache search openttd

Kuinka ollakkaan, kyseinen paketti löytyi!

![scrshot1](../images/scrshot001.png)

Voin siis luoda pelin asennusta ja säätämistä varten salt-modulin ilman 'cmd.run' tmv. kikkailuja.

Loin uuden kansion "**openttd**" kansioon **/srv/salt**, ja loin init.sls tiedoston kansioon tilaa varten.

![scrshot2](../images/scrshot002.png)

## Lähteet

Tero Karvinen: terokarvinen.com/2020/configuration-managment-systems-palvelinten-hallinta-ict4tn022-spring-2020/
