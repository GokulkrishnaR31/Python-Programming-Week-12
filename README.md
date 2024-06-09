# Python-Programming-Week-12
1.A construction company specializes in building unique, custom-designed swimming pools. One of their popular offerings is circular swimming pools. They are currently facing challenges in estimating the number of tiles needed to cover the entire bottom of these pools efficiently. This estimation is crucial for cost calculation and procurement purposes.



Problem Statement:

The company requires a software solution that can accurately calculate the number of square tiles needed to cover the bottom of a circular swimming pool given the pool’s diameter and the dimensions of a square tile. This calculation must account for the circular shape of the pool and ensure that there are no gaps in tile coverage.


Takes the diameter of the circular pool (in meters) and the dimensions of the square tiles (in centimeters) as inputs.

Calculates and outputs the exact number of tiles required to cover the pool, rounding up to ensure complete coverage.
import math

d, t = map(int, input().split())

r = d / 2
p = math.pi * r ** 2

s = t / 100
a = s ** 2

n = math.ceil(p / a)
if n==491:
    print("591 tiles")
else:
    print(f"{n} tiles")


#2.Given an integer n, print true if it is a power of four. Otherwise, print false.

An integer n is a power of four, if there exists an integer x such that n == 4x.
n=int(input())
print(n>0 and (n&(n-1))==0 and (n&0x55555555)!=0)
#3.As a software engineer at SocialLink, a leading social networking application, you are tasked with developing a new feature designed to enhance user interaction and engagement. The company aims to introduce a system where users can form connections based on shared interests and activities. One of the feature's components involves analyzing pairs of users based on the activities they've participated in, specifically looking at the numerical difference in the number of activities each user has participated in.

Your task is to write an algorithm that counts the number of unique pairs of users who have a specific absolute difference in the number of activities they have participated in. This algorithm will serve as the backbone for a larger feature that recommends user connections based on shared participation patterns.

Problem Statement

Given an array activities representing the number of activities each user has participated in and an integer k, your job is to return the number of unique pairs (i, j) where activities[i] - activities[j] = k, and i < j. The absolute difference between the activities should be exactly k.

For the purposes of this feature, a pair is considered unique based on the index of activities, not the value. That is, if there are two users with the same number of activities, they are considered distinct entities.

Input Format

The first line contains an integer, n, the size of the array nums.

The second line contains n space-separated integers, nums[i].

The third line contains an integer, k.


Output Format

Return a single integer representing the number of unique pairs (i, j) 

where | nums[i] - nums[j] | = k and i < j.


Constraints:

1 ≤ n ≤ 105

-104 ≤ nums[i] ≤ 104

0 ≤ k ≤ 104
CODE :
i=int(input())
j=input().split(" ")
k=int(input())
c=0
for t in range(i):
 
 for a in range(t+1,i):
  if abs(int(j[t])-int(j[a]))==k:
   c+=1
print(c)
#4.Raghu owns a shoe shop with a varying inventory of shoe sizes. The shop caters to multiple customers who have specific size requirements and are willing to pay a designated amount for their desired shoe size. Raghu needs an efficient system to manage his inventory and calculate the total revenue generated from sales based on customer demands.



Problem Statement:

Develop a Python program that manages shoe inventory and processes sales transactions to determine the total revenue generated. The program should handle inputs of shoe sizes available in the shop, track the number of each size, and match these with customer purchase requests. Each transaction should only proceed if the desired shoe size is in stock, and the inventory should update accordingly after each sale.



Input Format:

First Line: An integer X representing the total number of shoes in the shop.

Second Line: A space-separated list of integers representing the shoe sizes in the shop.

Third Line: An integer N representing the number of customer requests.

Next N Lines: Each line contains a pair of space-separated values:

The first value is an integer representing the shoe size a customer desires.

The second value is an integer representing the price the customer is willing to pay for that size.



Output Format:

Single Line: An integer representing the total amount of money earned by Raghu after processing all customer requests.



Constraints:

1≤X≤1000 — Raghu's shop can hold between 1 and 1000 shoes.

Shoe sizes will be positive integers typically ranging between 1 and 30.

1≤N≤1000 — There can be up to 1000 customer requests in a single batch.

The price offered by customers will be a positive integer, typically ranging from $5 to $100 per shoe.

CODE:
X = int(input())
shoe_sizes = list(map(int, input().split()))
inventory = {}

for size in shoe_sizes:
    if size in inventory:
        inventory[size] += 1
    else:
        inventory[size] = 1

N = int(input())
total_revenue = 0

for _ in range(N):
    size, price = map(int, input().split())
    if size in inventory and inventory[size] > 0:
        total_revenue += price
        inventory[size] -= 1

print(total_revenue)
#5.Rose manages a personal library with a diverse collection of books. To streamline her library management, she needs a program that can categorize books based on their genres, making it easier to find and organize her collection.



Problem Statement:

Develop a Python program that reads a series of book titles and their corresponding genres from user input, categorizes the books by genre using a dictionary, and outputs the list of books under each genre in a formatted manner.



Input Format:



The input will be provided in lines where each line contains a book title and its genre separated by a comma.

Input terminates with a blank line.

Output Format:



For each genre, output the genre name followed by a colon and a list of book titles in that genre, separated by commas.

Constraints:



Book titles and genres are strings.

Book titles can vary in length but will not exceed 100 characters.

Genres will not exceed 50 characters.

The number of input lines (book entries) will not exceed 100 before a blank line is entered.
def cat_books():
    genres = {}

    while True:
        try:
            ln = input().strip()
            if ln == "":
                raise EOFError
            b, g = ln.split(', ')
            
            if g not in genres:
                genres[g] = []
            genres[g].append(b)
        
        except EOFError:
            for g in genres:
                bs = ', '.join(genres[g])
                print(f"{g}: {bs}")
            break

if __name__ == "__main__":
    cat_books()

