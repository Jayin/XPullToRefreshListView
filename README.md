XPullToRefreshListView
======================

A library includes three kind of useful ListView 

Library Includes
=======
* 1.PullToRefreshListView  下拉刷新
* 2.LoadMoreListView       到底部自动加载更多
* 3.PullAndLoadListView   下拉刷新+到底部自动加载更多

Install
===
1.
```shell
git clone https://github.com/Jayin/XPullToRefreshListView.git
```

2.add this library:
your own project properties -> Android —> Library "add" this project
 


Quick start(PullAndLoadListView)
===
###  Layout
```xml
      <com.coustom.widget.PullAndLoadListView
        android:id="@+id/xlistview"
        android:layout_width="match_parent"
        android:layout_height="match_parent" >
    </com.costum.android.widget.PullAndLoadListView>
```

### Activity
```java
   private PullAndLoadListView lv;
   ....
   lv =(PullAndLoadListView)findViewById(R.id.xlistview);
   ....
   lv.setOnRefreshListener(new OnRefreshListener() {

			@Override
			public void onRefresh() {
			    //start a task here
			    lv.onRefreshComplete(); //you must call this method when you finish your task
			}
		});
    ......
	lv.setOnLoadMoreListener(new OnLoadMoreListener() {

			public void onLoadMore() {
                  //start a task here
			 	lv.onLoadMoreComplete(); //you must call this method when you finish your task
			}
		});
   
```

Advanced
===
coutom layout by yourself but pay attention to the [IDs]

License
===
The MIT License (MIT)



