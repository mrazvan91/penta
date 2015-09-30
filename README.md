import java.util.Arrays;

/**
 *
 * @author Maldarus Razvan
 */
 
 /*
    Se da `n`, un numar pozitiv si `a` un array de numere intregi de lungime n-1, care contine numere de la 1 la n, in orice ordine. 
    Fiecare numar apare maxim o data in array (`a` nu contine duplicate). Gaseste numarul lipsa.        
*/

public class ArrayMain {
    
    public static void main(String[] args)
    {
        int n = 10;
        int[] a = {10, 8, 9, 7, 5, 1, 2, 3, 4};//Pentru numere de la 1 la 10, fara 0
        int[] a_sort = {10, 8, 9, 7, 5, 1, 2, 3, 4};//Pentru numere de la 1 la 10, fara 0
        int[] aux = new int[n+1];
        int m1 = 0, m2 = 0;
        
        
        /* Metoda 1 */
        long start_time = System.nanoTime();

        for(int i = 0 ; i < n - 1 ; i++)
            aux[ a[i] ] = 1;
        
        for(m1 = 1 ; m1 < aux.length ; m1++)
            if( aux[ m1 ] == 0 )
                break;
        
        long end_time = System.nanoTime();
        double difference1 = (end_time - start_time); ///1e6;
        
        
        /* Metoda 2 */
        long start_time2 = System.nanoTime();
        
        Arrays.sort(a_sort);
        for(m2 = 0 ; m2 < aux.length ; m2++)
            if( a_sort[ m2 ] != ( m2 + 1 ) )
                break;
        
        long end_time2 = System.nanoTime();
        double difference2 = (end_time2 - start_time2);
        
        
        /* Metoda 3 */
        long start_time3 = System.nanoTime();
        
        double expected_sum_m3 = (n * ( (n + 1) / 2.0 ) ), real_sum_m3 = 0;
        for (int i : a)
            real_sum_m3 += i; 

        double m3 = expected_sum_m3 - real_sum_m3;
        
        long end_time3 = System.nanoTime();
        double difference3 = (end_time3 - start_time3);
        
        
        /* Metoda 4 */
        long start_time4 = System.nanoTime();
        
        int expected_sum_m4 = n, real_sum_m4 = 0;  
        for (int i = 0; i < a.length; i++) {  
            expected_sum_m4 += i+1;  
            real_sum_m4 += a[i];  
        }  
        int m4 = expected_sum_m4 - real_sum_m4;  
          
        long end_time4 = System.nanoTime();
        double difference4 = (end_time4 - start_time4);
        
        
        /* Metoda 5 */
        long start_time5 = System.nanoTime();
        int m5 = n;
        for (int i = 0; i < a.length; i++)  
            m5 += i + 1 - a[i];
        
        long end_time5 = System.nanoTime();
        double difference5 = (end_time5 - start_time5);
        
        
        System.out.println("------------------------------------");
        
        System.out.println("Met1. Solutia este: " + m1);
        System.out.println("Met2. Solutia este: " + ( m2 + 1 ) );
        System.out.println("Met3. Solutia este: " + m3);
        System.out.println("Met4. Solutia este: " + m4);
        System.out.println("Met5. Solutia este: " + m5);
        
        System.out.println("------------------------------------");
        
        System.out.println("difference1: " + difference1);
        
        System.out.println("------------");

        System.out.println("difference2: " + difference2);
        
        System.out.println("------------");

        System.out.println("difference3: " + difference3);
        
        System.out.println("------------");

        System.out.println("difference4: " + difference4);
        
        System.out.println("------------");

        System.out.println("difference5: " + difference5);
        
       
    }
    		
	/* 
	output run_1
	run:
	------------------------------------
	Met1. Solutia este: 6
	Met2. Solutia este: 6
	Met3. Solutia este: 6.0
	Met4. Solutia este: 6
	Met5. Solutia este: 6
	------------------------------------
	difference1: 621.0
	------------
	difference2: 22392.0
	------------
	difference3: 622.0
	------------
	difference4: 311.0
	------------
	difference5: 311.0
	BUILD SUCCESSFUL (total time: 0 seconds)



	output run_2
	run:
	------------------------------------
	Met1. Solutia este: 6
	Met2. Solutia este: 6
	Met3. Solutia este: 6.0
	Met4. Solutia este: 6
	Met5. Solutia este: 6
	------------------------------------
	difference1: 933.0
	------------
	difference2: 33587.0
	------------
	difference3: 933.0
	------------
	difference4: 622.0
	------------
	difference5: 311.0
	BUILD SUCCESSFUL (total time: 0 seconds)



	output run_3
	run:
	------------------------------------
	Met1. Solutia este: 6
	Met2. Solutia este: 6
	Met3. Solutia este: 6.0
	Met4. Solutia este: 6
	Met5. Solutia este: 6
	------------------------------------
	difference1: 622.0
	------------
	difference2: 22391.0
	------------
	difference3: 622.0
	------------
	difference4: 622.0
	------------
	difference5: 311.0
	BUILD SUCCESSFUL (total time: 0 seconds)
	*/
    
}


