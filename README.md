# Personal-java-notes

*For each with collections

import java.util.Collection;
import java.util.List;
import java.util.ArrayList;

public class ForeachDemo {
  static void iterate(Collection<String> c) {
      for (String s : c)
      System.out.println(s);
  }
  public static void main(String args[]) {
    List<String> l = new ArrayList<String>();
    l.add("Toronto");
    l.add("Stockholm");
    iterate(l);
  }
}


*The foreach(for each) loop is essentially read-only.


public class MainClass {
  public static void main(String args[]) {
    int nums[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    for (int x : nums) {
      System.out.print(x + " ");
      x = x * 10; // no effect on nums
    }

    System.out.println();

    for (int x : nums)
      System.out.print(x + " ");

    System.out.println();
  }
}

Question: This is the snippet of Java code: 
  
int[][] uu = new int[1][1];
uu[0][0] = 5;
for(int[] u: uu){
    System.out.println(u[0]);
}
  
It prints 5. But why does the declaration part of for loop is declared as int[] u, but not as int[][] u?

  
Answer: Since your uu is an array of array. So, when you iterate over it, you will first get an array, and then you can iterate over that array to get individual elements. So, your outer loop has int[] as type, and hence that declaration. If you iterate through your u in one more inner loop, you will get the type int: -

for (int[] u: uu) {
    for (int elem: u) {
        // Your individual element
    }
}
           
