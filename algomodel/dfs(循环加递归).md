//
// Source code recreated from a .class file by IntelliJ IDEA
// (powered by Fernflower decompiler)
//

import java.util.ArrayList;
import java.util.List;

public class Permutations {
    List<List<Integer>> result = new ArrayList();
    public List<List<Integer>> permute(int[] nums) {
        boolean[] used = new boolean[nums.length];
        this.dfs(nums, used, new ArrayList());
        return this.result;
    }
    void dfs(int[] nums, boolean[] used, List<Integer> path) {
        if (path.size() == nums.length) {
            this.result.add(new ArrayList(path));
        } else {
            for(int i = 0; i < nums.length; ++i) {
                if (!used[i]) {
                    used[i] = true;
                    path.add(nums[i]);
                    this.dfs(nums, used, path);
                    path.remove(path.size() - 1);
                    used[i] = false;
                }
            }
        }
    }
    public static void main(String[] args) {
        Permutations solution = new Permutations();
        int[] nums = new int[]{1, 2, 3};
        List<List<Integer>> res = solution.permute(nums);
        System.out.println("[");
        for(List<Integer> list : res) {
            System.out.println("  " + String.valueOf(list));
        }
        System.out.println("]");
    }
}
