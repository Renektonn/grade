//excel成績

import java.util.Scanner;
class Main {
  
  public static void main(String[] args) {
    Scanner cin=new Scanner(System.in);
    
    Student [] stu = new Student [10+1];
    
    for(int i = 1;i <= 3;i++){
      int Chinese=cin.nextInt();
      int Math=cin.nextInt();
      int English=cin.nextInt();
      stu[i] = new Student(Chinese , Math , English);
    }

    for(int i = 1;i <= 3;i++){ // compute rank
      for(int j = i + 1;j <=3 ;j++){
        if(stu[i].fakeAverage < stu[j].fakeAverage){
          int tem = stu[i].fakeAverage;
          stu[i].fakeAverage = stu[j].fakeAverage;
          stu[j].fakeAverage = tem;
        }
      }
    }
    for(int i=1;)

    System.out.printf("%-10s","num");
    System.out.printf("%-10s","Chinese");
    System.out.printf("%-10s","Math");
    System.out.printf("%-10s","English");
    System.out.printf("%-10s","average");
    System.out.println();

    for(int i = 1;i <= 3;i++){
      System.out.printf("%10d",i);
      System.out.printf("%10d",stu[i].Chinese);
      System.out.printf("%10d",stu[i].Math);
      System.out.printf("%10d",stu[i].English);
      System.out.printf("%10.2f",stu[i].average);
      System.out.println();
    }
  }

}
class Student{
  int Chinese;
  int Math;
  int English;
  double average;
  double fakeAverage;
  int rank;
  
  public Student(int Chinese , int Math , int English){
    this.Chinese = Chinese;
    this.Math = Math;
    this.English = English;
    this.average = (Chinese + Math + English)/3.0; 
    this.fakeAverage=average;
  }

}
