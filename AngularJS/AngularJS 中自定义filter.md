AngularJS 中自定义filter
---

### Fiter
`filter`作用很多，比如可以用来进行排序，搜索等等，`AngularJS`也提供了很多内置的`filter`，可以查阅文档进行学习使用。



### 自定义函数作为filter
如果需要的`filter`内部逻辑比较复杂，不方便用一条语句进行计算，考虑使用函数。
如在视图上有:

```javascript
<tr ng-repeat="user in userData | filter:filterUserBySearch">
	<td> ... </td>
</tr>
```
想对`userData`上的不同`field`进行搜索过滤，如根据用户id、用户名等等，那么可以将函数定义为(其中`$scope.searchUser` 和 `$scope.search_user` 是用了控制搜索条件的变量):

```javascript
$scope.filterUserBySearch = function(value, index, array){
		if($scope.searchUser === 'All' && $scope.search_user){
			return JSON.stringify(value).indexOf($scope.search_user) >= 0;
		}else if($scope.searchUser === 'Id' && $scope.search_user){
			//Search by id
			return value['id'].indexOf($scope.search_user) >= 0;
		}else if($scope.searchUser === 'Name' && $scope.search_user){
			//Search By Name
			return value['name'].indexOf($scope.search_user) >= 0;
		}else{
			return true;
		}
	}
```

函数的三个参数含义一目了然，返回值就是true和false，这也就是最简单的过滤结果，为true就表示匹配，否则就不匹配。上面的条件只要是搜索的字符串包含在当前item中就匹配，这也是很多`AngularJS`自带过滤器的匹配条件，可以根据需要自行设定。

> 原创文章，转载请注明出处！