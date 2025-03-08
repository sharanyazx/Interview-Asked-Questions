# Insertion Sort 
```` java []
import java.util.*; 
class Node {

    int val;

    Node next;

    Node(int val) {

        this.val = val;

        this.next = null;

    }

}

public class Main {

    public static Node insertionSortList(Node head) {
        if (head == null) return null;
        Node sorted = null;
        while (head != null) {
            Node current = head;
            head = head.next;
            if (sorted == null || sorted.val >= current.val) {

                current.next = sorted;

                sorted = current;

            } else {

              Node temp = sorted;

                while (temp.next != null && temp.next.val < current.val) {

                    temp = temp.next;

                }

                current.next = temp.next;

                temp.next = current;

            }

        }

        return sorted;

    }

    

    public static void printList(Node head) {

        while (head != null) {

            System.out.print(head.val + " ");

            head = head.next;

        }

        System.out.println();

    }

    

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);



     System.out.print("Enter the number of elements in the linked list: ");

        int n = scanner.nextInt();

        

        if (n < 0) {

            System.out.println("Invalid input");

            return;

        }

        

       Node head = null;
       Node tail = null;



  System.out.print("Enter the elements of the linked list: ");

        for (int i = 0; i < n; i++) {

            int value = scanner.nextInt();

            Node newNode = new Node(value);

            if (head == null) {

                head = newNode;

                tail = newNode;

            } else {

                tail.next = newNode;

                tail = newNode;

            }

        }

 
        head = insertionSortList(head);

        printList(head); 


        scanner.close();

    }

}

````
# Output
```
Enter the number of elements in the linked list: 5
Enter the elements of the linked list: 1
2
8
4
6
1 2 4 6 8 

```

# SQL Queries 

