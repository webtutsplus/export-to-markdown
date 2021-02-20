
## Solve Leetcode Problems and Get Offers From Your Dream Companies

1423. **Maximum Points You Can Obtain from Cards**

In this series, I am going to solve Leetcode medium problems live with my friends, which you can see on our youtube channel, Today we will do Problem Leetcode: 1423. **Maximum Points You Can Obtain from Cards.**

![](https://cdn-images-1.medium.com/max/2560/1*NnlSQcwN8weJcadNuKuGLg.png)

A little bit about me, I have offers from **Uber** **India** and **Amazon** **India** in the past, and I am currently working for **Booking.com** in Amsterdam.

## Motivation to learn algorithms
[**Solve Leetcode Problems and Get Offers From Your Dream Companies**
*Introduction and Motivation Behind practicing Leetcode*medium.com](https://medium.com/leetcode-simplified/solve-leetcode-problems-and-get-offers-from-your-dream-companies-2786415be0b7)

## Problem Statement

There are several cards **arranged in a row**, and each card has an associated number of points The points are given in the integer array cardPoints.

In one step, you can take one card from the beginning or from the end of the row. You have to take exactly k cards.

Your score is the sum of the points of the cards you have taken.

Given the integer array cardPoints and the integer k, return the *maximum score* you can obtain.

**Example 1:**

    **Input:** cardPoints = [1,2,3,4,5,6,1], k = 3
    **Output:** 12
    **Explanation:** After the first step, your score will always be 1. However, choosing the rightmost card first will maximize your total score. The optimal strategy is to take the three cards on the right, giving a final score of 1 + 6 + 5 = 12.

**Example 2:**

    **Input:** cardPoints = [2,2,2], k = 2
    **Output:** 4
    **Explanation:** Regardless of which two cards you take, your score will always be 4.

**Example 3:**

    **Input:** cardPoints = [9,7,7,9,7,7,9], k = 7
    **Output:** 55
    **Explanation:** You have to take all the cards. Your score is the sum of points of all cards.

**Example 4:**

    **Input:** cardPoints = [1,1000,1], k = 1
    **Output:** 1
    **Explanation:** You cannot take the card in the middle. Your best score is 1.

**Example 5:**

    **Input:** cardPoints = [1,79,80,1,1,1,200,1], k = 3
    **Output:** 202

## **Youtube Discussion**
youtube:https://medium.com/media/b2a422d7d6bd59ae0c470f17e46e9b6c

## **Solution**

We will discuss two approaches, the first one will give **TIME LIMIT EXCEEDED** and the second one will be accepted.

According to the question, we can choose a card from either the beginning or the end and we need to repeat this step till we get k cards.

**Base Cases:**

 1. If k is less than 1 then no cards can be chosen

2. i should be always less than j

3. If i equal to j and k=1 , then we have to choose i -th card.

**Recursion Step:**

So for an array from i to j , with k cards to be drawn,

if we choose the card from the beginning then ar[i]+choose from (i+1) to j

if we choose the card from the end then ar[j]+choose from (i) to (j-1)

To avoid the same calculations, we can use dynamic programming.We can store the value for i to j with k cards to be drawn in a dictionary.
{% gist https://gist.github.com/sksaikia/10ea71990b58e8733d740824ed3a8774.js %}
This solution is not that efficient and will give **TIME LIMIT EXCEEDED.**

Let’s talk about the optimal solution for this problem. We have to k cards either from the beginning or the end. Therefore we can choose

0 cards from left and k cards from right

1 card from left and (k-1) cards from right

2 cards from left and (k-2) cards from right

.............

k cards from left and 0 cards from right

Therefore, we need to find the maximum of these combinations. To make our calculations simpler, we can store the cumulative sum of first k cards from beginning and end. We can find the maximum for all these combinations ;

left[i]+right[k-i] for all possible values of i (k is given)
{% gist https://gist.github.com/sksaikia/8007504665d3e8b2f505b49568693af1.js %}
The code for this problem can be found in the following repository.
[**webtutsplus/LeetCode**
*Contribute to webtutsplus/LeetCode development by creating an account on GitHub.*github.com](https://github.com/webtutsplus/LeetCode/tree/main/src/LC1423_MaximumPointsObtainedFromCards)

## Thank You for reading and Follow this publication for more LeetCode problems!😃
[**LeetCode Simplified**
*We are going to solve Leetcode problems live, which you can watch on our youtube channel*medium.com](https://medium.com/leetcode-simplified)
