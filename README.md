# SearchDialog
仿bilibili搜索框效果(只需要三句话即可实现)

先看预览图(转换后有一点点失真):

<img src="https://github.com/wenwenwen888/SearchDialog/blob/master/preview/1.gif" width="30%" height="30%">

前言
-------
1,支持搜索历史(已经做了数据库存储了)

2,基本与bilibili的搜索效果差不多了

3,需要修改更多内容可以下载library自己修改

4,本人非大牛,有不妥之处请Issues指出,谢谢

5,参考了该po的[文章](http://lhunter.org/2016/08/06/%E4%BB%BF%20Bilibili%20%E6%90%9C%E7%B4%A2%E6%95%88%E6%9E%9C/) ,感谢


Usage
--------

With Gradle:
```groovy
   1.在Project的build.gradle中加入
 // jitPack仓库地址
        maven{ url "https://jitpack.io" }
        如下：
        allprojects {
               repositories {
                   jcenter()
                   maven { url 'https://jitpack.io' }
               }
           }
   2.在app的build.gradle中加入
    compile 'com.github.Blankwhiter:SearchDialog:1.0.0'（可到该项目的release中看最后的版本）
```


How to use
--------
第一句 , 实例化:
```java
 SearchFragment searchFragment = SearchFragment.newInstance();
```
第二句 , 设置回调:
```java
 searchFragment.setOnSearchClickListener(new IOnSearchClickListener() {
            @Override
            public void OnSearchClick(String keyword) {
                //这里处理逻辑
                Toast.makeText(ToolBarActivity.this, keyword, Toast.LENGTH_SHORT).show();
            }
        });
```
第三句 , 显示搜索框:
```java
  searchFragment.show(getSupportFragmentManager(),SearchFragment.TAG);
```
第四句 , 设置搜索框提示:
 ```java
   searchFragment.setKeywordHint("你需要设置的提示");
 ```

