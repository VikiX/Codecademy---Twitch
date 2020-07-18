# Codecademy-Twitch # 
Twitch DS Project
Twitch stream data can be found [here](https://raw.githubusercontent.com/Codecademy/datasets/master/twitch/stream.csv) 
Twitch chat data can be found [here](https://github.com/Codecademy/datasets/blob/master/twitch/chat.csv)  

## What are the unique games, channels in the stream table?
Unique games, order by number of devices/players play each game 

```
select distinct game, count(device_id) as num_of_device
from stream
where game is not null
group by game 
order by count(device_id) desc;   
``` 
The most popular game is 'League of Legends'

|game|num_of_device|
|-------|---------|
|League of Legends|193524|
|Dota 2|85603|
|Counter-Strike: Global Offensive|54437|
|DayZ|37997|
|Heroes of the Storm|35309|
|The Binding of Isaac: Rebirth|29465|
|Gaming Talk Shows|28115|
|World of Tanks|15932|
|Hearthstone: Heroes of Warcraft|14399|
|Agar.io|11478|
|Rocket League|7087|
|ARK: Survival Evolved|4158|
|SpeedRunners|3367|
|Duck Game|1063|
|Fallout 3|485|
|Devil May Cry 4: Special Edition|231|
|Breaking Point|161|
|Batman: Arkham Knight|117|
|Reign Of Kings|50|
|The Witcher 3: Wild Hunt|45|
|Block N Load|34|
|Depth|27|
|Mortal Kombat X|22|
|H1Z1|7|
|Super Mario Bros.|6|
|Grand Theft Auto V|5|
|Music|4|
|The Elder Scrolls V: Skyrim|3|
|The Last of Us|3|
|Risk of Rain|2|
|Senran Kagura: Estival Versus|2|
|Besiege|1|
|Blackjack|1|
|Bridge Constructor Medieval|1|
|Choice Chamber|1|
|Cities: Skylines|1|
|Hektor|1|
|Lucius|1|
|Super Mario Bros. 3|1|
|The Sims 4|1|
|You Must Build A Boat|1|


Unique channels, order by number of devices/players play each game 
```
select distinct channel,  count(device_id) as num_of_device
from stream
where game is not null
group by channel 
order by count(device_id) desc;  
```
|channel|num_of_device|
|-------|------|
|frank|193520|
|estelle|72454|
|kramer|66060|
|george|42495|
|newman|41472|
|morty|35309|
|elaine|28357|
|susan|15932|
|helen|14405|
|jerry|13144|



## These are some big numbers from the game League of Legends (also known as LoL). Where are these LoL stream viewers located?
```
SELECT
country, COUNT(*) as num_of_players
FROM stream
where game = "League of Legends" 
and country is NOT NULL
GROUP BY country
order by count(*) desc
limit 10;
```
|country| num_of_players|
|-------|------|
|US|85606|
|CA|13034|
|DE|10835|
|GB|6964|
|TR|4412|
|AU|3911|
|SE|3533|
|NL|3213|
|DK|2909|
|GR|2885|
