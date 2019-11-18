` /** 处理地址 **/
	const address = res.data.result.address
	// * 表示零到多个字符串，+ 表示一到多个字符
	const provinceExp = '.+?(省|自治区|行政区)'
	const cityExp = '.+?(市|盟|自治州|地区|区划|县)'
	const countryExp = '.+?(区|县|旗|镇|市|乡)'
	const province = address.match(new RegExp(provinceExp)) ? address.match(new RegExp(provinceExp))[0] : ''
	const city = address.match(new RegExp(cityExp)) ? address.match(new RegExp(cityExp))[0].replace(province, '') : ''
	const country = address.replace(province, '').replace(city, '').match(new RegExp(countryExp)) ? address.replace(province, '').replace(city, '').match(new RegExp(countryExp))[0] : ''
	const street = country ? address.replace(province, '').replace(city, '').replace(country, '') : ''`

