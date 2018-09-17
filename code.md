    //全选全不选
$(function(){
	var flag = true;
    $("#checkall").click(function() {
        var cb = $("input[name='drugadd']");
        for(var i = 0; i < cb.length; i++) {
            cb[i].checked = flag;
        }
            flag = !flag;
    });
});
   $(function(){
	$("#queren").click(function(){
		var supplier_name = $("#gongyingshangming").val();
		var contact_phone = $("#lianxirenshouji").val();
		var contact_name  = $("#lianxirenming").val();
		var contact_telephone = $("#lianxidianhua").val();
		var setup_time = $("#chuangjianriqi").val();
		var bank_card  = $("#yinhangkahao").val();
		var supplier_address = $("#gongyinshangdizhi").val();
		var id = $("#pid").val();
		$.ajax({
			type: 'post',
			url: '/yladmin/drug/dobianji',
			data: {
				id : id,
				supplier_name : supplier_name,
				contact_phone : contact_phone,
				contact_name  : contact_name,
				contact_telephone : contact_telephone,
				setup_time : setup_time,
				bank_card  : bank_card,
				supplier_address : supplier_address,
			},
			cache: true,
			dataType: 'json',
			error: function(XMLHttpRequest, textStatus, errorThrown) {
				alert("保存失败！");
			},
			success: function(data) {
				window.location.href = '/yladmin/drug/drug_supplier';
			}
	});
})
})
```
