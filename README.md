# harz_tsp

Experiments with the Traveling Salesman Problem applied to the Harz mountain region.

The Harz Mountains, a highland region in central Germany, are a popular destination for nature enthusiasts. This area is steeped in history, with its highest peak, the Brocken (1,141 m above sea level), playing a significant role in German culture. During the period of divided Germany, the Brocken served as a Soviet military base. Its historical significance extends further back to medieval times, where it was surrounded by legends of witches and devilish activities, immortalized by Johann Wolfgang von Goethe in his play *Faust*.

The Harz region offers a vast network of hiking trails, making it a haven for outdoor adventurers. In modern times, the area boasts extensive tourist infrastructure that highlights both its natural beauty and rich history. One notable feature of this infrastructure is the Harzer Wandernadel (Harz Hiking Pin Collection, or HWN). This initiative includes 222 stamping locations scattered across the region, where hikers can collect stamps in a dedicated passport. More information about these stamps can be found in an accompanying gallery.

While there is an abundance of books and guides detailing routes, attractions, and stamp-collection strategies, one intriguing question remains unanswered: is there an optimal route that connects all 222 stamp locations? If such a route exists, how long would it take to complete? This question is well-suited for exploration using graph theory and optimization techniques, such as those applied in solving the Traveling Salesman Problem (TSP).


### Project Objectives and TODOs

1. **Graph Modeling of Stamp Locations**  
   - Create graph matrices to represent the relationships between stamp locations.  
   - Calculate direct distances between stamp points (completed).  
   - Explore the use of mapping APIs (e.g., Komoot, OpenStreetMap) to calculate realistic routes using actual paths.  
     - Utilize the provided GPX file with coordinates of all stamp locations.  
     - Experiment with creating routes between two points and let the API generate realistic paths.  
     - In the future, compute routes connecting all 222 stamps, recognizing the computational time this might require.  

2. **Enhancing Route Parameters**  
   - Incorporate additional factors into route planning:  
     - Starting location preferences.  
     - Connections to public transportation.  
     - Altitude changes along the routes.  
     - Estimated time required to traverse each route.  

3. **Algorithm Selection**  
   - Research and implement suitable graph theory algorithms to optimize the route.  
