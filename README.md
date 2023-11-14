# Find-All-Numbers-Disappeared-in-an-Array-using-Java-Leetcode


    class Solution {
        public static void swap(int[] arr, int i , int correct){
            int temp;
            temp = arr[i];
            arr[i] = arr[correct];
            arr[correct]= temp;
    
        }
        public static void sort(int[] arr){
            int i =0; 
            while(i<arr.length){
                int correct = arr[i]-1;
                if(i<arr.length & arr[i]!=arr[correct]){
                    swap(arr,i,correct);
                }else{
                    i++;
                }
            }
        }
        public List<Integer> findDisappearedNumbers(int[] nums) {
            Solution obj = new Solution();
            obj.sort(nums);
            List<Integer> li = new ArrayList<>();
            for(int i =0; i<nums.length;i++){
                if(nums[i] != i+1){
                    li.add(i+1);   
                }
            }
            return li;
        }
    }
