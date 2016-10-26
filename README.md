Reproduces issue in databinding.

Steps:

1. check out repo, build and run
2. check out branch add-res
3. build and run (without cleaning)
4. rotate device, crashes

TLDR:
```
./gradlew installDebug && git checkout add-res && ./gradlew installDebug
```

```
 10-26 16:54:54.406 9400-9400/tatarka.me.databindingissue E/AndroidRuntime: FATAL EXCEPTION: main
                                                                           Process: tatarka.me.databindingissue, PID: 9400
                                                                           android.view.InflateException: Binary XML file line #2: Error inflating class layout
                                                                               at android.view.LayoutInflater.createViewFromTag(LayoutInflater.java:757)
                                                                               at android.view.LayoutInflater.inflate(LayoutInflater.java:482)
                                                                               at android.view.LayoutInflater.inflate(LayoutInflater.java:414)
                                                                               at android.databinding.DataBindingUtil.inflate(DataBindingUtil.java:116)
                                                                               at android.databinding.DataBindingUtil.inflate(DataBindingUtil.java:88)
                                                                               at tatarka.me.databindingissue.MainActivity$1.onCreateViewHolder(MainActivity.java:25)
                                                                               at android.support.v7.widget.RecyclerView$Adapter.createViewHolder(RecyclerView.java:6073)
                                                                               at android.support.v7.widget.RecyclerView$Recycler.getViewForPosition(RecyclerView.java:5243)
                                                                               at android.support.v7.widget.RecyclerView$Recycler.getViewForPosition(RecyclerView.java:5153)
                                                                               at android.support.v7.widget.LinearLayoutManager$LayoutState.next(LinearLayoutManager.java:2061)
                                                                               at android.support.v7.widget.LinearLayoutManager.layoutChunk(LinearLayoutManager.java:1445)
                                                                               at android.support.v7.widget.LinearLayoutManager.fill(LinearLayoutManager.java:1408)
                                                                               at android.support.v7.widget.LinearLayoutManager.onLayoutChildren(LinearLayoutManager.java:580)
                                                                               at android.support.v7.widget.RecyclerView.dispatchLayoutStep2(RecyclerView.java:3374)
                                                                               at android.support.v7.widget.RecyclerView.dispatchLayout(RecyclerView.java:3183)
                                                                               at android.support.v7.widget.RecyclerView.onLayout(RecyclerView.java:3627)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.widget.RelativeLayout.onLayout(RelativeLayout.java:1076)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.widget.FrameLayout.layoutChildren(FrameLayout.java:579)
                                                                               at android.widget.FrameLayout.onLayout(FrameLayout.java:514)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.support.v7.widget.ActionBarOverlayLayout.onLayout(ActionBarOverlayLayout.java:437)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.widget.FrameLayout.layoutChildren(FrameLayout.java:579)
                                                                               at android.widget.FrameLayout.onLayout(FrameLayout.java:514)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.widget.LinearLayout.setChildFrame(LinearLayout.java:1703)
                                                                               at android.widget.LinearLayout.layoutVertical(LinearLayout.java:1557)
                                                                               at android.widget.LinearLayout.onLayout(LinearLayout.java:1466)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.widget.FrameLayout.layoutChildren(FrameLayout.java:579)
                                                                               at android.widget.FrameLayout.onLayout(FrameLayout.java:514)
                                                                               at android.view.View.layout(View.java:15689)
                                                                               at android.view.ViewGroup.layout(ViewGroup.java:5040)
                                                                               at android.view.ViewRootImpl.performLayout(ViewRootImpl.java:2116)
                                                                               at android.view.ViewRootImpl.performTraversals(ViewRootImpl.java:1873)
```
