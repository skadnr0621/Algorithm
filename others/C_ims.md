``` java
import java.util.*;
import java.io.*;

public class Main {
    /**
     * 2022 ICPC sinchon summer algorithm camp contest open
     * */
    public static void main(String[] args) throws IOException{
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());
        int tired = Integer.parseInt(st.nextToken());
        int n = Integer.parseInt(st.nextToken());
        int[] jewel = new int[n];
        StringTokenizer st2 = new StringTokenizer(br.readLine());
        for(int i=0; i<n; ++i){
            jewel[i] = Integer.parseInt(st2.nextToken());
        }
        Arrays.sort(jewel);
        int j=0;
        int cnt=0;
        while(tired<200 && j<n && cnt<=n){
            tired+=jewel[j];
            ++j;
            ++cnt;

        }
        System.out.println(cnt);
        br.close();
    }
}

```

