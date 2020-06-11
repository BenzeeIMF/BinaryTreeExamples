In this code, we have shown you how to implement a Binary Tree. To display items we have used InOrder Traversal!
This is Binary Tree not binary Search Tree

```
public class ImplementationOfBT {

    class Node {
        Node root, left, right;
        int data;
    }
    Node root;

    Node add(int data) {
        Node node = new Node();
        node.data = data;
        return node;
    }

    void inOrderTraversal(Node node) {
        if (node == null) {
            return;
        }

        inOrderTraversal(node.left);
        System.out.print(node.data + " ");
        inOrderTraversal(node.right);

    }

    public static void main(String[] args) {
        ImplementationOfBT implementationOfBT = new ImplementationOfBT();
        Node root = implementationOfBT.add(2);
        implementationOfBT.root = root;
        root.left = implementationOfBT.add(7);
        root.right = implementationOfBT.add(5);
        root.left.left = implementationOfBT.add(12);
        root.left.right = implementationOfBT.add(6);
        root.right.right = implementationOfBT.add(9);
        root.left.right.left = implementationOfBT.add(5);
        root.left.right.right = implementationOfBT.add(11);
        root.right.right.left = implementationOfBT.add(4);
        implementationOfBT.inOrderTraversal(root);
    }
}
```
Output - 
```
12 7 5 6 11 2 5 4 9 
```
