```
class Solution {
    public boolean isPalindrome(String s) {
        boolean flag=true;
        if (s.equals("")) {
            return true;
        }
        /**
         * 1.先将字符串变为全部小写的
         * 2.然后进行比较
         */
        
        String str=s.toLowerCase();
        
        int length=str.length();
        int left=0;
        int right=length-1;
        char[] charStr=str.toCharArray();
        while(left<right){
            while (!Character.isLetterOrDigit(charStr[left]) && left<right) {
                left++;
            }
            while (!Character.isLetterOrDigit(charStr[right]) && left<right) {
                right--;
            }
            if (left>=right) {
                return flag;
            }
            if (charStr[left]!=charStr[right]) {
                flag=false;
                break;
            }else{
                left++;
                right--;
            }
        }
        return flag;
    }
}
```
