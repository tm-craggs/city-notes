LIKE - A keyword that can be used to see if an attribute is similar to a pattern
For example:

SELECT *
FROM client
WHERE client_name LIKE '%LLC'

% - Any number of characters can come before the sign, just checks if the name ends in LLC

__ - The underscore means any characters. These can be used for checking dates, as the format means there will always be a particular number of digits. 

