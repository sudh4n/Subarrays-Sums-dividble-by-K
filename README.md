class Solution {
public:  
    int subarraysDivByK(vector<int>& A, int K) {
        map<int,int>a;
        int sum=0, res=0, n=A.size();
        a[0]=1;
        for(int i=0;i<n;i++){
            sum += A[i];
            int rem = sum % K;
            if(rem < 0) rem += K;

            if(a.find(rem)!=a.end()){
                res += a[rem];
            }
            a[rem]++;
        }
        return res;
    }
};
