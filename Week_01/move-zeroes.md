```java
class Solution {
  public void moveZeroes(int[] nums) {
    loopAndCountZero(nums);
  }

  private void loopAndCountZero(int[] nums) {
    int count = 0;
    for (int i = 0; i < nums.length - 1; i++) {
      if (nums[i] == 0) {
        count++;
        if (nums[i + 1] == 0) {
          continue;
        } else {
          nums[i] = nums[i + 1];
          nums[i + 1] = 0;
          count--;
        }
      }
    }
    for (int a = 0; a < count; a++) {
      for (int i = 0; i < nums.length - 1; i++) {
        if (nums[i] == 0) {
          if (nums[i + 1] == 0) {
            continue;
          } else {
            nums[i] = nums[i + 1];
            nums[i + 1] = 0;
          }
        }
      }
    }
  }

  private void doublePoint(int[] nums) {
    for (int i = 0, j = 0; i < nums.length; i++) {
      if (nums[i] != 0) {
        nums[j] = nums[i];
        if (j != i) {
          nums[i] = 0;
        }
        j++;
      }
    }
  }
}

```