//Given an array of integers A and an integer B, find and return the maximum value K 
//such that there is no subarray in A of size K with sum of elements greater than B.


/*
Input Format
The first argument given is the integer array A.
The second argument given is integer B.

Output Format
Return the maximum value of K (sub array length).

Constraints
1 <= length of the array <= 100000
1 <= A[i] <= 10^9
1 <= B <= 10^9
*/


int isKTrue(vector<long long> &v,int k,int B)
{
    int n=v.size();
    long long last=0;
    for(int i=0;i<n-k+1;i++)
    {
        int end=i+k-1;
        long long sum=(v[end]-last);
        if(sum>B)
            return 0;
        last=v[i];
    }
    return 1;
}
int Solution::solve(vector<int> &A, int B) {
    int n=A.size();
    vector<long long> v(n);
    v[0]=A[0];
    for(int i=1;i<n;i++)
    {
        v[i]=v[i-1]+A[i];
    }
    int l=1;
    int r=n;
    while(l<=r)
    {
        int k=l+(r-l)/2;
        if(isKTrue(v,k,B))
        {
            if(k==n||!isKTrue(v,k+1,B))
            {
                return k;
            }
            else
            {
                l=k+1;
            }
        }
        else
        {
            r=k-1;
        }
        
    }
    return 0;
}
