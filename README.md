SELECT COUNT(*) AS total_admissions
FROM admissions;

SELECT AVG(DATEDIFF(discharge_date, admission_date)) AS average_length_of_stay
FROM admissions;

SELECT primary_diagnosis, COUNT(*) AS total_admissions
FROM admissions
GROUP BY primary_diagnosis;

SELECT service, AVG(DATEDIFF(discharge_date, admission_date)) AS average_length_of_stay
FROM admissions
GROUP BY service;

SELECT discharge_disposition, COUNT(*) AS total_discharges
FROM admissions
GROUP BY discharge_disposition;

SELECT service, COUNT(*) AS total_admissions
FROM admissions
GROUP BY service
HAVING COUNT(*) > 5;

SELECT AVG(DATEDIFF(discharge_date, admission_date)) AS average_length_of_stay
FROM admissions
WHERE primary_diagnosis = 'stroke';

SELECT acute_level, COUNT(*) AS total_visits
FROM emergency_visits
GROUP BY acute_level;

SELECT primary_diagnosis, service, COUNT(*) AS total_admissions
FROM admissions
GROUP BY primary_diagnosis, service;

SELECT MONTH(admission_date) AS month, COUNT(*) AS total_admissions
FROM admissions
GROUP BY month;

SELECT primary_diagnosis, MAX(DATEDIFF(discharge_date, admission_date)) AS max_length_of_stay
FROM admissions
GROUP BY primary_diagnosis;
