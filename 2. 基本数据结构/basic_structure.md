# 第二章：基础数据结构
## 栈

- 包含min函数的栈
  
- 编辑器
  
- 火车进栈
  
- 火车进出栈问题
  
- 直方图中的最大矩形
  
  

> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## 队列

- 小组队列

- 蚯蚓

- 双端队列

- 最大子序和

  

> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## 链表与邻接表

- 邻值查找

  


> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## Hash表

- 字符串哈希

  - base 通常选131，1331
  - mod 选择 2^64 则无需取模，取模运算较慢
  
- 雪花雪花

- 兔子与兔子

- 回文串的最大长度

- 后缀树组

  

> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## 字符串

- 字符串哈希

  - base 通常选131，1331
  - mod 选择 2^64 则无需取模，取模运算较慢

- 周期

  

> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## Trie

- 前缀统计

- 最大异或对

- 最长异或值路径

  

> 小标题

```

```



> 小标题

```

```



> 小标题

```

```



## 二叉堆

- 超市

- 序列

- 数据备份

- 合并果子

- 荷马史诗

  

> 小标题

```

```



> 小标题

```

```



> 小标题

```
#include <bits/stdc++.h>

using namespace std;

vector<string> split_string(string);
vector<vector<int>>stu;
vector<vector<int>>gus;

/*
 * Complete the guestTable function below.
 */
void guestTable(vector<int> generosities) {
    cout<<"guestTable:"<<endl;
    for(int i = 0; i < generosities.size(); i++)
    {
        cout<<generosities[i]<<" ";
    }
    cout<<endl;
}

/*
 * Complete the solve function below.
 */
void solve() {
    /*
     * Write your code here.
     */

}

int main()
{
    for (int tc_itr = 0; tc_itr < tc; tc_itr++) {
        string mn_temp;
        getline(cin, mn_temp);

        vector<string> mn = split_string(mn_temp);

        int m = stoi(mn[0]);

        int n = stoi(mn[1]);
        
        
        cout<<m<<" "<<n<<endl;

        vector<vector<int>> charm(m);
        for (int charm_row_itr = 0; charm_row_itr < m; charm_row_itr++) {
            charm[charm_row_itr].resize(n);

            for (int charm_column_itr = 0; charm_column_itr < n; charm_column_itr++) {
                cin >> charm[charm_row_itr][charm_column_itr];
            }

            cin.ignore(numeric_limits<streamsize>::max(), '\n');
        }
        
        stu = charm;
        cout<<"charm:"<<endl;
        for(int i = 0; i < charm.size(); i ++)
        {
            for(int j = 0; j < charm[i].size(); j ++)
            {
                cout<<charm[i][j]<<" ";
            }
            cout<<endl;
        }
        cout<<endl;
        
        int t;
        cin >> t;
        cin.ignore(numeric_limits<streamsize>::max(), '\n');

        for (int t_itr = 0; t_itr < t; t_itr++) {
            int x;
            cin >> x;
            cin.ignore(numeric_limits<streamsize>::max(), '\n');

            string generosities_temp_temp;
            getline(cin, generosities_temp_temp);

            vector<string> generosities_temp = split_string(generosities_temp_temp);

            vector<int> generosities(x);

            for (int generosities_itr = 0; generosities_itr < x; generosities_itr++) {
                int generosities_item = stoi(generosities_temp[generosities_itr]);

                generosities[generosities_itr] = generosities_item;
            }

            guestTable(generosities);
        }

        int k;
        cin >> k;
        cin.ignore(numeric_limits<streamsize>::max(), '\n');

        solve();
    }

    return 0;
}

vector<string> split_string(string input_string) {
    string::iterator new_end = unique(input_string.begin(), input_string.end(), [] (const char &x, const char &y) {
        return x == y and x == ' ';
    });

    input_string.erase(new_end, input_string.end());

    while (input_string[input_string.length() - 1] == ' ') {
        input_string.pop_back();
    }

    vector<string> splits;
    char delimiter = ' ';

    size_t i = 0;
    size_t pos = input_string.find(delimiter);

    while (pos != string::npos) {
        splits.push_back(input_string.substr(i, pos - i));

        i = pos + 1;
        pos = input_string.find(delimiter, i);
    }

    splits.push_back(input_string.substr(i, min(pos, input_string.length()) - i + 1));

    return splits;
}

```

