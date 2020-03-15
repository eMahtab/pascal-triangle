# Pascal Triangle
# https://leetcode.com/problems/pascals-triangle

# Implementation :

```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<>();
        if(numRows < 1)
            return result;
        if(numRows >= 1) {
            List<Integer> firstRow = new ArrayList<>();
            firstRow.add(1);
            result.add(firstRow);
        }
        if(numRows >= 2) {
            List<Integer> secondRow = new ArrayList<>();
            secondRow.add(1); secondRow.add(1);
            result.add(secondRow);
        }
        
        for(int i = 3; i <= numRows; i++) {
            List<Integer> previousRow = result.get(i-2);
            List<Integer> nextRow = new ArrayList<>();
            nextRow.add(1);
            for(int j = 0; j < previousRow.size() - 1; j++) {
                nextRow.add(previousRow.get(j) + previousRow.get(j+1));
            }
            nextRow.add(1);
            result.add(nextRow);
        }
        
       return result; 
    }
}
```
