## UIScrollView+XSState

给 UIScrollView、UITableView、UICollectionView 展示状态信息（比如：加载中、数据为空、加载失败、网络异常等）

## 为什么重复造轮子

给UITableView展示空数据的有[DZNEmptyDataSet](https://github.com/dzenbot/DZNEmptyDataSet)、[LYEmptyView](https://github.com/dev-liyang/LYEmptyView)，都为开发者提供了常见的提示UI，但使用起来比较繁琐，需要对其提供的UI进行定制。  

## UIScrollView+XSState设计原则
-  保持精简，源代码只有100行左右。
-  使用方便，提供的接口少。
-  提供扩展，开发者可任意定制任何状态的下的UI。

## 使用
**在设置state前，需要设置state对应的view**，state对应的view完全有开发者提供。
提供两种设置view的方式：  

-  全局设置  
-  局部设置

局部设置的优先级高于全局设置。

``` objc
[UIScrollView setClass:[CustomEmptyView class] forState:XSScrollViewStateEmpty];
[UIScrollView setClass:[CustomLoadingView class] forState:XSScrollViewStateLoading];
[UIScrollView setClass:[CustomFailedView class] forState:XSScrollViewStateFailed];
```
