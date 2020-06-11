This code finds out the number of nodes in O(n) time with O(1) space complexity.
We can also find the same by using queue, but it'll make our space complexity to O(n) than O(1)
```
public class GetNumberOfNodes {
    
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
    
    int getNoOfNodes(Node node) {
        if (node == null) {
            return 0;
        }
        
        return 1 + getNoOfNodes(node.left) + getNoOfNodes(node.right);
        
    }
    
    public static void main(String[] args) {
        GetNumberOfNodes numberOfNodes = new GetNumberOfNodes();
        Node root = numberOfNodes.add(9);
        numberOfNodes.root = root;
        root.left = numberOfNodes.add(13);
        root.right = numberOfNodes.add(8);
        root.left.left = numberOfNodes.add(17);
        root.left.right = numberOfNodes.add(2);
        root.right.right = numberOfNodes.add(10);
        root.left.right.left = numberOfNodes.add(6);
        root.left.right.right = numberOfNodes.add(1);
        root.right.right.left = numberOfNodes.add(41);
        System.out.println(numberOfNodes.getNoOfNodes(root));
    }
}
```

Output - 
```
9
```
