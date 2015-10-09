---
layout: post
title: Longest Increase Sequence
---

#### Solution one O(NxN)
use a table to store the longest increase sequence number at **current index**

```
int lis(vector<int>& data){
    if(data.size() == 0)return -1;

    vector<int> table(data.size(),1);

    for(int i = 1;i < data.size();++i){
    	
    	for(int j = 0;j < i;++j){
    		if(data[i] > data[j]){
    			table[i] = table[j] + 1;
    		}
    	}
    }

    return *max_elemet(table.begin(),table.end());
}
```

#### Solution two O(Nxlog(N))
use a table to store the **minimal maximum** value of a LIS with length n
for example:
    table[2] stores the minimal (maximum value of a LIS with length of 2 + 1)

```
int lis(vector<int>& data){
    if(data.size() == 0)return -1;

    int res = 1;
    int curLen;
    //vector<int> table(data.size(),1);
    vector<int> Max(data.size(),0);
    
    Max[0] = data[0];

    for(int i = 1;i < data.size();++i){
	curLen = 1;
	for(int j = res;j >= 1;--j){
	    if(data[i] > Max[j - 1]){
		curLen = j + 1;
		break;
	    }
	}

	if(curLen > res){
	    res = curLen;
	    Max[curLen - 1] = data[i];
	}else{
	    if(data[i] < Max[curLen - 1] && (curLen - 2 < 0 || data[i] > Max[curLen - 2])){
		Max[curLen - 1] = data[i];
	    }
	}
    }
    return res;
}
```
#### Reference
Beauty of Programming Page 196
