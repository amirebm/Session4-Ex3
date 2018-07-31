//برنامه ایی بنوسید که دو آرایه از ورودی گرفته و آنها را در یک آرایه دیگر به صورت مرتب شده نمایش دهد  



# Session4-Ex3

package com.personal.Ex3;
import java.util.Scanner;

public class Ex3 {

	
	static int arX[];
	static int arY[];
	static int arrayLengthX, arrayLengthY;
    static int arrayLengthXY;
    static int[] arXY= new int [arrayLengthXY];
    
    
	public static void main(String[] args) {
	
		
		Scanner sc= new Scanner(System.in);
		System.out.println("Enter the size of the first array");
		arrayLengthX=sc.nextInt();
		arX= new int[arrayLengthX];
		
		System.out.println("Enter the size of the Second array");
		arrayLengthY=sc.nextInt();
		arY= new int[arrayLengthY];
		arrayLengthXY=(arrayLengthY+arrayLengthX);
		arXY= new int[arrayLengthXY];
        
		System.out.println("Please enter "+ arrayLengthX+ " numbers for array X :");
		
		for (int i = 0; i < arrayLengthX; i++) {
			arX[i]=sc.nextInt();	
			arXY[i]=arX[i];
						}
		
        System.out.println("Now Please enter "+ arrayLengthY+ " numbers for array Y :");
		
		for (int i = 0; i < arrayLengthY; i++) {
			arY[i]=sc.nextInt();
			arXY[i+(arrayLengthX-1)]=arY[i];
						}
		System.out.println("Tarkibe 2 araye be soorate moratab nashode");
        printArray(arXY);
		System.out.println("******************************************");
		System.out.println("Tarkibe 2 araye be soorate moratab SHODE");
        mergeSort(arXY, 0, arrayLengthXY-1);
        printArray(arXY);
        }	
	
	
		static void merge(int[] arXY, int low, int middle, int high) {
			
			int x=middle-low+1;
			int y=high-middle;
			
			int L[]=new int[x];
			int R[]=new int[y];
			
			for (int i=0; i<x; ++i)
	            L[i] = arXY[low+ i];
	        for (int j=0; j<y; ++j)
	            R[j] = arXY[middle + 1+ j];
	 
			int i=0,j=0;
			int k= low;
			while(i< x&& j<y) {
				
				if(L[i]<=R[j]) {
					arXY[k]=L[i];
				i++;}
				else {
					arXY[k]=R[j];
				j++;
				}
				k++;
				
			}
			while(i<x) {
				arXY[k]=L[i];
				i++;
				k++;
						
			}
			while(j<y) {
				arXY[k]=R[j];
				j++;
				k++;
						
			}
			
			}
						
        static void mergeSort(int[]arXY,int low,int high) {
	
	     if(low<high) {
	    	 int middle= (low+high)/2;
			mergeSort(arXY ,low, middle);
	     	mergeSort(arXY, middle+1, high);
		merge(arXY, low,middle, high);
		
	     }
        }
        
        static void printArray(int arr[])
        {
            int n = arr.length;
            for (int i=0; i<n; ++i)
                System.out.print(arr[i] + " ");
            System.out.println();
        }
        }
