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
  List<List<Integer>> values = new ArrayList<>();

  public List<List<Integer>> levelOrder(Node root) {
    nlevelorder(Arrays.asList(root));
    return values;
  }

  private void nlevelorder(List<Node> nodes) {
    if (nodes != null) {
      List<Integer> level = new ArrayList<>();
      List<Node> children = new ArrayList<>();
      for (Node node : nodes) {
        if (node != null) {
          level.add(node.val);
          children.addAll(node.children);
        }
      }
      if (!level.isEmpty()) {
        values.add(level);
      }
      if (!children.isEmpty()) {
        nlevelorder(children);
      }
    }
  }
}

```