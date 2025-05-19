import java.util.*;

public class BellmanFord{
    static class Edge{
        int from, to, weight;
        Edge(int from, int to, int weight){
            this.from=from;
            this.to=to;
            this.weight=weight;
        }
    }

    public static boolean bellmanFord(int v, List<Edge> edges, int source, int[] dist){
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[source]=0;

        for(int i=0;i<v-1;i++){
            for(Edge edge:edges){
                if(dist[edge.from] != Integer.MAX_VALUE &&
                   dist[edge.from]+edge.weight < dist[edge.to]){
                   dist[edge.to] = dist[edge.from] + edge.weight;
                }
            }
        }

        for(Edge edge:edges){
            if(dist[edge.from] != Integer.MAX_VALUE &&
               dist[edge.from]+edge.weight < dist[edge.to]){
               return false;
            }
        }
        return true;
    }

    public static void main(String[] args){
        int v=5;
        List<Edge> edges=new ArrayList<>();

        edges.add(new Edge(0, 1, -1));
        edges.add(new Edge(0, 2, 4));
        edges.add(new Edge(1, 2, 3));
        edges.add(new Edge(1, 3, 2));
        edges.add(new Edge(1, 4, 2));
        edges.add(new Edge(3, 2, 5));
        edges.add(new Edge(3, 1, 1));
        edges.add(new Edge(4, 3, -3));

        int[] dist=new int[v];
        boolean hasNoNegativeCycle=bellmanFord(v, edges, 0, dist);

        if(hasNoNegativeCycle){
            System.out.println("Shortest distance from source 0:");
            for(int i=0;i<v;i++){
                System.out.println("To node "+i+" = "+dist[i]);
            }
        }
        else{
            System.out.println("Graph contains a negative weight cycle.");
        }
    }
}
