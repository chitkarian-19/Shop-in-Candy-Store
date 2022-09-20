# Shop-in-Candy-Store
Shop in Candy Store

This is a easy greedy problem.
Problem Statement : In a candy store, there are N different types of candies available and the prices of all the N different types of candies are provided to you.
You are now provided with an attractive offer.
You can buy a single candy from the store and get at most K other candies ( all are different types ) for free.
Now you have to answer two questions. Firstly, you have to find what is the minimum amount of money you have to spend to buy all the N different candies. Secondly, you have to find what is the maximum amount of money you have to spend to buy all the N different candies.

Code Approach: First sort the array and then just add Math.ceil(n/k+1) numbers from start to get the min amount. To get the max amount get Math.ceil(n/k+1) numbers from ending.


    static ArrayList<Integer> candyStore(int candies[],int n,int k){
        // code here
        Arrays.sort(candies);
        ArrayList<Integer> op = new ArrayList<Integer>();
        int loop = (int)Math.ceil((double)n/(k+1));
        int price =0;
        for(int i=0;i<loop;i++){
            price+=candies[i];
        }
        op.add(price);
        
        price=0;
        for(int i=n-1;i>=n-loop;i--){
            price+=candies[i];
        }
        op.add(price);
        
        return op;
    }


Practise link: https://practice.geeksforgeeks.org/problems/shop-in-candy-store1145/1
