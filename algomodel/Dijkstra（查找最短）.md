import java.util.*;
public class Dijkstra {
    public static void main(String[] args) {
        // 示例：节点数为 5
        int n = 5;
        // 调用 Dijkstra 算法，从节点 1 出发
        dijkstra(n, 1);}
    /**
     * Dijkstra算法实现
     * @param  n 节点总数（节点编号 1~n）
     * @param start 起点节点
     */
     static void dijkstra(int n, int start) {
        // 1. 初始化邻接表
         List<int[]>[] g = new ArrayList[n + 1];//这里是数组嵌套列表嵌套数组的三层结构第一层是节点位置，列表的存在是方便邻接表，列表里面每个数组都是两个元素第一个是后节点，第二个元素是前节点到后节点的距离
        for (int i = 1; i <= n; i++) {
            g[i] = new ArrayList<>();循环分配节点
        }
        // 【可选】这里可以添加边，示例：节点1→2，权值3；节点1→3，权值1；节点2→4，权值2；节点3→4，权值5
        g[1].add(new int[]{2, 3});
        g[1].add(new int[]{3, 1});
        g[2].add(new int[]{4, 2});
        g[3].add(new int[]{4, 5});
        // 2. 初始化距离数组和优先队列
        int[] dist = new int[n + 1];
        Arrays.fill(dist, Integer.MAX_VALUE);//初始全部无穷大距离
        dist[start] = 0;
        // 优先队列：按距离从小到大排序，存储格式为 [节点编号, 当前距离],括号里面放排序器方法
        PriorityQueue<int[]> pq = new PriorityQueue<>(Comparator.comparingInt(a -> a[1]));
        pq.offer(new int[]{start, 0});//初始化最初距离
        // 3. Dijkstra 主循环
        while (!pq.isEmpty()) {
            int[] cur = pq.poll();将最小的距离拿出来放到一个中间数组
            int u = cur[0];//当前的节点位置
            int d = cur[1];//当前节点的距离
            // 如果当前距离不是已知的最短距离，跳过
            if (d != dist[u]) {
                continue;}
            // 遍历 u 的所有邻接边
            for (int[] e : g[u]) {
                int v = e[0];//邻接边的节点
                int w = e[1];//邻接边的距离
                // 防止整数溢出：如果 dist[u] 是无穷大，就不更新，当前节点的距离加上邻接距离
                if (dist[u] != Integer.MAX_VALUE && dist[v] > dist[u] + w) {
                    dist[v] = dist[u] + w;更新
                    pq.offer(new int[]{v, dist[v]});更新距离数组的数据
                }
            }
        }
        // 输出结果：从起点到各节点的最短距离
        System.out.println("从节点 " + start + " 出发的最短距离：");
        for (int i = 1; i <= n; i++) {
            System.out.println("到节点 " + i + "：" + (dist[i] == Integer.MAX_VALUE ? "不可达" : dist[i]));
        }
    }
}
