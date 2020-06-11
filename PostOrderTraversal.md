In this code, we have traverse the tree using PostOrderTraversal

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


    void postOrderTraversal(Node node) {

        if (node == null) {
            return;
        }
        postOrderTraversal(node.left);
        postOrderTraversal(node.right);
        System.out.print(node.data + " ");

    }

    public static void main(String[] args) {
        ImplementationOfBT implementationOfBT = new ImplementationOfBT();
        Node root = implementationOfBT.add(9);
        implementationOfBT.root = root;
        root.left = implementationOfBT.add(13);
        root.right = implementationOfBT.add(8);
        root.left.left = implementationOfBT.add(17);
        root.left.right = implementationOfBT.add(2);
        root.right.right = implementationOfBT.add(10);
        root.left.right.left = implementationOfBT.add(6);
        root.left.right.right = implementationOfBT.add(1);
        root.right.right.left = implementationOfBT.add(41);
        implementationOfBT.postOrderTraversal(root);
    }
}
```

Output - 
```
17 6 1 2 13 41 10 8 9 
```
