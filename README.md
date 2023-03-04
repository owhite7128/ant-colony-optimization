# C Implementation of Ant Colony Optimization

## Example of using the headers.
```C
    #include "ants.h"
    int main () {
        int coords_len = 11;
        int coords_arr[11][2] = {{0,0}, {0,1}, {1,0}, {1,1}, {2,1}, {1,2}, {3,4}, {5,2}, {5,6}, {2,3}, {22,12}};
        int ant_num = 10;
        int gen_num = 10;
        WEB new_web = instatiate_web(coords_len, coords_arr);
        ANT* ants;

        for (int i=0; i<gen_num; i++)
        {
            ANT* ants = new_ants(new_web, ant_num);
            walk (ants, ant_num, &new_web);
            destroy_ants (ants, ant_num);
        }

        out_best_path (new_web);
        return 0;
    }
 ```