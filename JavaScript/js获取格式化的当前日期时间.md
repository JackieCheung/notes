**获取格式化的当前日期时间**

`getNowFormatDate () {
	const seperator1 = '-'
	const seperator2 = ':'
	const date = new Date()
	const year = date.getFullYear()
	let month = date.getMonth() + 1
	let day = date.getDate()
	let hour = date.getHours()
	let minute = date.getMinutes()
	let second = date.getSeconds()
	month = month >= 1 && month <= 9 ? '0' + month : month
	day = day >= 1 && day <= 9 ? '0' + day : day
	hour = hour >= 0 && hour <= 9 ? '0' + hour : hour
	minute = minute >= 0 && minute <= 9 ? '0' + minute : minute
	second = second >= 0 && second <= 9 ? '0' + second : second
	return year + seperator1 + month + seperator1 + day + ' ' + hour + seperator2 + minute + second
}`

