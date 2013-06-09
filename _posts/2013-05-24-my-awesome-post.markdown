---
layout: post
author: Brent
published: true
title:  "My new digital home on the web!"
date:   2013-05-24 17:52:16
categories: post
picture: "http://placekitten.com/g/870/400"
caption: "Oooh, eyeballs!"
---

This post is different and has a kitten.

{% highlight objectivec linenos %}

- (void)setUp
{
    viewController = [[BrowseOverflowViewController alloc] init];
    tableView = [[UITableView alloc] init];
    viewController.tableView = tableView;
    datasource = [[TopicTableDataSource alloc] init];
    viewController.dataSource = datasource;
    viewController.delegate = datasource;
    objc_removeAssociatedObjects(viewController);
    realViewDidAppear = @selector(viewDidAppear:);
    testViewDidAppear = @selector(browseOverflowViewControllerTests_viewDidAppear:);
    [BrowseOverflowViewControllerTests swapInstanceMethodsForClass:[UIViewController class]
                                                          selector:realViewDidAppear
                                                       andSelector:testViewDidAppear];
    
    realViewWillDisappear = @selector(viewWillDisappear:);
    testViewWillDisappear = @selector(browseOverflowViewControllerTests_viewWillDisappear:);
    [BrowseOverflowViewControllerTests swapInstanceMethodsForClass:[UIViewController class]
                                                          selector:realViewWillDisappear
                                                       andSelector:testViewWillDisappear];
    realUserDidSelectTopic = @selector(userDidSelectTopicNotification:);
    testUserDidSelectTopic = @selector(browseOverflowControllerTests_userDidSelectTopicNotification:);
    
    navController = [[UINavigationController alloc] initWithRootViewController:viewController];
    
}



{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
