This is how PreOrder Traversal Works! In last code we used Inorder Traversal to traverse the Binary Tree

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
    
    void preOrderTraversal(Node node) {
        
        if (node == null) {
            return;
        }
        
        System.out.print(node.data+" ");
        preOrderTraversal(node.left);
        preOrderTraversal(node.right);
        
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
        implementationOfBT.preOrderTraversal(root);
    }
}
```
Output - 
```
2 7 12 6 5 11 5 9 4
```
