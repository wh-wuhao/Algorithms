# Algorithms
An array of n positive distinct integers, a = [1, 5, 3, 4, 2]
An integer, k = 2. 
Find pairs of elements, where the difference of the pair is k. Found the following three pairs: (1, 3), (5, 3), and (4, 2). 
Thus, we return 3 as our answer.

Solution:
int kDifference(vector <int> a, int k) {
    sort(a.begin(), a.end());
    int res = 0;
    for (int i=0; i<a.size()-1; i++){
        int l=i+1, r=a.size()-1;
        while(l<=r){
            int mid = (l+r)>>1;
            if (a[mid]-a[i] == k) {res++; break;}
            if (a[mid]-a[i] > k) {r=mid-1;}
            else l=mid+1;
        }
    }
    return res;
}
