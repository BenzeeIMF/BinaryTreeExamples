This code finds out the sum of all nodes in O(n) time complexity and O(1) space complexity!
We can solve this question using Queue also. But it'll make the space complexity of O(n) instead of O(1)

```
public class GetSumofAllNodes {
    
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
    
    int sumOfAllNodes(Node node) {
        
        if (node == null) {
            return 0;
        }
        
        return node.data + sumOfAllNodes(node.left) + sumOfAllNodes(node.right);
        
    }
    
    public static void main(String[] args) {
        GetSumofAllNodes sumofAllNodes = new GetSumofAllNodes();
        Node root = sumofAllNodes.add(9);
        sumofAllNodes.root = root;
        root.left = sumofAllNodes.add(13);
        root.right = sumofAllNodes.add(8);
        root.left.left = sumofAllNodes.add(17);
        root.left.right = sumofAllNodes.add(2);
        root.right.right = sumofAllNodes.add(10);
        root.left.right.left = sumofAllNodes.add(6);
        root.left.right.right = sumofAllNodes.add(1);
        root.right.right.left = sumofAllNodes.add(41);
        System.out.println(sumofAllNodes.sumOfAllNodes(root));
    }
    
}

```
Output - 
```
107
```
