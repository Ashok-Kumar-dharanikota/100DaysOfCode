// Online Java Compiler
// Use this editor to write, compile and run your Java code online

class HelloWorld {
    
    public static boolean isPolindrome(String text) {
        String revText  = "";
        
        for(int i=text.length()-1; i>=0; i--) {
            revText = revText + text.charAt(i);
        }
        
        return text.equals(revText);
    }
    
    public static int isNumberPolindrome(int num) {
        
        int reverse = 0;
        while(num >0) {
        reverse = reverse*10 + num%10;
        num = num/10;
        }
        
        return reverse;
    }
    
    public static boolean isPrimeNumber(int num) {
        
        for(int i=2; i< Math.sqrt(num); i++) {
            if(num%i ==0){
                return false;
            }
        }
        
        return true;
    }
    
    public static boolean isAmstrongNum(int num) {
        String resNum = Integer.toString(num);
        
        return true;
    }
    
    public static void main(String[] args) {
        
        String text  = "abba";
        int num = 11;
        System.out.println(isPrimeNumber(num));
    }
    
    
    
    
}