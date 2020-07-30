# RestaurantBoston

## 1. Introduction:
### 1.1 Background: 
Established in Berlin in 1919, and with 60 locations worldwide, Cafe Landwer is expanding to North America. Cafe Landwer is a specialty coffee shop with highly trained baristas combined with a full service, sit down and take out restaurant serving breakfast, lunch and dinner. Their menu is inspired by Italian and Mediterranean cuisine, and they adhere to the highest standards of quality for our ingredients.

### 1.2 Problem
Cafe Landwer has their first two locations in Boston, and have been an extreme local success. I will look to see where would be the best location for a third location if they were to expand further out in the Metro-Bosotn Area by leveraging Foursquare API data. 

Cafe Landwer's new location must be able to accommodate for their unique style, price, and additional outdoor dining area. 

### 1.2.1 Questions
####   1. Which Boston city has the most Coffee Shops/Cafes?
####   2. Which Metro-Boston location does their price range fit?
####   3. Are their current locations sufficient for business?
####   4. Have the local customers been to the existing locations?


## 2. Data:
#### 2.1 Method - Idea: 
###### 2.1.1 Boston Area:
1. Extract Latitude and Longitude from Metro-Boston Cities csv file
###### 2.1.2 Foursquare:
1. Collect data on most popular type of restaurants within each set area
2. Limit search to areas with their price range
3. Search the local cuisines of the area, exclude those with Mediterranean cuisine
  a. Use rating data to see areas where mediterranean food is favorable.
4. Use k-means to find the best location for a new Cafe Landwer restaurant, given their 2 existing locations.
###### 2.1.3 Outside Research:
Find potential commercial listings within that area for proposal.


## 3. Methodology:
1. Limit search by picking a arbitrary latitude and longitude for desired max area region
###### Lat: (42.425141; 42.307227) Lon:(-70.964606,-71.258284)
2. Find all names of the cities that make up boston and convert to readable pandas file
3. Convert SqMiles to Meters for approximation around the given city area
4. Gather Latitude and Longitude from each city, (i)fill in missing data
5. Check test cases for neighborhood information
6. Get nearby venues types of the surrounding city (i) using method get_category_type
7. Get nearby venues of each area (i) using method getNearbyVenues
8. Group the venues to collect the popularity of each type (i) search through newly acquired groups of venues
9. Organize newly found data in table ascending in most common venue to least common
10. Map data using folium. 
11. Describe data by clusters based on similar venue types


## 4. Results: 
#### 4.1 Coffee Shop/Cafe Most Common Venues:
1. Back Bay
2a. South End
2b. Fenway
3a. Downtown
3b. Jamaica Plain
4a. Longwood
4b. Leather District
4c. Dorchester
5a. North End
5b. South Boston Waterfront
5c. South Boston
6. Mission Hill
7. Charlestown
8a. West End
8b. Chinatown
9. Brighton
10. Longwood
___Unlisted:___
- Roslindale
- Bay Village
- Roxbury
- East Boston
- Beacon Hill
- West Roxbury
- Mattapan
- Allston


### 4.2 Cluster by Venue Types
#### Cluster 1: 
Jamaica Plain
Bay Village
Leather District
Chinatown
North End
South End
Back Bay
Beacon Hill
Fenway
Allston

#### Cluster 2: 
West Roxbury

#### Cluster 3:
Roxbury

#### Cluster 4:
Roslindale
Mission Hill
East Boston
Charlestown
West End
Downtown
Brighton
Hyde Park
Dorchester
South Boston Waterfront
South Boston

#### Cluster 5:
Longwood
Mattapan



