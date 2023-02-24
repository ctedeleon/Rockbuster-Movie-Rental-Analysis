Countries and Rental Revenue https://public.tableau.com/app/profile/christina.deleon/viz/3_10RentalRevenuebyCountry/Sheet1

##### SQL Query to produce data for the Tableau graphic:

SELECT 
country.country AS "Country",
SUM(payment.amount) AS "Total Revenue"

FROM customer customer

INNER JOIN address address 
ON customer.address_id = address.address_id

INNER JOIN city city 
ON address.city_id = city.city_id

INNER JOIN country country
ON city.country_id = country.country_id

INNER JOIN payment payment 
ON customer.customer_id = payment.customer_id

GROUP BY 1

ORDER BY 2 DESC 
