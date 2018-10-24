# calendar
js实现日历,原生js实现当年日志
核心代码：

function getCalemder(mon){
			var TheMon = {'Year':Year,'Mon':mon} //当月
			var LastMon = getLastMon(mon) //上一个月
			var TheMonDay = getDateMonDay(TheMon) //当月多少天 
			var LastMonDay = getDateMonDay(LastMon) //上个月多少天
			var theMonWeek = weekData[new Date(TheMon.Year + '-' + TheMon.Mon + '-01').getDay()] //判断属于星期几，然后获取当月的1号是在date数组中，下标是多少
			var EndDayNum = TheMonDay + theMonWeek
			for(var i = 0; i < date.length; i++){
				var day = i+1 //因为数组从0 开始,为了对应天数，所以需要加1
				if(i<theMonWeek){
					day = LastMonDay - theMonWeek + day
				}else if (theMonWeek <= i && i < EndDayNum) {
					day = day - theMonWeek
				}else if(EndDayNum <= i){
					day = day - EndDayNum
				}
				date[i] = day
			}
			console.log(date)
		}



