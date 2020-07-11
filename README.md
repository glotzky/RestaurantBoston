# RestaurantBoston

## 1. Introduction:
### 1.1 Background: 
Established in Berlin in 1919, and with 60 locations worldwide, Cafe Landwer is expanding to North America. Cafe Landwer is a specialty coffee shop with highly trained baristas combined with a full service, sit down and take out restaurant serving breakfast, lunch and dinner. Their menu is inspired by Italian and Mediterranean cuisine, and they adhere to the highest standards of quality for our ingredients.

### 1.2 Problem
Cafe Landwer has their first two locations in Boston, and have been an extreme local success. I will look to see where would be the best location for a third location if they were to expand further out in the Metro-Bosotn Area by leveraging Foursquare API data. 

Cafe Landwer's new location must be able to accommodate for their unique style, price, and additional outdoor dining area. 

### 1.2.1 Questions
####   1. Which Metro-Boston location does their price range fit?
####   2. Is there already a restaurant with similar cuisine near that area?
####   3. Has the area had a previous Mediterranean cuisine restaurant that failed?
####   4. Have the local customers been to the existing locations?

## 2. Data:

#### Method - Idea: 
###### Boston Area:
1. Extract zipcodes from Metro-Boston
2. Exclude existing Cafe Landwer Locations
###### Foursquare:
1. Collect data on average prices of restaurants within the set area
2. Limit search to areas with their price range
3. Search the local cuisines of the area, exclude those with Mediterranean cuisine
  a. Use rating data to see areas where mediterranean food is favorable.
4. Use k-means to find the best location for a new Cafe Landwer restaurant, given their 2 existing locations.
###### Outside Research:
Find potential commercial listings within that area for proposal.
