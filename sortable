var begin=0;
// 点击表头选择列排序
$('th').click(function() {
	if (begin==0) {
		begin=1;
	} else {
		begin=0;
	}
	sortTable($(this).index());
})

// 交换行
function swaprow(i,k) {
	var tb=$('tbody').find('tr');
	$(tb).eq(i).insertBefore($(tb).eq(k));
	tb=$('tbody').find('tr');
	//需要对tb进行跟新，否则tb里没有一行的顺序是不会改变的
	$(tb).eq(k).insertBefore($(tb).eq(i));
}

// 对列元素进行比较并排序
function sortTable(col) {
	var str='td:eq('+col+')';
	var arry=$('tbody tr').find(str);
	for (var i=0; i<arry.length-1; i++) {
		for (var j=i; j<arry.length; j++) {
			if ((begin==0&&arry.eq(i).text()>arry.eq(j).text())
				||begin==1&&arry.eq(i).text()<arry.eq(j).text()) {
				var temp;
				temp = arry[i];
				arry[i]=arry[j];
				arry[j]=temp;
				swaprow(i,j);
			}
		}
	}
}
