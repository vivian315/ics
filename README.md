Mac或iPhone自带「提醒事项」和「日历」应用，用来管理日常日程很方便， 自带的中国节假日有24节气和节假日，但不含节假日的补班调休等。

那么，如何在Mac或者iOS系统自带日历软件中加入中国节假日以及法定假期补班调休日历呢？
方法有
方法一：自己参照国务院每年发布的假期详情去编辑自己的本地日历，从Mac上导入，通过iCloud同步到手机
方法二：导入或者订阅一些第三方平台已经做好的日历模块，但容易被植入广告

本文介绍方法一的如何自定义日历
大家可以下载日历ics文件模版自己定义然后导入即可

```基本的ics文件格式
BEGIN:VCALENDAR                 #iCalendar 文件由以BEIGIN开始，以END结尾的部分组成。 VCALENDAR 用于容纳其他所有部分。 
                                #包括：VEVENT：用于定义事件	VALARM：用于定义提醒 VTODO：用于待办事项	VJOURNAL：用于日志条目 VTIMEZONE：用于时区信息的
VERSION:2.0                     #版本号，一般保留2.0即可
X-WR-CALNAME:                   #日历名称，如：2021中国大陆法定节假日
X-APPLE-CALENDAR-COLOR:         #日历配色，例如#E16B8C 
X-WR-TIMEZONE:                  #时区，例如Asia/Beijing
BEGIN:VEVENT                    #日历事件
UID:2021-0101-0001              #事件ID，需唯一
DTSTART;VALUE=DATE:20210101     #开始时间，格式YYYYMMDD**T**HHMMSS
DTEND;VALUE=DATE:20210103
SUMMARY:元旦假期
SEQUENCE:0
BEGIN:VALARM
TRIGGER;VALUE=DATE-TIME:19760401T005545Z
ACTION:NONE
END:VALARM
END:VEVENT
END:VCALENDAR 
```
