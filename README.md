# Allergy-checker
This Python code provides a basic allergy checker that leverages Google Search to retrieve ingredients for a given consumable and checks them against your listed allergies.

Functionality:

Import Necessary Libraries:

Requests: This is used to make web requests to Google Search.
BeautifulSoup: Parses the HTML content returned by Google Search.
get_ingredients_google Function:

Takes a consumable as input (e.g., "pizza").
Constructs a Google search query string by appending "ingredients" to the consumable.
Forms a URL for the Google search.
Sets a user-agent header to mimic a web browser for better compatibility.
Sends a GET request to the URL using requests.get.
Parses the HTML response with BeautifulSoup.
Extracts text from relevant HTML elements (likely div with class BNeawe) and stores them in a list.
Returns a comma-separated string of ingredients, or "Ingredients not found" if none were found.
check_allergies Function:

Takes two arguments: ingredients (a string) and allergies (a list of strings).
Converts the ingredients string to lowercase for case-insensitive matching.
Iterates through each allergy in the list:
Checks if the lowercase allergy is present within the lowercase ingredients string using the in operator.
If any allergy is found, returns True (indicating a potential allergy match).
If no allergies are found, returns False.
User Input:

Prompts the user to enter the consumable they want to check.
Prompts the user to enter their comma-separated allergies (e.g., "peanuts, shellfish").
Splits the allergies input into a list and removes leading/trailing whitespace from each allergy.
Main Processing:

Calls get_ingredients_google to fetch the ingredients for the consumable.
Calls check_allergies to check if any allergies are present in the ingredients.
Based on the return value of check_allergies:
If True, prints a warning message indicating potential allergy matches.
If False, prints a message stating no known allergies were found.
Important Notes:

This code relies on web scraping, which can be unreliable due to potential website structure changes. Consider alternative data sources for ingredients if accuracy is critical.
The code performs a basic string search. For better accuracy, consider using food databases or allergy-specific information sources.
The code does not handle potential errors during web scraping (e.g., network issues). Implement error handling to make the code more robust.
Additional Considerations:

Explore alternative ingredient retrieval methods, such as APIs or pre-built food databases.
Implement more comprehensive allergy checking by considering synonyms or variations of known allergies.
Provide options for users to specify the source of ingredient information for improved confidence.
Overall, this code offers a starting point for building a more sophisticated allergy checker. However, it's crucial to address its limitations and explore reliable data sources to ensure accuracy and user safety.
