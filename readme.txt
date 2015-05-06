Handlebars 笔记

1.访问父级的属性 [../]：
"spe_data": [
	{
		"spe_tpl": "spe_radios",
		"spe_Rname": "myRadios01",
		"spe_childArray": [
			{"spe_name":"单件A", "rad_val":"0", "isChecked":"checked"},
			{"spe_name":"单件B", "rad_val":"1"}
		]
	},

	{
		"spe_tpl": "spe_checkbox",
		"spe_childArray": [
			{"spe_name":"单件AA", "rad_val":"0", "isChecked":"checked"}
		]
	}

],
如在此代码是我们如下操作，
	{{#each spe_childArray}}
		<label>
			<input name="{{spe_Rname}}" value="{{rad_val}}" type="radio" style="position: relative; top: 3px; margin: 0 3px;" {{#if isChecked}}checked{{/if}}>{{spe_name}}
		</label>
	{{/each}}	
那么name="{{spe_Rname}}"是无法获得的，我们可以使用 name="{{../spe_Rname}}"来访问上级元素