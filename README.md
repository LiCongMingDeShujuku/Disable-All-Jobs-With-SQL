![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 禁用SQL Server中的所有作业
#### Delete All Jobs With SQL
**发布-日期: 2014年04月14日 (评论)**

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
你可以使用此快速脚本禁用所有作业。

## English
Here’s a quick you can use to disable all Jobs.

---
## Logic
```SQL
-- to disable all jobs run this.
-- 运行此段代码禁用所有的作业。
use msdb;
set nocount on
declare @disable_all_jobs varchar(max)
set @disable_all_jobs = ”
select @disable_all_jobs = @disable_all_jobs +
‘sp_update_job @job_name = ”’ + name + ”’, @enabled = ”0”’ + char(10) + ‘go’ + char(10) from sysjobs
exec (@disable_all_jobs)
go

-- to enable all the jobs just run this. 
-- 运行此段代码启用所有的作业。
use msdb;
set nocount on
declare @enable_all_jobs varchar(max)
set @enable_all_jobs = ”
select @enable_all_jobs = @enable_all_jobs +
‘sp_update_job @job_name = ”’ + name + ”’, @enabled = ”1”’ + char(10) + ‘go’ + char(10) from sysjobs
exec (@enable_all_jobs)
go


```

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

