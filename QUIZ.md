# Image understanding application

Our client asked us to create an image understanding tool for their internal use. Here are the features the tool should have from the client perspective:
1. The user will upload a photo
2. The tool will identify all objects in the photo (e.g. the photo contains 1 car, 1 cat and two birds)
3. For each object in the photo, the tool will find similar images in a database of images compiled by the client
4. The tool will display to the user the found objects, similar images for each object and associated metadata 

## Your Task 

With this information and assuming the code your colleagues provided works correctly, please write a high level design document for the image understanding tool, covering the following aspects:
1. Frontend architecture
   a. What technologies would be used to create the user interface, and how to communicate with the backend to get the correct data?
   b. User login is not necessary
2. Backend architecture
   a. If you are applying for a frontend only position, ignore this task and assume the backend is correctly implemented by another engineer
   b. Refer to the appendix below explaining the AI algorithm
   c. What technologies would be used to create the backend, and how to integrate the AI algorithm into a web application?
3. Cloud deployment
   a. How would you package and deploy the finished application to the cloud (e.g. AWS, GCP, azure)
   b. What technologies would you use?
4. Testing and QA
   a. How would you test the frontend and backend of this application?
   Write around 500 words or less per each point (roughly 3 paragraphs). You may include diagrams if it helps to convey your point.

## AI algorithm 

To achieve this, the AI engineers have proposed an algorithm to enable the functionality of the tool which is described in the diagram below:

For the rest of this exercise, you can assume you are given the implementations of algorithm A and algorithm B with the following API

### Algorithm A
Given an image, outputs a list of objects in the image.
* Inputs:
  * image_path: the path to the uploaded image on a storage bucket
* Outputs:
  * objects: a list of (x,y) coordinates that designate object bounding boxes
### Algorithm B
Given an image, outputs a vector containing 128 floating point numbers (this vector is usually called a "representation"). It is stated in the documentation for this code that two images with similar semantic content (e.g. two dogs) will produce similar representations, while an image with dissimilar content (e.g. a cat) will produce a very different representation.
* Inputs:
  * image_path: the path to a crop of the original image on a storage bucket 
* Outputs:
  * representation: a 128-dimensional floating-point vector describing the image contents For the Approximate Nearest Neighbor search, a library like faiss can be used.

