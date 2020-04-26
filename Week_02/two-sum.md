```java
class Solution {
  public int[] twoSum(int[] nums, int target) {
    return sigleHashMap(nums, target);
  }

  private int[] loopAll(int[] nums, int target) {
    for (int i = 0; i < nums.length - 1; i++) {
      for (int j = i + 1; j < nums.length; j++) {
        if (nums[i] + nums[j] == target) {
          return new int[] {i, j};
        }
      }
    }
    return new int[0];
  }

  private int[] doubleHashMap(int[] nums, int target) {
    Map<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
      map.put(nums[i], i);
    }
    for (int i = 0; i < nums.length; i++) {
      int anthor = target - nums[i];
      Integer anthorIndex = map.get(anthor);
      if (anthorIndex != null && anthorIndex != i) {
        return new int[] {i, anthorIndex};
      }
    }
    return new int[0];
  }

  private int[] sigleHashMap(int[] nums, int target) {
    Map<Integer, Integer> map = new HashMap<>();
    for (int i = 0; i < nums.length; i++) {
      Integer anotherIndex = map.get(target - nums[i]);
      if (anotherIndex != null) {
        return new int[] {i, anotherIndex};
      }
      map.put(nums[i], i);
    }
    return new int[0];
  }
}

```