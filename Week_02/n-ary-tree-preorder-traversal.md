```java
/*
// Definition for a Node.
class Node {
    public int val;
    public List<Node> children;

    public Node() {}

    public Node(int _val) {
        val = _val;
    }

    public Node(int _val, List<Node> _children) {
        val = _val;
        children = _children;
    }
};
*/

import java.util.ArrayList;
import java.util.Arrays;

class Solution {
  private List<Integer> values = new ArrayList<>();

  public List<Integer> preorder(Node root) {
    npreorder(root);
    return values;
  }

  private void npreorder(Node node) {
    if (node != null) {
      values.add(node.val);
      npreorder(node.children);
    }
  }

  private void npreorder(List<Node> nodes) {
    if (nodes != null) {
      for (Node node : nodes) {
        npreorder(node);
      }
    }
  }
}

```