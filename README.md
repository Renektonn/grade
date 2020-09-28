//excel成績

import java.util.Scanner;
class Main {
  
  
  static void output(Student [] numStu , int num){
    
    System.out.printf("%-10s","num");
    System.out.printf("%-10s","Chinese");
    System.out.printf("%-10s","Math");
    System.out.printf("%-10s","English");
    System.out.printf("%-10s","average");
    System.out.println();

    
    for(int i = 1;i <= num;i++){
      System.out.printf("%10d",i);
      System.out.printf("%10d",numStu[i].Chinese);
      System.out.printf("%10d",numStu[i].Math);
      System.out.printf("%10d",numStu[i].English);
      System.out.printf("%10.2f",numStu[i].average);
      System.out.println();
    }
  }

  static void input(Student [] numStu , int num){
    
    Scanner cin = new Scanner (System.in);
    for(int i = 1;i <= num;i++){
      int Chinese = cin.nextInt();
      int Math    = cin.nextInt();
      int English = cin.nextInt();
      numStu[i] = new Student(Chinese , Math , English);
    }
  }

  public static void main(String[] args) {
    
    
    Student [] numStu = new Student [10+1];
    input(numStu,10);
    output(numStu,10);
    

    
  }

}
class Student{
  int Chinese;
  int Math;
  int English;
  double average;
  int rank;
  
  public Student(int Chinese , int Math , int English){
    this.Chinese = Chinese;
    this.Math = Math;
    this.English = English;
    this.average = (Chinese + Math + English)/3.0; 
  }

}
