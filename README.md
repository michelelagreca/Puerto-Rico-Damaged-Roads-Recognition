# Puerto Rico's Damaged Roads Recognition
The project is based on the recognition of damaged roads with no entry or exit present in the territory of Puerto Rico. 
## Inspiration
Thanks to artificial intelligence, it is possible to complete many tasks, even the resolution of problems useful to society. In 2017, Hurricane Maria damaged part of the territory of Puerto Rico, and the recognition of all the elements resulting from this disaster could be difficult for the human eye, given the enormous size of the territory of Puerto Rico. Here artificial intelligence could be useful. It generally uses data to make a model learn to perform a certain task, maximizing its performance. In this case, it is possible to build a model that uses data to classify and recognize certain elements of the territory of Puerto Rico, such as damaged roads with no entrance or exit. <br><br>The data available to the model are the LIDAR data of Puerto Rico before and after the hurricane. Light Detection and Ranging (lidar) isa technology used to create high-resolutionmodels of ground elevationwithavertical accuracyof10centimeters (4 inches). Lidar equipment, which includes a laserscanner, a Global Positioning System (GPS), and an Inertial Navigation System (INS), istypicallymounted on a small aircraft. The laser scanner transmits brief pulses of light to the ground surface. Those pulsesare reflected or scatteredback and theirtravel timeisused to calculate the distance between the laser scanner and theground.
## Approach
The project aims to classify and recognize those areas of the territory of Puerto Rico characterized by damaged roads and therefore different from those before the hurricane. In fact, they can present narrowing of the carriageway, more or less abrupt interruptions such as the absence of the entrance and exit of the road itself, and so on.<br><br> The approach that can be used is to initially understand how the data is made. The data provided is LIDAR Data before and after the hurricane. They are data without a label, so a supervised learning procedure cannot be used, but unsupervised learning. An interesting technique that could be used is clustering, that is, grouping data that have similar characteristics among the whole dataset. In our case it could be useful to use this technique to group together all those portions of the territory of Puerto Rico that have characters connected to roads, so as to focus only on them.<br><br> After the clusters that contain the elements that interest us for the problem have been created, it is useful to go and check how we can actually understand if a road is damaged or not. This can be done by comparing the LIDAR data before the hurricane with those after the hurricane. One software for analyzing LIDAR data is Quick Terrain Modeler, which allows 360-degree manipulation of LIDAR data.<br><br>
To create the clusters it is first necessary to go and collect the data (LIDAR points in suitable structures). This can be done using a pre-existing data structure, called **KDTree**, available through the skylearn library (``sklearn.neighbors.KDTree``). The definition of a KDtree is that, its a structure of nodes which are interlinked sequentially together based on their properties, the arrangements of nodes is similar to that of a Tree structure in K dimensions, which makes it efficient to search for neighboring points.<br><br>Before running the eponymous method, a KDtree is build in the _init_ method. Initially every point is assigned a processed_flag_ with a default value of False, and when the point is processed its changed to True. If the point is not processed before, it’s assigned as a new cluster and all the nearby points to the cluster is found by the search_elements method. All the points returned are then recursively iterated again through the find_clusters method, to check if they are part of another cluster and to verify if the nearby points have not been processed before.<br><br>The final result will be a 3D map, composed of various clusters each with certain characteristics. The project will only take the clusters related to the elements of the damaged stages.
## Results
My team and I have encountered various difficulties in drafting the project. In particular, most of the difficulties are related to the resources that must be used to complete the project. Firstly, the data made available was constituted by an enormous size that did not allow the correct use due to the great computational power they needed. Moreover, there were difficulties in downloading the Quick Terrain Modeler software which was useful for manipulating LIDAR data. As a result, the project could not be completed and no results were evaluated.
## Teamwork
The team consists of 2 members. We initially tried to create an international team. In the team there were 2 guys from Brazil and Florida respectively. Unfortunately these guys were only available from 8pm which in Italy corresponds to 2 am. We Italian guys has decided to try anyway to find an approach to solve the problems related to the hackaton. The connections have happened via slack and via discord. Using applications for remote control (we used Anydesk) we have worked on the same code sharing ideas and knowledge. Although it was the first time we got in touch, there was immediately harmony in the team. We have worked well together and have combined our knowledge to try to create a working algorithm. Thanks to the knowledge acquired during the work produced in the degree theses, we were still able to sketch an algorithm for the Image clustering. Harmony was essential and the union of our knowledge allowed us to work together, sharing knowledge and making available as much as possible to collaborate in the best possible way.
## Team Composition
Michele La Greca, University of Catania<br>
Enrica Spataro, University of Catania
