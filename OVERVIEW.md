# SQL-ISLAND-GAME
I completed the mini-game of SQL Island.
# GAME EXPLAINED 
Your character begins the game stranded on an island with three villages and randomly chosen villagers. To get food and money and eventually escape the island, you must speak to the right people and gather the right information.
# Provided Tables
VILLAGE (villageid, name, chief)
INHABITANT (personid, name, villageid, gender, job, gold, state)
ITEM (item, owner)
# QUERIES
# FROM
SELECT * 

FROM inhabitant;
# WHERE
SELECT * 
FROM inhabitant
WHERE state = 'friendly';

# AND
SELECT * 
FROM inhabitant
WHERE state = ‘friendly’
AND job = ‘weaponsmith’;

SELECT * 
FROM inhabitant
WHERE state = ‘friendly’
AND job LIKE ‘%smith’;

SELECT * 
FROM INHABITANT 
WHERE state = ‘friendly’ 
AND job = ‘dealer’ 
OR job = ‘merchant’

SELECT inhabitant.name 
FROM village, inhabitant 
WHERE village.chief = inhabitant.personid 
AND village.name = ‘Onionville’

SELECT COUNT(*) 
FROM inhabitant, village
WHERE village.villageid = inhabitant.villageid 
AND village.name = ‘Onionville’ 
AND gender = ‘f’

# OR
SELECT SUM(inhabitant.gold) 
FROM inhabitant 
WHERE job = ‘baker’ 
OR job = ‘dealer’ 
OR job = ‘merchant’

# GROUP BY
SELECT state, AVG(inhabitant.gold) 
FROM inhabitant 
GROUP BY state 
ORDER BY AVG(inhabitant.gold)
