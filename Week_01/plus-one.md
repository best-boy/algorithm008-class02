```java
class Solution {
    public int[] plusOne(int[] digits) {
    
        if(digits.length==0||digits[0]==0){
            return new int[]{1};
        }
        for(int i=digits.length-1;i>=0;i--){       
                if(digits[i]<9){
                    digits[i]+=1;
                    return digits;
                } else{
                    digits[i]=0;
                }
         }
        if(digits[0]==0){
            int[]temp =new int[digits.length+1];
            temp[0]=1;
            for(int i=1;i<temp.length;i++){
                temp[i]=digits[i-1];
            }
            return temp;
        }
        
        return digits;
    }
}
```