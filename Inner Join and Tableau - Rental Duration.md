Average Rental Length by Genre https://public.tableau.com/app/profile/christina.deleon/viz/3_10RentalDurationbyGenre/Sheet1

##### SQL query to produce data for the Tableau graphic:
SELECT 
genre.name AS "Genre",
AVG(film.rental_duration) AS "Average Rental Length"

FROM film film 

INNER JOIN film_category film_category
ON film.film_id = film_category.film_id

INNER JOIN category genre
ON film_category.category_id = genre.category_id

GROUP BY 1

ORDER BY 2 DESC
