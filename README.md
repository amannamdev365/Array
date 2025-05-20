//  Two sum problem array
// tc o(n^2)
bool twoSum(vector<int>& arr, int target) {
        int i;
        for(int j=0;j<arr.size();j++){
            for(int i=j+1;i<arr.size();i++){
                if(arr[j]+arr[i]==target){
                    return true;
                }
            }
        }
        return false;
    }



// better is hash map
like q (2,0),(3,1) then this become the optimum



// optimum
//tc = O(n)+O(nlogn)    sc=O(1)
    bool twoSum(vector<int>& arr, int target) {
        int n=arr.size();
    int left=0,right=n-1;
    sort(arr.begin(),arr.end());
    while(left<right){
        int sum=arr[left]+arr[right];
           if(sum==target){
              return true;
    }
        else if(sum<target) left++;
        else right--;
    }
     return false;
    }



    // # maximum/largest consecutive onews
     int findMaxConsecutiveOnes(vector<int>& nums) {
        int maxi=0;
        int count=0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]==1){
                count++;
                maxi=max(maxi,count);
            }
            else{
                count=0;
            }
        }
        return maxi;
    }



    int findMaxConsecutiveOnes(vector<int>& nums) {
    int maxi = 0;    // Stores the maximum number of consecutive 1s found so far
    int count = 0;   // Current count of consecutive 1s

    for (int i = 0; i < nums.size(); i++) {
        if (nums[i] == 1) {
            count++;                      // Count the current 1
            maxi = max(maxi, count);      // Update maximum if current count is higher
        } else {
            count = 0;                    // Reset count if a 0 is found
        }
    }
    return maxi; // Return the maximum streak of 1s
}


// sort 0s,1s,2s (sort colour) tc=o(2N) sc O(1)
void sortColors(vector<int>& nums) {
      int count0=0,count1=0,count2=0; 
      for(int i=0;i<nums.size();i++){
        if(nums[i]==0)  count0++;
        else if(nums[i]==1) count1++;
        else count2++;
      }
      for(int i=0;i<count0;i++) nums[i]=0;
      for(int i=count0;i<count0+count1;i++) nums[i]=1;
      for(int i=count0+count1;i<nums.size();i++) nums[i]=2;
    }

