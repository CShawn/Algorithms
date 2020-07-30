# 2-排序

排序需对元素进行两两比较，将元素交换至适当的位置，排序的抽象方法如下：

```text
public class Example {
    public static void sort(Comparable[] a) { 
        // 具体的实现
    }

     private static boolean less(Comparable v, Comparable w) { 
         return v.compareTo(w) < 0;
     }

    private static void exch(Comparable[] a, int i, int j) {
        Comparable t = a[i];
        a[i] = a[j];
        a[j] = t;
    }

     private static void show(Comparable[] a) {
         // Print the array, on a single line.
        for (int i = 0; i < a.length; i++)
            System.out.println(a[i] + " ");
    }

    public static boolean isSorted(Comparable[] a) {
         // Test whether the array entries are in order.
        for (int i = 1; i < a.length; i++)
            if (less(a[i], a[i-1])) return false;
        return true;
    }

    public static void main(String[] args) { 
         // Read strings from standard input, sort them, and print.
        String[] a = In.readStrings();
        sort(a);
        assert isSorted(a);
        show(a);
    }
}
```

