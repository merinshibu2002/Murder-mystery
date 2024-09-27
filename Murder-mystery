Code 1
SELECT *
FROM crime_scene_report where type=&#39;murder&#39; and city=&#39;SQL City&#39; and
date=20180115
Output

| date     | type   | description                                                                                      | city     |
|----------|--------|--------------------------------------------------------------------------------------------------|----------|
| 20181115 | murder | Security footage shows that there were 2 witnesses. The first witness lives at the last house on "Northwestern Dr". The second witness, named Annabel, lives somewhere on "Franklin Ave". | SQL City |



Code 2
SELECT *
FROM person where address_street_name=&#39;Northwestern Dr&#39;ORDER BY
address_number DESC
limit 1
output
| id    | name          | license_id | address_number | address_street_name | ssn      |
|-------|---------------|------------|----------------|---------------------|----------|
| 14087 | Morty Szapiro | 11309      | 4919           | Northwestern Dr     | 11563429 |


Code 3
SELECT *
FROM person where name like &#39;%Annabel%&#39; and
address_street_name=&#39;Franklin Ave&#39;
Output
| id    | name           | license_id | address_number | address_street_name | ssn      |
|-------|----------------|------------|----------------|---------------------|----------|
| 16371 | Annabel Miller | 49073      | 103            | Franklin Ave        | 3187743  |


Code 4
SELECT *
FROM interview where person_id=14887
Output
| person_id | transcript |
|-----------|------------|
| 4487      | I heard a gunshot and then saw a man run out. He had a 'Get Fit Now Gym' bag. The membership number on the bag started with '48Z'. Only gold members have those bags. The man got into a car with a plate that included 'H42W'. |


Code 5
SELECT *
FROM interview where person_id=16371
Output
| person_id | transcript |
|-----------|------------|
| 4487      | I heard a gunshot and then saw a man run out. He had a "Get Fit Now Gym" bag. The membership number on the bag started with "48Z". Only gold members have those bags. The man got into a car with a plate that included "H42W". |


Code 6
SELECT *
FROM get_fit_now_member
where person_id=16371
Output
| Id    | person_id | name           | membership_start_date | membership_status |
|-------|-----------|----------------|-----------------------|-------------------|
| 99081 | 16571     | Annabel Miller | 2014/02/08            | gold              |


Code 7
SELECT *
FROM get_fit_now_check_in
where check_in_date=20180109 and membership_id like&#39;%48Z%&#39;
Output
| membership_id | check_in_date | check_in_time | check_out_time |
|---------------|---------------|---------------|----------------|
| 487ZA         | 20180109      | 1600          | 1730           |
| 4875A         | 20180109      | 1530          | 1700           |


Code 8
SELECT *
FROM get_fit_now_member
WHERE id = &#39;48Z7A&#39; OR id = &#39;48Z55&#39;;
Output
| id    | person_id | name          | membership_start_date | membership_status |
|-------|-----------|---------------|-----------------------|-------------------|
| 48255 | 67318     | Jeremy Bowers | 20160101              | gold              |
| 4827A | 28819     | Joe Germuska  | 20160305              | gold              |


Code 9
SELECT *
FROM drivers_license
where plate_number like &#39;%H42W%&#39;
output
| id     | age | height | eye_color | hair_color | gender | plate_number | car_make  | car_model |
|--------|-----|--------|-----------|------------|--------|--------------|-----------|-----------|
| 183779 | 21  | 65     | blue      | blonde     | female | H42W0X       | Toyota    | Prius     |
| 423327 | 30  | 70     | brown     | brown      | male   | O42H2V       | Chevrolet | Spark LS  |
| 664780 | 21  | 71     | black     | black      | male   | A42H2VR      | Nissan    | Altima    |


Code 10
SELECT *
FROM person
where license_id=423327 or license_id=664760
output
| id    | name          | license_id | address_number | address_street_name  | ssn       |
|-------|---------------|------------|----------------|----------------------|-----------|
| 51739 | Tushar Chandra| 644736     | 3412           | Phil St              | 1378202671|
| 67318 | Jeremy Bowers | 423327     | 530            | Washington St, Apt A3A| 837629279 |


Code 11
SELECT *
FROM person
WHERE (license_id=423327 OR license_id=664760) AND (id=67318 OR
id=28819);
output
| Id    | Name   | License ID | Address Number | Address Street Name      | SSN       |
|-------|--------|------------|----------------|--------------------------|-----------|
| 67318 | Jeremy | 423327     | 530            | Washington PI, Apt 3A    | 871539279 |
|       | Bowers |            |                |                          |           |

| Value | Description |
|-------|-------------|
| Congrats, you found the murderer! But wait, there's more... If you think you're up for a challenge, try querying the Interview transcript of the murderer to find the real villain behind this crime. If you feel especially confident in your SQL skills, try to complete this final step with no more than 2 queries. Use this INSERT statement with your new suspect to check your answer. | |



Code 12
SELECT * FROM interview WHERE person_id = &quot;67318&quot;;
output
| person_id | transcript |
|-----------|------------|
| 67318     | I was hired by a woman with a lot of money. I don't know her name but I know she's around 5'5" (65") or 5'7" (67"). She has red hair and she drives a Tesla Model S. I know that she attended the SQL Symphony Concert 3 times in December 2017. |


Code 13
SELECT * FROM drivers_license WHERE gender = &quot;female&quot; AND hair_color =
&quot;red&quot; AND height BETWEEN 65 AND 67 AND car_make = &quot;Tesla&quot; AND car_model =
&quot;Model S&quot;;
output
| Id     | Age | Height | Eye Color | Hair Color | Gender | Plate Number | Car Make | Car Model |
|--------|-----|--------|-----------|------------|--------|--------------|----------|-----------|
| 202298 | 68  | 66     | Green     | Red        | Female | 500123       | Tesla    | Model S   |
| 291182 | 65  | 66     | Blue      | Red        | Female | 08CM64       | Tesla    | Model S   |
| 918773 | 48  | 65     | Black     | Red        | Female | 917UU3       | Tesla    | Model S   |


Code 14
SELECT *
FROM person
WHERE license_id IN (&quot;202298&quot;, &quot;291182&quot;, &quot;918773&quot;);
output
| id    | name           | license_id | address_number | address_street_name | ssn        |
|-------|----------------|------------|----------------|---------------------|------------|
| 78881 | Red Korb       | 918773     | 107            | Camerata Dr         | 961388910  |
| 90700 | Regina George  | 291182     | 332            | Maple Ave           | 337169072  |
| 99716 | Miranda Priestly| 202298    | 1883           | Golden Ave          | 987756388  |


Code 15
SELECT *
FROM facebook_event_checkin
WHERE person_id IN (&quot;78881&quot;, &quot;90700&quot;, &quot;99716&quot;) GROUP BY person_id, event_name;
output
| person_id | event_id | event_name           | date     |
|-----------|----------|----------------------|----------|
| 99716     | 1143     | SQL Symphony Concert | 20171229 |


FINAL ANSWER FOR MURDER
SELECT *
FROM person
WHERE id=99716
output
| id    | name           | license_id | address_number | address_street_name | ssn         |
|-------|----------------|------------|----------------|---------------------|-------------|
| 89716 | Miranda Priestly | 202728    | 1083           | Colerian Ave.       | 987/65/8888 |




| value |
|-------|
| Congrats, you found the brains behind the murder! Everyone in SQL City hails you as the greatest SQL detective of all time. Time to break out the champagne! |



