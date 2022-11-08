# QUESTION 1
Show first name, last name, and gender of patients who's gender is 'M'
``` sql
select first_name , last_name , gender from patients where gender = 'M';
```

# QUESTION 2
Show first name and last name of patients who does not have allergies. (null)

``` sql
select first_name , last_name from patients where allergies is null;
```

# QUESTION 3
Show first name of patients that start with the letter 'C'

``` sql
select first_name from patients where SUBSTR(first_name , 1 , 1) = 'C';
```
# QUESTION 4

Show first name and last name of patients that weight within the range of 100 to 120 (inclusive)

``` sql
select first_name , last_name FROM patients WHERE weight between 100 AND 120;
```
# QUESTION 5
Update the patients table for the allergies column. If the patient's allergies is null then replace it with 'NKA'

``` sql
update patients 
set allergies = 'KNA'
where allergies is NULL;
```

# QUESTION 6
Show first name and last name concatinated into one column to show their full name.
``` sql
select concat(first_name, ' '  , last_name) as full_name from patients;
```
# QUESTION 7
Show first name, last name, and the full province name of each patient. Example: 'Ontario' instead of 'ON'

``` sql
select patients.first_name, patients.last_name , province_names.province_name
from patients inner join province_names on patients.province_id = province_names.province_id; 
```

# QUESTION 8
Show how many patients have a birth_date with 2010 as the birth year.

``` sql
select count(birth_date) from patients where year(birth_date) = 2010; 
```

# QUESTION 9
Show the first_name, last_name, and height of the patient with the greatest height
``` sql
select first_name, last_name, Max(height) from patients; 
```
# QUESTION 10
Show all columns for patients who have one of the following patient_ids:
1,45,534,879,1000
``` sql
SELECT *
FROM patients
WHERE
  patient_id IN (1, 45, 534, 879, 1000);
```

# QUESTION 11

Show the total number of admissions

``` sql
select count(patient_id) from admissions;
```

# QUESTION 12
Show all the columns from admissions where the patient was admitted and discharged on the same day.
``` sql
select * from admissions WHERE admission_date = discharge_date;
```

# QUESTION 13

Show the total number of admissions for patient_id 579.
``` sql
select patient_id , COUNT(*) as total_admission from admissions WHERE patient_id = 579;
```

# QUESTION 14
Based on the cities that our patients live in, show unique cities that are in province_id 'NS'?

``` sql
SELECT DISTINCT(city) AS unique_cities
FROM patients
WHERE province_id = 'NS';
```
# QUESTION 15
Write a query to find the first_name, last name and birth date of patients who have height more than 160 and weight more than 70.

``` sql
select first_name , last_name , birth_date from patients where height > 160 and weight > 70;
```

# QUESTION 16
Write a query to find list of patients first_name, last_name, and allergies from Hamilton where allergies are not null

``` sql
select first_nameselect first_name , last_name , allergies from patients where city = 'Hamilton' and allergies is not NULL;
```
