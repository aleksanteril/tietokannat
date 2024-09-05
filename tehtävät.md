

# Yhteen tauluun kohdistuvat kyselyt

### Tehtävä 1
select * from goal;
![Screenshot 2024-09-05 094053](https://github.com/user-attachments/assets/a59400f0-ff4d-4822-b170-1e4964039e24)


### Tehtävä 2
select airport.name, airport.type
from airport
where airport.iso_country = "FI"; 
![Screenshot 2024-09-05 094712](https://github.com/user-attachments/assets/d9eda852-6587-4955-b94f-fb092ae51b2a)


### Tehtävä 3
select name
from airport
where iso_country = "FI"
order by name asc;
![Screenshot 2024-09-05 095000](https://github.com/user-attachments/assets/331be0e8-2bcd-43b9-bba2-35ad37e85505)


### Tehtävä 4
select name, type
from airport
where iso_country = "FI"
order by type, name asc;
![Screenshot 2024-09-05 095231](https://github.com/user-attachments/assets/abaa4de7-139f-4a3e-a2c7-1054b9fe3448)


### Tehtävä 5
select name
from country
where name like "F%";
![Screenshot 2024-09-05 095334](https://github.com/user-attachments/assets/a53c2ba2-8a58-49e4-86dd-bab6374dc364)


### Tehtävä 6
select name
from country
where name like "%F%";
![Screenshot 2024-09-05 095433](https://github.com/user-attachments/assets/0b3b1f12-8e91-4756-8259-a64eb0c9374a)


### Tehtävä 7
select location
from game
where screen_name = "vesa";
![Screenshot 2024-09-05 095643](https://github.com/user-attachments/assets/cdbe6d17-556e-49a9-a3c1-327ce11bd9dc)


### Tehtävä 8
select co2_consumed
from game
where screen_name = "Ilkka";
![Screenshot 2024-09-05 095754](https://github.com/user-attachments/assets/86f704ba-cbee-4255-8ec7-bf0327c7d56c)


### Tehtävä 9
select distinct co2_budget
from game;
![Screenshot 2024-09-05 095855](https://github.com/user-attachments/assets/f0b1f6f8-6540-4586-951f-26077e1b913c)


########################################
# Where osan liitosehto harjoitukset

### Tehtävä 1
select country.name as "country name", airport.name as "airport name"
from country, airport
where country.name = "Iceland" and airport.iso_country = country.iso_country;
![Screenshot 2024-09-05 100236](https://github.com/user-attachments/assets/398e58b5-0dd8-4619-8df2-fdcb1355f7f3)


### Tehtävä 2
select airport.name as "airport name"
from airport, country
where country.iso_country = airport.iso_country 
and country.name = "France" and airport.type = "large_airport";
![Screenshot 2024-09-05 100434](https://github.com/user-attachments/assets/60ac6613-a06c-4e3a-82ed-22da1005f11b)

### Tehtävä 3
select country.name as "country_name", airport.name as "airport_name"
from airport, country
where country.continent = "AN" and country.iso_country = airport.iso_country;
![Screenshot 2024-09-05 102403](https://github.com/user-attachments/assets/2a7de8cc-541a-4f40-80f6-cab493b0fe7c)


### Tehtävä 4
select elevation_ft
from airport, game
where screen_name = "Heini" and airport.ident = game.location;
![Screenshot 2024-09-05 102918](https://github.com/user-attachments/assets/fdf9e6ac-1b09-4653-bd4c-4392ffcf66f0)


### Tehtävä 5
select elevation_ft*0.3048 as "elevation_m"
from airport, game
where screen_name = "Heini" and airport.ident = game.location;
![Screenshot 2024-09-05 103042](https://github.com/user-attachments/assets/9dbf132c-a64a-4eff-9e67-1fed10d9682b)


### Tehtävä 6
select airport.name
from airport, game
where screen_name ="Ilkka" and airport.ident = game.location;
![Screenshot 2024-09-05 103155](https://github.com/user-attachments/assets/2166cd3c-6f9e-4268-ba61-1c188fe622d7)


### Tehtävä 7
select country.name
from airport, game, country
where screen_name ="Ilkka" and airport.ident = game.location
and airport.iso_country = country.iso_country;
![Screenshot 2024-09-05 103427](https://github.com/user-attachments/assets/283ea497-2cfe-48c8-9b9f-a253f2830038)


### Tehtävä 8
select goal.name
from goal, goal_reached, game
where screen_name = "Heini" and game.id = game_id and goal.id = goal_id;
![Screenshot 2024-09-05 103709](https://github.com/user-attachments/assets/bdea4e59-9987-46d3-919e-9fdd0f406d22)


### Tehtävä 9
select airport.name
from goal, goal_reached, game, airport
where screen_name = "Ilkka"
and goal.name = "clouds"
and game.id = game_id and goal.id = goal_id
and game.location = airport.ident;
![Screenshot 2024-09-05 104133](https://github.com/user-attachments/assets/1cf60108-4996-4ee2-92f2-90439504defe)

### Tehtävä 10
select country.name
from goal, goal_reached, game, airport, country
where screen_name = "Ilkka"
and goal.name = "clouds"
and game.id = game_id and goal.id = goal_id
and game.location = airport.ident
and airport.iso_country = country.iso_country;
![Screenshot 2024-09-05 104320](https://github.com/user-attachments/assets/bd5615de-405f-45e9-a083-b005d0e9cdd5)


########################################
# Join kysely harjoitukset

### Tehtävä 1
select country.name as "country name", airport.name as "airport name"
from airport
inner join country on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";
![Screenshot 2024-09-05 110012](https://github.com/user-attachments/assets/4fe3e108-a404-4588-b71e-6bbc258163ad)


### Tehtävä 2
select screen_name, airport.name
from game inner join airport on game.location = airport.ident;
![Screenshot 2024-09-05 110126](https://github.com/user-attachments/assets/ee335bff-98b3-49b5-80e4-ff881bc6b05d)


### Tehtävä 3
select screen_name, country.name
from game inner join airport on game.location = airport.ident
inner join country on country.iso_country = airport.iso_country;
![Screenshot 2024-09-05 110225](https://github.com/user-attachments/assets/4cdb42bb-e261-4fe8-b092-657298ca2e54)


### Tehtävä 4
select airport.name, game.screen_name
from airport left join game on airport.ident = game.location
where airport.name like "%Hels%";
![Screenshot 2024-09-05 110800](https://github.com/user-attachments/assets/e0c80156-4ab8-4239-af59-2a417704823f)


### Tehtävä 5
select goal.name, screen_name
from goal left join goal_reached on goal.id = goal_id 
left join game on game.id = game_id;
![Screenshot 2024-09-05 111338](https://github.com/user-attachments/assets/47119086-1f70-4228-8954-da29306d61a3)


########################################
# Sisäkysely harjoitukset

### Tehtävä 1
select country.name
from country
where iso_country = (
	select iso_country
	from airport
	where name like "Satsuma%");
![Screenshot 2024-09-05 112624](https://github.com/user-attachments/assets/254bf584-0b4c-433e-bf1e-0a0737bd5897)


### Tehtävä 2
select airport.name
from airport
where iso_country = (
	select iso_country
	from country
	where name = "Monaco"); 
![Screenshot 2024-09-05 112821](https://github.com/user-attachments/assets/4be3c359-5a1d-4c09-852f-ee6eefa4c6b9)


### Tehtävä 3
select screen_name
from game
where id in (
	select game_id
	from goal_reached
	where goal_id in(
		select id 
		from goal
		where name = "CLOUDS"));
![Screenshot 2024-09-05 113338](https://github.com/user-attachments/assets/0d2f1a64-237d-4b93-8748-b23c96e756dc)

### Tehtävä 4
select country.name
from country
where iso_country not in (
	select iso_country
	from airport);
![Screenshot 2024-09-05 113428](https://github.com/user-attachments/assets/cdf80f47-5078-47c8-83dc-4384e379a49d)


### Tehtävä 5
select goal.name
from goal
where id not in(
	select goal_id
	from goal_reached
	where game_id in(
		select id
		from game
		where screen_name = "Heini"));
![Screenshot 2024-09-05 113609](https://github.com/user-attachments/assets/94d3ce69-3926-4670-9cb6-8dc2c83cd2e7)


########################################
# Koostetietokyselyt

### Tehtävä 1
select max(elevation_ft)
from airport;
![Screenshot 2024-09-05 132158](https://github.com/user-attachments/assets/68df5fc6-d7b8-4df4-a3d0-d96e42d20b4d)


### Tehtävä 2
select country.continent, count(*)
from country
group by continent;
![Screenshot 2024-09-05 132834](https://github.com/user-attachments/assets/f1341611-3c2e-42a8-a569-46d9c3649a36)


### Tehtävä 3
select screen_name, count(*)
from game, goal_reached
where id = game_id
group by screen_name;
![Screenshot 2024-09-05 133412](https://github.com/user-attachments/assets/3a199c5a-bf12-4978-9ea5-981d0c7805b3)


### Tehtävä 4
select screen_name
from game
where co2_consumed in(
	select min(co2_consumed)
	from game);
![Screenshot 2024-09-05 133513](https://github.com/user-attachments/assets/6ed14fb6-1c0a-492d-994c-5c073e83579d)


### Tehtävä 5
select country.name, count(*)
from country, airport
where airport.iso_country = country.iso_country
group by country.name
order by count(*) desc
limit 50;
![Screenshot 2024-09-05 134559](https://github.com/user-attachments/assets/b6651f43-5824-491d-87a3-73d0ba1253e8)


### Tehtävä 6
select country.name
from country, airport
where airport.iso_country = country.iso_country 
group by country.iso_country having count(*) > 1000;
![Screenshot 2024-09-05 135026](https://github.com/user-attachments/assets/b4bbb846-910a-4fca-861f-89376af5a4fa)


### Tehtävä 7
select name
from airport
where elevation_ft in(
	select max(elevation_ft)
	from airport);
![Screenshot 2024-09-05 135510](https://github.com/user-attachments/assets/39794363-1bdf-4c48-bf78-c6124c3c088f)


### Tehtävä 8
select name
from country
where iso_country in(
	select iso_country
	from airport
	where elevation_ft in(
		select max(elevation_ft)
		from airport));
![Screenshot 2024-09-05 135714](https://github.com/user-attachments/assets/995261c7-172c-4954-9ebe-f13703943b5a)


### Tehtävä 9
select count(*)
from goal_reached
where game_id in(
	select id
	from game
	where screen_name = "Heini");
![Screenshot 2024-09-05 135905](https://github.com/user-attachments/assets/6f45c76b-2a8e-4c3f-98c3-abeb2e5e5bf1)

### Tehtävä 10
select name
from airport
where latitude_deg in(
	select min(latitude_deg)
	from airport);
![Screenshot 2024-09-05 140112](https://github.com/user-attachments/assets/ab774d23-859b-49c5-8c3c-069fdbdd4e7f)


########################################
# Päivityskyselyt

### Tehtävä 1
update game
set co2_consumed = co2_consumed + 500,
location = (
	select ident
	from airport
	where name = "Nottingham airport")
where screen_name = "Vesa";
![Screenshot 2024-09-05 141008](https://github.com/user-attachments/assets/8998370d-4234-43e1-8d03-c41136b8b161)


### Tehtävä 3
delete from goal_reached;
select from goal_reached;
![Screenshot 2024-09-05 141136](https://github.com/user-attachments/assets/b7e1103c-71c4-4a18-a766-ab3fe4100055)


### Tehtävä 4
delete from game;
select from game;
![Screenshot 2024-09-05 141244](https://github.com/user-attachments/assets/2457adf9-b09f-40e2-8cff-cc148ec94d12)

