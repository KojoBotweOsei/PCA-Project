
---
title: "Distance & PCA Project"
author: "Kojo Botwe Ampiaw Osei"
date: "2024-03-21"
output: html_document
---

## Problem: Given two objects represented by the tuples (22, 1, 42, 10) and (20, 0, 36, 8):
## (a) Compute the Euclidean distance between the two objects.
## (b) Compute the Manhattan distance between the two objects.
## (d) Compute the Supremum distance between the two objects.

## 2. For the following asymmetric binary attributes, calculate the Jaccard coefficient (similarity)
## between following two objects:
## X = (1, 0, 0, 0, 0, 0, 0, 0, 0, 0)
## Y= (0, 0, 0, 0, 0, 0, 1, 0, 0, 1)

## 3. Calculate cosine similarity for the following two document vectors:
## X = (3, 2, 0, 5, 0, 0, 0, 2, 0, 0)
## Y = (1, 0, 0, 0, 0, 0, 0, 1, 0, 2)


# Euclidean Distance

Define a function to compute the Euclidean distance between two objects:

```{r}
euclidean_distance <- function(x, y) {
  squared_diff <- (x - y)^2
  sqrt(sum(squared_diff))
}
```

# Manhattan Distance

```{r}
manhattan_distance <- function(x, y) {
  abs_diff <- abs(x - y)
  sum(abs_diff)
}
```


# Supremum Distance


```{r}
supremum_distance <- function(x, y) {
  max(abs(x - y))
}
```



# Jaccard Similiarity
```{r}
jaccard_similarity <- function(x, y) {
  intersect_count <- sum(x & y)
  union_count <- sum(x | y)
  intersect_count / union_count
}
```


# Cosine Simliarity

```{r}
cosine_similarity <- function(x, y) {
  dot_product <- sum(x * y)
  magnitude_x <- sqrt(sum(x^2))
  magnitude_y <- sqrt(sum(y^2))
  dot_product / (magnitude_x * magnitude_y)
}
```


# Distances and Simliriaties


```{r}
object1 <- c(22, 1, 42, 10)
object2 <- c(20, 0, 36, 8)

euclidean_dist <- euclidean_distance(object1, object2)
manhattan_dist <- manhattan_distance(object1, object2)
supremum_dist <- supremum_distance(object1, object2)

X <- c(1, 0, 0, 0, 0, 0, 0, 0, 0, 0)
Y <- c(0, 0, 0, 0, 0, 0, 1, 0, 0, 1)

jaccard_sim <- jaccard_similarity(X, Y)

X <- c(3, 2, 0, 5, 0, 0, 0, 2, 0, 0)
Y <- c(1, 0, 0, 0, 0, 0, 0, 1, 0, 2)

cosine_sim <- cosine_similarity(X, Y)

```
