function($scope,$http,snRecordWatcher,$rootScope) {
  /* widget controller */
  var c = this;
	c.data.loading = true;
	c.data.table = c.options.table || "incident";
	c.data.query = c.options.query || "";
	c.data.template = c.options.template || "task-category";
	function getData(){
	$http.get('/api/now/table/'+c.data.table+'?sysparm_query='+c.data.query).success(function(response){
		c.data.loading=false;
		c.data.list = response.result;
		$rootScope.$broadcast("K17ListWidgetUpdated",c.data.list);
	})
	}
	getData();
	
	snRecordWatcher.initList(c.data.table, c.data.query);
	$scope.$on('record.updated', function(name, data) {
		getData();
	});
}
