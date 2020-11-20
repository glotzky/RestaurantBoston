# RestaurantBoston
## Report: 
### **** See presentation is in repository. 'Cafe Landwer Location.pdf'
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
2. South End, Fenway
3. Downtown, Jamaica Plain
4. Longwood, Leather District, Dorchester
5. North End, South Boston Waterfront, South Boston
6. Mission Hill
7. Charlestown
8. West End, Chinatown
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
- Jamaica Plain
- Bay Village
- Leather District
- Chinatown
- North End
- South End
- Back Bay
- Beacon Hill
- Fenway
- Allston

#### Cluster 2: 
- West Roxbury

#### Cluster 3:
- Roxbury

#### Cluster 4:
- Roslindale
- Mission Hill
- East Boston
- Charlestown
- West End
- Downtown
- Brighton
- Hyde Park
- Dorchester
- South Boston Waterfront
- South Boston

#### Cluster 5:
- Longwood
- Mattapan

#### 4.2 Interpretation: 
Cafe Landwer currently has locations in Fenway(2nd most popular venue, Cluster 1) and Brighton(9th most popular venue, Cluster 4). Their locations reflect that they have placed them in locations where the areas are not similar in types of venues frequencies per square meter. Since their price is regarded as category 1, the least expensive price type, their locations of similar venues are not as reflective of the areas since their locations can be assumed to not be dependent for them on the average price of restaurant within the area. 

## 5. Discussion
Cafe Landwer is a price tier of 1, which means that they are the least expensive category for a venue. Given this information it can be assumed that their choice for a new location won't be dependent on the price of the surrounding area since it is affordable by most socioeconomic groups. From the k-means clusters gathered it would be recommended that they stay within Clusters 1 and 4 regarding locations with similar venue styles. By limiting Cluster if they would prefer to add a location with other competing coffee shops/cafes they should search Back Bay or South End. If they choose to add a location where cafes are not as popular then any of the Unlisted locations would suffice. 

##### 5.1 Limit search: 
##### a. Search in areas most similar to their current locations.

Cluster 1 and Cluster 4.

###### Cluster 1: 
- Jamaica Plain
- Bay Village
- Leather District
- Chinatown
- North End
- South End
- Back Bay
- Beacon Hill
- Fenway
- Allston

###### Cluster 4:
- Roslindale
- Mission Hill
- East Boston
- Charlestown
- West End
- Downtown
- Brighton
- Hyde Park
- Dorchester
- South Boston Waterfront
- South Boston

##### b. Search in area where Cafe type is least common within cluster
- Searching within the given clusters would indicate that their locations would be most similar for their customer groups to go. Use the unlisted type from each cluster.

Additionally remove Cafe Landwer current location cities. 
Unlisted: Roslindale, Bay Village, Roxbury, East Boston, Beacon Hill, West Roxbury, Mattapan, Allston
###### Cluster 1: 
- Bay Village
- Beacon Hill
- Allston
Eliminated: Jamaica Plain, Leather District, Chinatown, North End, South End, Back Bay

###### Cluster 4:
- Roslindale
- East Boston

Eliminated: South Boston, South Boston Waterfront, Dorchester, Hyde Park, Downtown, West End, Charlestown, Mission Hill

Has current Location in Brighton and Fenway
Eliminated: Brigton, Fenway

Search limited to: Bay Village, Beacon Hill, Allston, Roslindale, East Boston

###### Potential Locations: 
- Bay Village, Beacon Hill, Allston, Roslindale, East Boston

##### c. In order to stay within close proximity of each location average radial distance between each location 2.5 mi = 4025 m
- Bay Village, Beacon Hill, Allston

Under 2.5 mi:

- Bay Village(~2.5 mi - Fenway Location, ~5 mi - Brigton Location)
- Beacon Hill(~2.5 mi - Fenway Location, ~5 mi - Brigton Location)
- Allston(~1.7 mi - Fenway Location, ~2.2 mi - Brighton Location)

Over 2.5 mi:

###### ~ 5 mi away:

- Roslindale(~ 5.6 mi - Brigton Location, ~ 5.6 mi - Fenway Location)
- East Boston(~ 5 mi - Fenway Location, ~7.5 mi - Brighton Location)

###### Potential Locations: 
- Bay Village, Beacon Hill, Allston

Transportation in Boston is a major component for its unique set of demographics to travel. Whether college students, high school students, working professionals, or the elderly community, T-train proximity is a significant factor for moving around the city. 

##### d. Stay within close proximity to the T train. Need walking distance to T stop

###### Potential Locations: 
Allston, Beacon Hill, Bay Village

## Conclusion: 
Based on this approach, it would reccomended to Cafe Landwer that they search for a new location within Allston, Beacon Hill, and Bay Village. 
All of these locations are:
1. In the similar Clusters to Cafe Landwer current locations based on venue similarity of area
2. Cafe/Coffee Shop is least common venue of that area
3. Within 2.5 mi of a given Cafe Landwer Location
4. Within Close Proximity to the T train(Walking Distance). 



