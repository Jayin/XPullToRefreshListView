XPullToRefreshListView
======================

A library includes three kind of useful ListView 

Library Includes
=======
* 1.PullToRefreshListView  下拉刷新
* 2.LoadMoreListView       到底部自动加载更多
* 3.PullAndLoadListView   下拉刷新+到底部自动加载更多

Feature of PullAndLoadListView  (added in 2014.1.15)
* add funcion `canLoadMore()` to help you control whetherthe data can load more and update the footView  or not 



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
    </com.coustom.widget.PullAndLoadListVieww>
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
              new Task().excute();
			 //	lv.onLoadMoreComplete(); //you must call this method when you finish your task
			}
		});
   
```

```java
class Task extends AsyncTask<Void, Void, Void> {

		@Override
		protected Void doInBackground(Void... params) {
			//do the long-time work here
			return null;
		}

		@Override
		protected void onPostExecute(Void result) {
		   // lv.canLoadMore(false);//if you found that you can't load more data(Like:page is in the end),called this method and listview won't loadmore again!
		    lv.onLoadMoreComplete()
		}

	}

```

Advanced
===
coutom layout by yourself but pay attention to the [IDs]

License
===
The MIT License (MIT)



