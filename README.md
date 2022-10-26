# Recommendation System

A recommender system aims to suggest relevant content or products to users that might be liked or purchased by them. It helps to find items that the user is looking for — and they don’t even realize it until the recommendation is displayed. Different strategies have to be applied for different clients and they are determined by available data. Since RS has to be a data-driven approach, it can be fueled by machine learning algorithms.

There are two main techniques to be described: content-based filtering and collaborative filtering.

## 1. Content-based filtering

Content-based filtering means that RS will recommend similar items to the liked or purchased ones (contextual strategy). For example, if user A watched two horror movies, another horror movie will be proposed to him. This technique can be user or item-centered.

![image](https://user-images.githubusercontent.com/35486320/197945835-e04fccfa-cda4-422a-904f-07623a7e4f5c.png)

## 2. Collaborative filtering

It addresses some of the limitations of content-based filtering by using similarities between users and items simultaneously. It allows us to recommend an item to user A based on the items purchased by similar user B. 

![image](https://user-images.githubusercontent.com/35486320/197945997-e5328328-9780-4bc1-924e-0481a487f0b0.png)

## Difference between Content-based and Collaborative Filtering

<table>
  <tr>
    <th> Model </th>
    <th> Content-based </th>
    <th> Collaborative Filterng </th>
  </tr>
  <tr>
    <td> Example </td>
    <td> If a user likes comedy, another comedy is recommended </td>
    <td> If user A is similar to user B and user B likes a certain video, then this video is recommended to user A </td>
  </tr>
  <tr>
    <td> Advantages </td>
    <td> 1. Doesn’t need any data about the other users
         2. Can recommend niche items </td>
    <td> 1. Doesn’t require domain knowledge
         2. Help users to discover new interests </td>
  </tr>
  <tr>
    <td> Disadvantages </td>
    <td> 1. Requires a lot of domain knowledge
         2. Makes recommendations only based on the existing interests of the user </td>
    <td> 1. Cannot handle fresh items (cold-start)
         2. Hard to include features beyond the query </td>
  </tr>
</table>

## Evaluating the recommendation system

There are several metrics to evaluate models. In terms of content-based filtering, we should choose from similarity metrics, while for collaborative methods – predictive and classification metrics depend on whether we predict score or binary output. 

## Similarity metrics

When we have an item’s meta-data available, we can easily recommend new items to the user. For example, if we watched a movie A on Netflix, we can recommend another movie based on extensive meta-data tags for other movies and calculate the distance between them and movie A. Another way is to use NLP techniques such as Tf-Idf and represent movie descriptions as vectors. We only need to select a similarity metric. 

The most common ones are cosine similarity, Jaccard similarity, Euclidean distance, and Pearson Coefficient. All of these are available in the `sklearn.metrics` module.

- ### Cosine similarity 

  To compute the similarity between a purchased item and the new item for an item-centered system, we simply take the cosine between 2 vectors representing those items. Cosine similarity is the best match if there are many high-dimensional features, especially in text mining.
  
  ![image](https://user-images.githubusercontent.com/35486320/197948973-eac44063-b797-4441-aed9-f1e2d8275f08.png)

- ### Jaccard similarity

  Jaccard similarity is the size of the intersection divided by the size of the union of two sets of items.
  
  ![image](https://user-images.githubusercontent.com/35486320/197949149-38c2892f-8df6-4097-874b-4d9e8e2b00fd.png)

- ### Euclidean distance

  It is the distance between two users in a user-centered system is the length of the line segments connecting them. Based on user ratings we search for items liked by users with similar tastes. The lower the distance between two persons, the higher the chance they like similar items.
  
  ![image](https://user-images.githubusercontent.com/35486320/197949306-41932be6-fa70-492c-a642-0b67afa5bfdc.png)
