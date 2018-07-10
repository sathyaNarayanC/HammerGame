

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.*;
public class javaapplication2 {
     static int aa = 0;
    static String[][] w ;
    public static int fact(int n){
       if (n == 0)    
    return 1;    
  else    
    return(n * fact(n-1));    
    }
    
    public static String[][] permute(String[] a, int k, int len,  int factLen) 
    {
        if (k == a.length){
                if(aa < factLen){
                for(int j = 0; j < len; j++)
                    {
                        w[aa][j] = a[j];
                    }
                    aa++;
                }
        } 
        else{
            for (int i = k; i < a.length; i++) 
            {
                String temp = a[k];
                a[k] = a[i];
                a[i] = temp;
 
                permute(a, k + 1, len, factLen);
 
                temp = a[k];
                a[k] = a[i];
                a[i] = temp;
            }
        }
        return w;
    }
    
    public static void main(String args[]) throws IOException {
        Scanner scanner = new Scanner(System.in);
        BufferedReader input = new BufferedReader(new InputStreamReader(System.in));
        System.out.println("Enter N value");
        int n;
         n = Integer.parseInt(input.readLine());
        
        System.out.println("Enter M value");
        int m = Integer.parseInt(input.readLine());
        
        String Mm[] = new String[n];
        System.out.println("Enter the N number of values of weapons");
        for(int i = 0; i < n ; i++)
            Mm[i] = input.readLine();
            
        int len = Mm.length;
        //System.out.println(len);
        
        int factLen = fact(len);
        //System.out.println(factLen);
            
        w = new String[factLen][len];    
            
        String[][] wArr = permute(Mm,0,len,factLen);
        
        int rowVal;
        int sum;
        int totalSum[] = new int[factLen];
        int k;
        int sume= 0;
        int x;
        
        for(int i = 0; i< factLen;i++){
            
            sume = 0;
            boolean boo[] = new boolean[m];
            for(int j = 0; j < m ; j++){
                k =0;
                sum = 0;
                x = 0;
                while(k < (m + (m-1))){
                    if(k == 0 || k %2 == 0){
                       rowVal = Integer.parseInt(wArr[i][j].substring(k,k+1));
                    if(rowVal == 1 && !boo[x]){
                        sum += 1;
                        boo[x] = true;
                    }
                    x++;
                }
                k++;
            }
                sume += sum * sum;
            }
            totalSum[i] =  sume;
        }
        
        int smallestDist =0;
        for(int i= 0;i< totalSum.length;i++){
            if(i == 0)
                smallestDist = totalSum[0];
            else if(totalSum[i] < smallestDist)
                smallestDist  = totalSum[i];
        }
        System.out.println(smallestDist);
    }
}
