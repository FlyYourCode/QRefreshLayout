# QRefreshLayout
this is a custom layout with refresh and loadmore function for android

how to use:
1.gradle
dependencies {
    compile 'q.rorbin:QRefreshLayout:1.0.1'
}

2.xml
<q.rorbin.qrefreshlayout.QRefreshLayout
    android:id="@+id/refreshlayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <ListView
        android:id="@+id/listview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</q.rorbin.qrefreshlayout.QRefreshLayout>

3.code
  
  if you want loadmore, call this funcation
  
  mRefreshLayout.setLoadMoreEnable(true);

  then 
  
  mRefreshLayout.setRefreshHandler(new RefreshHandler() {
            @Override
            public void onRefresh(QRefreshLayout refresh) {
              do something...
              mRefreshLayout.refreshComplete();
            }
            @Override
            public void onLoadMore(QRefreshLayout refresh) {
              do something...
              mRefreshLayout.LoadMoreComplete();
            }
        });

  if you If you want to custom header or footer view, create your view and extends QLoadView like this
  
  public class HeaderView extends QLoadView
  
  then
  
  mRefreshLayout.setHeaderView(new HeaderView());