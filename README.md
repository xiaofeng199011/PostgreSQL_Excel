# PostgreSQL_Excel
PostgreSQL_Excel
psql -h localhost -p 5432 -U postgres
hostname:port:database:username:password

环境变量 path =D:\Software\pgsql\bin
系统变量 pgdata=D:\Software\pgsql\data   pghome=D:\Software\pgsql
初始化数据库 initdb -D D:\Software\pgsql\data -U postgres -A password -E utf8 --locale=C -W
命令参数说明
-D   data        指定初始化的数据库目录
-U   postgres    数据库超级用户名
-A   password    数据库使用密码授权
-E   utf8        数据库编码格式
-W               命令行执行后 输入密码

修改配置
postgresql.conf    listen_addresses ='localhost' 改成 listen_addresses ='*'
pg_hba.conf        
host all all 127.0.0.1/32  trust
host all all 0.0.0.0/0     md5
host all all 0.0.0.0/0     trust


shutdown.exe -s -t 7200

数据入湖 平台界面 F12 查找
fieldcode     slotlabelEn

pip install -i http://mirrors.tools.huawei.com/pypi/simple/ --trusted-host mirrors.tools.huawei.com 
pip install "C:\Users\xwx1160778\postgresql" https://github.com/roksela/postgresql-csv-loader
pip install notebook
pip install pip==22.3.1 
jupyter notebook

python 获取安装目录
>>> import sys
>>> print(sys.path)
pip list
pip show -f spyder                列出包信息
pip list -o -i                    源安装
pip install -r requirements.txt   批量安装模块
pip install --upgrade name        升级模块
pip install -U name
pip freeze 
pip freeze > D:/pip.txt           导出模块到txt
pip uninstall -r D:/pip.txt -y    卸载txt记录的模块

get-process -name *notepad*
ls | Select-Object Mode,Name | Export-Csv ~/desktop/test.csv
CMD  tasklist /m   >> d:/1.txt

Node.js 在连接到 PostgreSQL
cd cd D:\Code\node
npm init 
npm install pg
npm install express 
npm install express -g 
npm i D:\Code\node\express-locallibrary-tutorial 本地按照包
npm start express-locallibrary-tutorial          启动本地包
npm install -g pg --registry=https://mirrors.tools.huawei.com/npm/ 
npm list -g
npm uninstall express -g
var express = require('express'); 应用本地包
npm cache clean

安装源配置
prefix=D:\Code\node_global
cache=D:\Code\node_cache
no-proxy=.huawei.com
registry=https://cmc.centralrepo.rnd.huawei.com/npm
@nce:registry=https://npm.cloudartifact.dgg.dragon.tools.huawei.com/artifactory/api/npm/npm-nce/
@gdd:registry=https://npm.cloudartifact.dgg.dragon.tools.huawei.com/artifactory/api/npm/npm-nce/
@cloudsop:registry=https://npm.cloudartifact.dgg.dragon.tools.huawei.com/artifactory/api/npm/npm-cloudsop/
@wnoss:registry=https://npm.cloudartifact.dgg.dragon.tools.huawei.com/artifactory/api/npm/npm-mae/
@mae:registry=https://npm.cloudartifact.dgg.dragon.tools.huawei.com/artifactory/api/npm/npm-mae/
strict-ssl=false

ABI函数
满足条件的计算
iif(and(col['id']=='完成',col['id']=='完'),1,0)
iif(or(col['id']=='P1',col['id']=='P2',col['id']=='P3'),1,0)
iif((col['id']<col['id']) || (col['id']>col['id']),1,0)

ABI报表传参用法 站点，大区筛选
<dc>       and name_cn in           (?{dc})</dc>
<region> and dc_region_name_cn in (?{region})</dcregion>

ABI参数使用法
<bbq_m> ?{bbq_m} as cm,
to_char(to_date(?{bbq_m} || '-01', 'yyyy-mm-dd') - interval '1' month,'yyyy-mm') as lm
</bbq_m>

ABI参数使用法
select * from A 
<Pr>  where name=?{Pr}  </Pr>     /*Pr是参数名可以任意指定*/
with para as (select <_USER_> substr(?{_USER_}, 1, 1) as name </_USER_> from dual)
select * from Coffee <Pr> where product=?Pr </Pr>   Pr是参数名

ABI月份脚本
param['下月']=dateAdd(param["年月"],'month',-1);

去重计数
DistinctCount(col['id'])

distinct dc

获取数据集访问权限
with para as (select 'h00449593' as name from dual)  00648031
explain select * from A

URL跳转链接设置
1 新建列跳转地址
2 跳转URL到列名称 新建列
'http://eops-cloud.huawei.com/eticket/framework/?active=order&decodeutf8=true&number='+col['id']

cmd命令
dir    查看当前目录下的所有文件
cd     进入到指定的目录
.      表示当前目录
..     表示上一级目录
md     创建一个目录
rd     删除一个目录    
del    删除一个文件
cls    清除屏幕

help 帮助信息
\help select   关键字帮助
\q    退出
\h
\?
\c test
\l
\x               扩展显示
\i C:/Desktop/temp.sql 正常
\i C:\Desktop\temp.sql 报错
\d  table_name     表名显示表结构
\d+ table_name     
\d *
\timing on       打开查询所用时间
\i 
\echo hello word
\pset            设置输出格式
\pset boder0 ,1,2
\dt+ week

设置数据库字符编码
show client_encoding;
set client_encoding='gbk';
set client_encoding='utf8';
\encoding gbk
自动提交回滚
begin;
commit;      事务，使用commit命令提交所有的更改
rollback;)   事务，使用rollback命令撤消所有的更改
sql 流程控制语句 begin  end语句介绍
关闭自动提交
\set autocommit off

数据库中导入csv数据 先在数据库创建表，然后copy  from
数据导入注意事项 列序要一致，首列是主键
create table ups(
   name text primary key not null,
   dcname          text);
导入数据
\copy upsstsq1 from 'c:\upsstsq1.csv' delimiter ',' csv encoding 'utf8';

导出查询结果
\copy ecmdb to '/1.csv' csv header;
\copy (select * from pg_tables) to '/temp/data.csv' 

弹窗导入数据并重新命名导入表名称
import os
import tkinter
from tkinter import simpledialog
import pandas
from sqlalchemy import create_engine
import win32ui
dlg = win32ui.CreateFileDialog(1)  #1表示打开文件对话框
dlg.SetOFNInitialDir('D:/')    #打开默认目录
dlg.DoModal()
file = dlg.GetPathName()           #获取选择的文件名称
df = pandas.read_excel(file)
postgres_engine = os.getenv("postgres_engine")
engine = create_engine('postgresql+psycopg2://postgres:1@localhost/postgres')
root=tkinter.Tk()                 #弹窗输入数据库表名
table_name=simpledialog.askstring(title='表', prompt='PostgreSQL数据库表名称：') 
df.to_sql(table_name, engine)
print(df)
print('表名：',table_name)
root.mainloop()

Python链接数据库
import psycopg2
conn = psycopg2.connect(database="postgres", user="postgres", password="1", host="localhost", port="5432")
cursor = conn.cursor()
sql = "SELECT VERSION()"
cursor.execute(sql)
data = cursor.fetchone()
print("database version : %s " % data)
conn.commit()
conn.close()

import win32ui
dlg=win32ui.CreateFileDialog(1)
dlg.SetOFNInitialDir('D:/Code')  # 设置打开文件对话框中的初始显示目录
dlg.DoModal()
file = dlg.GetPathName() 
print(file)

import os
import tkinter
from tkinter import simpledialog
root=tkinter.Tk()
entery_str=simpledialog.askstring(title='表名', prompt='输入表名称')
print('表名：',entery_str)
root.mainloop()


查询所有系统表、视图
表的列(也称为”属性”或”字段”)
表、索引、序列、视图(“关系”)
\dt pg_*   \dv pg_*  
show config_file;
explain select * from data;
select user
select current_user
select session_user
select * from pg_settings
select * from user_tables
select * from pg_tables          --schemaname,tablename  
select * from pg_views           --schemaname,viewname,definition
select * from pg_namespace       --oid,nspname
select * from pg_type            --oid,typname                                   字段数据类型的相关信息
select * from pg_attribute       --attrelid,oid,atttypid,attnum,attname          关于表字段的信息
select * from pg_attrdef         --字段缺损值
select * from pg_description     --objoid oid,objsubid oid,classoid,description  字段描述
select * from pg_class           --oid,relname                                   数据库中表对象的信息 
select * from pg_index           --索引表
select * from pg_indexes         --索引表
select * from information_schema.views
select * from information_schema.columns
select * from pg_stat_activity   --活动的表

select * from pgxc_wlm_session_statistics --运行时间最长的SQL语句
pgxc_total_memory_detail  --内存查询


select * from pg_class c,pg_attribute a,pg_type t 
where c.relname='dim_ecmdb_dc' 
and a.attnum>0 
and a.attrelid=c.oid 
and a.atttypid=t.oid

select a.attnum,a.attname,t.typname as type 
from pg_class c,pg_attribute a,pg_type t 
where c.relname='dim_ecmdb_dc' 
and a.attnum>0 
and a.attrelid=c.oid 
and a.atttypid=t.oid

select * from information_schema.columns 
select r,r||'_tans' from generate_series(1,10) r;
select pg_database.datname, pg_size_pretty(pg_database_size(pg_database.datname)) as size from pg_database;
select table_schema || '.' || table_name as table_full_name, pg_total_relation_size('"' || table_schema || '"."' || table_name || '"')as size from information_schema.tables order by 2 desc;

pg_index
indexrelid   =pg_class.oid	
indrelid     =pg_class.oid	
indnatts     =pg_class.relnatts
indkey       =pg_attribute.attnum
indclass     =pg_opclass.oid

pg_tables
schemaname   =pg_namespace.nspname
tablename    =pg_class.relname
tableowner   =pg_authid.rolname
tablespace   =pg_tablespace.spcname

pg_indexes
schemaname =pg_namespace.nspname
tablename  =pg_class.relname
indexname  =pg_class.relname
tablespace =pg_tablespace.spcname

pg_views
schemaname =pg_namespace.nspname
viewname   =pg_class.relname
viewowner  =pg_authid.rolname

pg_class
oid          =pg_description.classoid
relname      =pg_description.classoid
relnamespace =pg_namespace.oid	
reltype      =pg_type.oid
relowner     =pg_authid.oid
reltablespace=pg_tablespace.oid
reltoastrelid=pg_class.oid
reltoastidxid=pg_class.oid
relfilenode  =pg_class.oid

pg_attribute
attrelid   =pg_class.oid
atttypid   =pg_type.oid   and pg_attribute.attnum>0
attnum     =pg_description.objsubid
attnum     =pg_class.relnatts

pg_namespace
nspowner  =pg_authid.oid	
oid       =pg_class.relnamespace

select * from information_schema.columns
tables
columns
column_privileges
column_udt_usage
column_domain_usage
role_column_grants

select * from information_schema.views
view_column_usage
view_table_usage
views
view_definition
table_schema
table_name
column_name

select relname,relnamespace,relfilenode,objoid,classoid,objsubid,description,attrelid,attname,atttypid,attnum from pg_class c
left join pg_description b on c.oid=b.objoid
left join  pg_attribute a  on c.oid=a.attrelid
--where objoid=74611

找字段语句
select table_schema,table_name,column_name,data_type,character_octet_length 
from information_schema.columns
--where table_name= 'dim_ecmdb_dc_abi'

select nspname,relname,attname,description
from pg_attribute a
left join pg_description b on a.attnum=b.objsubid 
left join pg_class c on a.attrelid=c.oid
left join pg_namespace d on c.relnamespace=d.oid

select table_schema,table_name,column_name,data_type,character_octet_length
from information_schema.columns
where table_schema in('ext','dm','dw','ods')

--('dbms_om','public','sys','pg_catalog','scheduler','cstore','ext','information_schema')

smartit
select current_catalog,current_database()       数据库名称
datalake
select inet_client_addr(),inet_client_port()    客户端 ip/端口
10.47.70.228  52601
select inet_server_addr(),inet_server_port()    服务端 ip/端口
21.112.12.64  8000
select pg_backend_pid()                         pid进程号查看

查询表的字段
select table_schema,table_name,column_name,data_type,character_octet_length
from information_schema.columns
where table_name= 'dm_asset_detail_f'

多表联合查询
with 
t as(select oid,nspname from pg_namespace),
x as(select oid,relname,relkind,relnamespace from pg_class),
a as(select attrelid,attname,attnum from pg_attribute)
select 
t.nspname "模式"
,x.relname "表名"
,a.attname "字段名" 
from t,x,a

with 
A as (select 1 as C),
B as (select * from A) 
select * from B

select 'sh.*' from A; 
select distinct region from sale_detai

按照第一列分组显示值，筛选大于100的数据，按照值大小排序，显示前10行
select dc_name,count(name) as num from dm.dim_ecmdb_rack
group by 1
having num>100
order by 2
limit 10        --从小到大
offset 5        --跳过5行数据
--desc limit 10 --从大到小

场景1：from->where->group by->having->select->order by->limit
场景2：from->where->select->distribute by->sort by

两列比较
select count(distinct name) from dim_ecmdb_dc
where region_type != cloud_service_tag

空值替换，如果A列为空则B替换空值 合并两列，以前面为准
coalesce(A,'B')
,coalesce(site,dc) as site 

空值查询
where A is null   A is not null

连接两列
concat(substring(A,1,length(A)-2),'*',substring(A,length(A)-1,1))
A列第一个字符替换成*

月份提取格式
,calendar_key=last_day(calendar_key::date)      取值每个月最后一天
substr(create_time,1,7)                  2022-07
substring(create_time,1,7)               2022-07
where substr(createtime,1,7)='2022-11'   提取指定月份数据

显示前六个月数据
where monthy in (select distinct substr(create_time,1,7) as monthy from X order by monthy desc limit 6)

查询近期数据
select * from dm_bluebird_routine
where taskcreatetime>=now() - interval '5 days'

JSON格式数据解析
查找key/value
with t as (select site,ordernumber
,jsonb_array_elements_text(skyc::jsonb) as a
from ods_eticket_dc_permissions_cardswiping_review_v as F)
select 
distinct jsonb_object_keys(a::jsonb)
from t

解析key/value 为单独列
with t as (select site,ordernumber
,jsonb_array_elements_text(skyc::jsonb) as a
from ods_eticket_dc_permissions_cardswiping_review_v as F)
select site,ordernumber
,a::jsonb->>'门禁编号'          as "门禁编号"
from t

创建数据库,表,添加列,删除列
alter database test owner to adminx
create schema app authorization adminx
create schema company
alter table X rename column a to b;
alter table X rename to Y;
create database test
drop database test
drop table test
alter table test drop column X;
alter table test add  column X;
alter table test alter column X type datatype; 更改列数据类型
create user adminx with password 'password';
grant all on company to adminx;
revoke all on company from adminx;
drop user adminx;
添加唯一约束add unique constraint
alter table table_name
add constraint test unique(column1, column2);

创建视图存储SQL逻辑语句
create view x as(select id,name,age from company)

查询表索引
select * from user_indexes where table_name='X'
select * from A,B where A.id=B.id;

聚合函数 分组操作 分组过滤
select col1,agg_func() from t group by col1 having conditions; 

聚合函数 grouping sets、rollup、cube 

连表查询
select t1.col1, t2.col1 from table1 as t1
inner | left | right | full | cross join t2 on conditions;
inner join（内连接）
下面列出了您可以使用的 join 类型，以及它们之间的差异。
join: 如果表中有至少一个匹配，则返回行
left join: 即使右表中没有匹配，也从左表返回所有的行
right join: 即使左表中没有匹配，也从右表返回所有的行
full join: 只要其中一个表中存在匹配，就返回行

关联子查询
select t1.col1, t1.col2 from t1
where exists (select 1 from t2 where t2.col1 = t1.col1);

集合运算
select col1, col2 from t1
union | intersect | except [all] 
select c1, c2 from t2 

union：连接两个查询，相同的部分不显示；
union all：连接两个查询，相同的部分显示；
intersect：返回两个查询中的相同部分；
minus：返回两个查询中的不同部分；

通用表表达式  递归查询
with recursive t as (
select ... 
union all
select ...) 
select * from ct

explain (format json) select * from X
explain (format xml) select * from X
explain analyze select * from X
explain select * from X

查看PostgreSQL可用的扩展模块：
create extension pgcrypto cascade;
create extension pgcrypto; 创建加密算法
select * from pg_available_extensions;
\dx 已安装扩展列表

encrypt(data bytea, key bytea, type text) --加密
convert_from(decrypt(data bytea, key bytea, type text),'SQL_ASCII') --解密

encrypt_iv(data bytea, key bytea, iv bytea, type text) returns bytea
decrypt_iv(data bytea, key bytea, iv bytea, type text) returns bytea

加密生成密钥 select encrypt('12345678','1','aes')
解密密钥     select convert_from(decrypt('\x90cce5fbc091bbe761a538a49b4e2e09','1','aes'),'SQL_ASCII');

select encode(encrypt('1234567'::bytea,'1','aes-ecb'),'base64');
select convert_from(decrypt(decode('Srm2phLqZSQ2oCHm1Hadbg==','base64'),'1','aes-ecb'),'SQL_ASCII');

加密生成密钥
UPDATE public.jobs
	SET miyao=encode(encrypt(job_id::bytea,'1','aes-ecb'),'base64')
	WHERE 1=1;

解密密钥
UPDATE public.jobs
	SET jiemi=convert_from(decrypt(decode(miyao,'base64'),'1','aes-ecb'),'SQL_ASCII')
	WHERE 1=1;	
	
create table company(
id        int not null,
name      text,
age       int,
address   text,
salary    float);

容易插入空格 去掉空格trim函数
insert into company values
('1','Paul ','32','California','20000'),
('2','Allen','25','Texas     ','15000'),
('3','Teddy','23','Norway    ','20000'),
('4','Mark ','25','Rich-Mond ','65000'),
('5','David','27','Texas     ','85000'),
('6','Kim  ','22','South-Hall','45000'),
('7','James','24','Houston   ','10000');

ID 自动递增
create table test(
   id  serial primary key,
   name           text      not null,
   age            int       not null,
   address        char(50),
   salary         real);
insert into test (name,age,address,salary) values ( 'paul', 32, 'california', 20000.00 );
insert into test (name,age,address,salary) values ('allen', 25, 'texas', 15000.00 );
insert into test (name,age,address,salary) values ('teddy', 23, 'norway', 20000.00 );
insert into test (name,age,address,salary) values ( 'mark', 25, 'rich-mond ', 65000.00 );
insert into test (name,age,address,salary) values ( 'david', 27, 'texas', 85000.00 );
insert into test (name,age,address,salary) values ( 'kim', 22, 'south-hall', 45000.00 );
insert into test (name,age,address,salary) values ( 'james', 24, 'houston', 10000.00 );

聚合计算的窗口函数：sum() over(); count() over(); avg() over;
组排序的窗口函数：row_number() over(); rank() over(); dense_rank() over()
分组查询的窗口函数：ntile() over()
偏移分析的窗口函数：lag() over();lead() over();first_value() last_value()

聚合函数使用方法 年级，班级，排名，按年纪排名，按班级排名
create table student(id int,grade int,score int)
insert into student values(1,1,88);
insert into student values(2,1,66);
insert into student values(3,1,75);
insert into student values(4,2,30);
insert into student values(5,2,70);
insert into student values(6,2,80);
insert into student values(7,2,60);
insert into student values(8,3,90);
insert into student values(9,3,70);
insert into student values(10,3,80);
insert into student values(11,3,80);

create table test (n text, x text, y bigint);
insert into test values 
('张三' , '语文' , 74),
('张三' , '数学' , 83),
('张三' , '物理' , 93),
('李四' , '语文' , 74),
('李四' , '数学' , 84),
('李四' , '物理' , 94);

按行合并列
select name,array_to_string(array_agg(distinct tag),',') from tb3 group by name;
按照学生分数排名
select *,row_number() over(order by score desc) as sequence from student;
先按照班级，再按照分数
select *,row_number() over(partition by grade order by score desc) as sequence from student;
取每个班级 第一名排名
select * from(select *,row_number() over(partition by grade order by score desc) as sequence from student) t where t.sequence<=1;
select *,rank() over(partition by grade order by score desc) as sequence from student;

分组求值
count() over(partition by X order by X)
max()   over(partition by X order by X)
min()   over(partition by X order by X)
avg()   over(partition by X order by X)
lag()   over(partition by X order by X)　　
lead()  over(partition by X order by X)
round(sum(t.amt) / sum(sum(t.amt)) over(partition by 1), 2) 保留两位小数点

窗口函数剖析
select sum() over(partition by ___ order by___) from table 
1  聚合功能：在上述例子中，我们用了sum()，但是你也可以用count(), avg()之类的计算功能
2  partition by：你只需将它看成group by子句，但是在窗口函数中，你要写partition by
3  order by：order by和普通查询语句中的order by没什么不同。注意，输出的顺序要仔细考虑

子查询 
select age from company
select * from employees
where salary > (select salaryfrom,employees where employee_id = 149)
select max(avg_sal) from (select avg(salary) avg_sal from employees group by department_id)
where exists (select age from company where salary > 65000)
select * from company where age >= 25 and salary >= 65000;
select * from company where name like 'ki%';
select * from company where name glob 'ki*';
select * from company where age in ( 25, 27 );
select * from company where age not in ( 25, 27 );
select * from company where age between 25 and 32;

distinct 用于返回唯一不同的值
limit 限制返回的行数
asc ：升序（默认）
desc ：降序
select * from  <表名>
where    <条件表达式>
and      同时满足  
or       满足其中一个条件 
not      不符合该条件
in       满足指定条件
between  在几个条件之间 
where    满足组合条件的查询
limit       限制查询行
asc|desc    升序/降序,系统默认升序,省略asc
from     从中检索数据的表 仅在从表选择数据时使用
where    行级过滤 否
group by 分组说明 仅在按组计算聚集时使用
count() over(partition by dc_name order by billing_month)
having 关键字用法，分组后过滤分组内容
select name from employees group by name having count (name) < 2;
order by 输出排序顺序 
子查询必须被圆括号 () 括起来
select cust_id from orders 
where order_num 
in (select order_num from orderitems where prod_id = 'rgan01')
extract(day from d) 提取月份
extract(second from(d2 - d) day to second)
子查询
select dc from dim_ecmdb_dc 
where dc in(select san from b where san='2')
exists  not 
intersect  
exists   有记录返回true

nvl 函数是一个空值转换函数 nullif  ifnull
nvl(name_en,0)      空值 0 替换
nvl(name,'na',name) 空值 字符 替换
nvl2
coalesce(a,b)       合并两列查询，以前面为准
coalesce(A,'B')     A列为空则B字符串替换空值
concat(substring(A,1,length(A)-2),'*',substring(A,length(A)-1,1))
coalesce(dc_name,dcname)   两列去重合并，两列都有数据，以前面为准

合并两列字段查询
select concat(h,i) from apd_cloud_type_class
count(expression) 返回表中不为null的行数
count(*)          返回所有行数

字符串转换成数字
convert(int,字段)
cast(字段 as int)
cast(A as int)
nvl(A,0)  
cast(char as numeric)
char::numeric   
to_number(text,int)
to_char(int,text)
to_char()：  数字转文本
to_number()：文本转数字

is null  空值
is not   不是特定值
is not null 不是空值

通配符like判断相似,%表示任意字符，只能用于文本字段
like 'a%'        查找以"a"开头的任何值
like '%a'        查找以"a"结尾的任何值
like '%或%'      查找在任何位置具有"或"的任何值
like '_r%'       查找第二个位置有"r"的任何值
like 'a_%'       查找以“a”开头且长度至少为2个字符的任何值
like 'a__%'      查找以"a"开头且长度至少为3个字符的任何值
like 'a%o'       查找以“a”开头并以“o”结尾的任何值
like '[bc]%'     用来指定一个字符集，它必须匹配指定位置
select * from dm_ecmdb_batterygroup_v
where model like '%200%'

使用in子句比exists子句更耗时
exists 运算符用于判断查询子句是否有记录
exists      <= in   <= join
not exists  <= not in   <= left join
is [not] null, [not] like, [not] between, [not] in, [not] exists
select * from a where exists(select 1 from b where a.a=b.b)      判断存在
select * from a where not exists(select 1 from b where a.a=b.b)  判断不存在

使用union 相同的列数、数据类型、顺序
a union b       并集，不保留重复记录  
a union all b   保留所有的记录 
a intersect b   交集，获取结果集a和结果集b共有的记录
a except b      差操作，从a中删掉含有b的结果

(a-b)union(b-a)
(select name_ci as n1,type as n2,subtype as n3 from ecmdb a
except
select name_ci1 as n1,type1 as n2,subtype1 as n3 from upsstsq1 b)
union
(select name_ci1 as n1,type1 as n2,subtype1 as n3 from upsstsq1 b
except
select name_ci as n1,type as n2,subtype as n3 from ecmdb a);

运算符
a == b
a = b
a != b
a <> b
a > b
a < b
a >= b
a <= b
a !< b
a !> b

连接（join）
内连接（inner join）
外连接（outer join）
左外连接（left outer join）
右外连接（right outer join）
全外连接（full outer join）
交叉连接（cross join）
自然连接（natural join）
自连接（self join）

时间运算 'yyyy-mm-dd hh24:mi:ss'
select current_date;
select current_time;
select current_timestamp;
select current_timestamp,localtimestamp,now();
select extract(year from current_timestamp)
select extract(doy from timestamp '2022-12-20 12:10:10'); 从年份中提取天
select extract(day from timestamp '2022-12-20 12:10:10'); 从日期中提取天
select extract(month from timestamp '2022-12-20 12:10:10'); 
select extract(mon from now())
select extract(year from now())
select extract(hours from '90 minutes'::interval)
select now()::timestamp + '1 year'
select now()::timestamp + '1 year 1 month 1 day 1 hour 1 min 1 sec'
select age(timestamp '2022-09-13',timestamp '1990-11-14');
select date_trunc('month',now()) +interval '12h'
select current_timestamp(0) + interval '-1 year'
select current_timestamp(0)::date + interval '1 month' - interval '1 day'  取每个月最后一天
where create_date >now()::date - interval '1 day'
date_trunc('month',calendar_key::date) + interval'1 month' - interval '1 day'
to_char(last_update_date, 'yyyymm') 取年月
last_day(date1)

Abbreviation	
Y	Years
M	Months 
W	Weeks
D	Days
H	Hours
M	Minutes 
S	Seconds

extract函数格式 extract （field from source）
extract函数是从日期或者时间数值里面抽取子域，
比如年、月、日等。source必须是timestamp、time、interval类型的值表达式。
field是一个标识符或字符串，是从源数据中的抽取的域

从时间戳中抽取季度，年份，月份
,(extract(year from X)::text || '.Q' || extract(quarter from X)::text) as quarter

正则表达式的子字符串，模式匹配
如果想匹配字符串中的 \ 转义  
匹配任意字符 '%'  
匹配百分号   '\%'  
匹配%_ 
匹配百分号，下划线前后任意字符 '%\%\_%'
关键字子句等同于转义 escape '#'
~     匹配正则表达式，区分大小写
~*    匹配正则表达式，不区分大小写
!~    不匹配正则表达式，区分大小写
!~*   不匹配正则表达式，不区分大小写
      用于忽略大小写的模式匹配
~~    等效于 like
!~~   等效于 not like

^     匹配开始
$     匹配结尾
.     任意一个字符

|       两个候选项之一
*       0次或更多次
+       一次或更多次
?       0次或一次
{m}     m次
{m, }   m次或更多次
{m,n}   只有m次，不超过n次
括号()..分组中的逻辑
[]      声明一个字符类，posix正则表达式

select 'osdba' ~ 'a';
select 'osdba' ~ '(b|a)*';
select 'osdba' ~ '.*(c|a).*';
select 'osdba' ~ '(s|d).*';
select 'osdba' ~ '^os';
select 'osdba' ~ 'db';
select 'osdba' ~ 'db$';
select 'osdba' ~ 'dba$';
substring(name,'[a-za-z0-9]+') 替换csv导入后的空格空行
substring(name,'[a-z0-9]+')
substring(name,'\w*\d.*$') 
replace(name,chr(9),'')   chr(9) 去tab   chr(32) 去空格 chr(9)去换行
similar to   sql正则表达式
~            posix正则表达式
select 'osdba' ~ 'sdb';
select 'osdba' similar to 'sdb';
select 'osdba' similar to '%sdb%';
select substring('osdb-5-osdb',e'(\\d+)');
select substring('osdb-5-osdb','%#"[0-9]+#"%','#');  两个标记字符串之间的数字
[a-za-z]              匹配所有字母
[0-9]                 匹配所有数字
[A_Za-z0-9]           匹配所有字母和数字
\w
^[a-za-z]+$           由26个英文字母组成的字符串
^\w+$　               由数字、26个英文字母或者下划线组成的字符串
[^A-Za-z0-9]+$        大小写数字
[^\u4e00-\u9fa5]      中文
[^\x00-\xff]          匹配双字节字符(包括汉字在内)
regexp_replace(str, regexp, rep [, position] )
str：要匹配的字符串表达式
regexp：具有匹配模式的字符串表达式
rep：作为替换字符串的字符串表达式
position：一个大于 0 的可选整型数字文本
参考ascii码对照表
tab char(9)  空格  char(32)   换行  char(10)  回车符 char(13)
select replace(name,chr(9),'') from A

提取数字，转换类型，计算总和
select cast(regexp_replace(visitornum,'\d','','g') as int)
from ods_eticket_dc_customers_visit_v as d

正则表达函数
regexp_extract_all 提取正则表达式的子串
regexp_extract     提取并返回目标字符串中符合正则表达式的第一个子串
regexp_like        判断目标字符串是否符合正则表达式
regexp_replace     替换目标字符串中符合正则表达式的子串
regexp_split       使用正则表达式分割目标字符串，返回被分割后的子串合集。
regexp_split_to_table() 
substring(string from pattern)
regexp_matches()
regexp_split_to_array()
regexp_replace(visitornum,'\d','','g')

select regexp_replace('os123dba','.[1-9]+','#');  o#dba     替换匹配posix正则表达式的字符串
select replace('123osdba45osdba78','osdba','-');  123-45-78 替换指定字符串
select split_part();

字符串分割函数
regexp_split_to_table 和 regexp_split_to_array 都是字符串分隔函数
regexp_split_to_table(w4,'\n')  
regexp_replace(w4,'[\u4e00-\u9fa5\()]+','')  将汉字替换为空

按特定字符拆分成多行
with para as (select 'h00449593' as name from dual)
select id,
regexp_split_to_table(control_level,',')
from dm.dim_ecmdb_dc
--regexp_split_to_table(w4,'\n')  

string_agg（合并）：多行数据合并成一个字符串，以逗号隔开。
string_split（拆分）:一个字符串，拆分成多行。


字符串函数和操作符
select 'post'||'12gresql';             字符串连接
select char_length('sql');             字符个数
select char_length('sql操作');         字符个数
select octet_length('jose');           字符串中字节数
select octet_length('jose名'); 7      一个字母一个字节，一个汉字占三个字节
select overlay('txxxxas' placing 'hom' from 2 for 4);   替换字符串改变长度
select position('om' in 'thomas'); 3                    指定字符串位置
select substring('thomas' from 2 for 3);                抽取字符串
select substring('thomas' from '...$'); 抽取匹配posix正则表达式的子字符串，模式匹配
select substring('thomas' from '%#"o_a#"_' for '#');    抽取匹配sql  正则表达式的子字符串
substr('alphabet', 3, 2)
select ascii('b');   ascii码 
convert()  decode()  encode()  initcap(string) 单词首字母大写  
to_ascii() translate()
md5(string) 
trim()  btrim()  删除空格
substr(create_time,1,7) as create_time
concat('abcde', 2, NULL, 22)
concat_ws(',', 'abcde', 2, NULL, 22)
format('hello')    格式化
length('jose')     字符串长度
md5('abc')         计算字符串md5散列十六进制
parse_ident('Some,Schem,asomeT,able');
regexp_matches()
regexp_replace()
regexp_split_to_array('hello world', '\s+')
regexp_split_to_table('hello world', '\s+')
repeat('Pg', 4)
replace('abcdefabcdef', 'cd', 'XX')
reverse('abcde')
right('abcde', 2)
left('abcde', 2)   取右边2位字符
split_part('abc,agu,ahu', ',', 2) 
strpos('high', 'ig')
substr('alphabet', 3, 2)
starts_with('alphabet', 'alph') 如果字符串以 alph开始 为真true
translate('12345', '143', 'ax') 替换字符串
string_agg()

select concat_ws('_','postgresql','9.6')
select concat('postgresql','9.6'),concat('postgresql',null,'testdb')
select concat_ws('_','postgresql','9.6')
select concat_ws('**','postgresql',null,'testdb')
select  left('football',5);
select  right('football',4);
select lpad('hello',4,'??'),lpad('hello',10,'??')   填充字符串
select rpad('hello',4,'?'),rpad('hello',10,'?');
select char_length('date'),char_length('zhang')
select length('date'),length('zhang')               uif 格式长度
注意：length函数的计算结果和char_length函数相同，因为英文字符的个数和所占字节相同，一个字符占一个字节。汉字是 一个子占两个字节
删除空格的函数：ltrim(s)、rtrim(s)和trim(s)
select '( book )',concat('(',ltrim(' book '),')')
select '( book )',concat('(',rtrim(' book '),')')
select '( book )',concat('(',trim(' book '),')')

删除指定字符串的函数：
trim(s1 from s)
select trim('zh' from 'zhanghellzhnihao')
select repeat('zhang',3);
select replace('www.baidu.com','w','z')
select substring('zhanghello',5) as a1,substring('zhanghello',5,3) as a2,substring('lunch',-3) as a3
select position('ball' in 'football')
select reverse('abc')

nvl(name_en,0)     字段为空值，显示0
nvl(to_char(name_en),'na',name) 先转换为字符串，然后空值赋值给字符串
coalesce(a.cloud_service_tag,b.cloud_type)   合并两列查询，以前面为准
excel去除字符中的空格
trim(a1)
substitute(a1," ","")

cast('5' as int)         数据类型转换函数
c::date                  简洁转换
select '12.73'::money;   转换格式

字符串提取拼接
left(),right(),substring(),substring_index(),mid(),substr()
select '123'||'456' from dual
select concat('123','456') from dual
concat()
,(left(month_key,4) ||'-'||right(month_key,2)||'-01')::date as month_key

连接两列 a列第一个字符替换成*
concat(substring(a,1,length(a)-2),'*',substring(a,length(a)-1,1))
字符串拆分为表，数组，聚合
select regexp_split_to_table('1,2,3',',')
select string_to_array('1,2,3' ,',');
select string_agg(a,'-') from regexp_split_to_table('1,2,3' ,',') a
arrat_to_string(array_agg(X order by X),',') as df

json 函数
,json_each(m::json)
,json_each_text(m::json)
,json_array_elements(m::json)
,jsonb_array_elements_text(m::jsonb)
,distinct jsonb_object_keys(m::jsonb)

json 格式解析
[
{"申请人姓名":"沈运来"
,"useer_type":"华为员工"
,"申请人工号":"sjb0303453"
,"position":"普通办公"
,"门禁点":"/"
,"sqlx":"新增权限"
,"jzsj":"2023-08-11 00:00:00"
}
,{"申请人姓名":"马强"
,"useer_type":"华为员工"
,"申请人工号":"mj004964628"
,"position":"普通办公"
,"门禁点":"/"
,"sqlx":"新增权限"
,"jzsj":"2023-08-11 00:00:00"
}
]

1 []中括号代表的是一个数组；
2 {}大括号代表的是一个对象
3 双引号""表示的是属性值
4 冒号：代表的是前后之间的关系，冒号前面是属性的名称，后面是属性的值，这个值可以是基本数据类型，也可以是引用数据类型

查找key/value
with t as (select site,ordernumber
,jsonb_array_elements_text(mjss::jsonb) as a
from ods_eticket_dc_permissions_cardswiping_review_v as f)
select 
distinct jsonb_object_keys(a::jsonb)
from t

解析key/value 为单独列
with t as (select site,ordernumber
,jsonb_array_elements_text(mjqxsq::jsonb) as e
from ods_eticket_dc_door_control_application_v as e)
select site,ordernumber
,e::jsonb->>'门禁' a
from t

将查询结果保存在新建表
create table csv as (select * from table_name)

将查询结果插入一张表
insert into table_name select * from table_name1

查重，查重计数
distinct x
select count(distinct a) as x1 from b

select v || '*' || h || '=' || v*h
from generate_series(1,9) v
cross join generate_series(1,9) h;

select v || '*' || h || '=' || v*h
from generate_series(1,9) v, generate_series(1,9) h;

select v || '*' || h || '=' || v*h
from generate_series(1,9) v
join generate_series(1,9) h on true;

regexp_split_to_table(string, pattern[, flags])函数用于拆分字符串，使用 posix 正则表达式
作为分隔符。函数的返回类型是 text 集合。
select regexp_split_to_table('hello world', '\s+') 拆分为两行
select split_part('abc~@~def~@~ghi', '~@~',2);
select split_part('wo,shi,xiao,ming',',',3);
text="a.b.c" split_part(text,'.',1) 结果： a
text="a.b.c" split_part(text,'.',2) 结果： b
text="a.b.c" split_part(text,'.',3) 结果： c

select split_part(control_level, ',',1) from dm.dim_ecmdb_dc

string_split() 
regexp_substr 

触发器例子
保存审计/审核,只要在company表中有一个新记录的条目，
就会在audit插入日志消息

母表company
create table company(  
   id int primary key     not null,
   name           text    not null,
   age            int     not null,
   address        char(50),
   salary         real  );

监视母表的所有操作，触发器表audit
create table audit(
    id   int  not null,
    date text not null);

创建函数/过程 连接两个表的函数
create or replace function audit_func() returns trigger as $test_table$
begin
insert into audit(id,date) values (new.id,current_timestamp);
return new;
end;
$test_table$ language plpgsql;

创建一个触发器
create trigger test_trigger after insert on company
for each row execute procedure audit_func();

插入数据检验触发器，函数
insert into company values(1, '小米科技', 8, '北京市朝阳区', 9999);
insert into company values(2, '京东中科', 6, '广州市天河区', 8999);

执行上面两条插入语句后，audit表自动插入两条审核记录)

PostgreSQL创建索引 B-tree，Hash，GiST，SP-GiST和GIN
create index index_name on table_name;
create index index_name on table_name (column1, column2); 多列索引

create index company_index on company (id,name);
drop index index_name;

lateral 子查询

利用窗口函数分组排序，然后提取排序小于3的行
select A,B,C,D 
from (select A,B,C
,rank() over (partition by B order by C desc,D) as pos from X) as s
where pos < 3;

SQl函数
create function add_em(x integer, y integer) returns integer as $$
    select x + y;
$$ language sql;
select add_em(1, 2);


组合查询 ( union, intersect, except)
exists not
exists

判断是否存在
where  exists (select substr(calendar_key,1,4)>=2022 from a)

exists用法筛选
select * from sds_du_release_t du
where du.enable_flag = 'y'
and exists (select 1 from sds_du_node_release_t dn where dn.du_id = du.du_id)
and dn.enable_flag = 'y'
group by dn.node_id, dn.service_scene
having count(1) > 1) 

select * from  emp  
where  empno > 0  
and  exists (select 'x'  from dept  where dept.deptno = emp.deptno and  loc = 'melb') 

高效
select  dept_no,dept_name  from  dept d  
where  exists (select 'x' from emp e where e.dept_no = d.dept_no)

select
date_format(actualfinishtime::date, '%y%m%d') as days
,count(distinct(actualfinishtime))
from dm_eticket_maintenance
group by days

explain select * from products where category='electronics'

SQL存储过程
create or replace function totalrecords ()  
returns integer as $total$  
declare  
    total integer;  
begin  
   select count(*) into total from employees;  
   return total;  
end;  
$total$ language plpgsql;

create table employees
(
    id serial,
    name varchar(100),
    dateofbirth date,
    city varchar(100),
    designation varchar(100),
    joiningdate date
)

create or replace procedure addemployee
(
    empid inout int,
    empname varchar(100),
    empdob date,
    empcity varchar(100),
    empdesignation varchar(100),
    empjoiningdate date
)
language plpgsql as
$$
begin
   insert into employees (name,dateofbirth,city,designation,joiningdate) values
    (empname,
     empdob,
     empcity,
     empdesignation,
     empjoiningdate
    ) returning id into empid;
end
$$;

call addemployee(null,'peter parker','1997-10-01','new york' ,'web developer','2020-11-01');

create or replace procedure updateemployee
(
    empid int,
    empname varchar(100),
    empdob date,
    empcity varchar(100),
    empdesignation varchar(100),
    empjoiningdate date
)
language plpgsql as
$$
begin
   update employees set
   name = empname,
   dateofbirth = empdob,
   city = empcity,
   designation = empdesignation,
   joiningdate = empjoiningdate
   where id = empid;
end
$$;

create or replace procedure deleteemployee
(
    empid int
)
language plpgsql as
$$
begin
    delete from employees where id = empid;
end
$$;


CICO/wulan1-datalake-encrypt
select table_schema,table_name,column_name,data_type,character_octet_length
from information_schema.columns
where table_schema in('ext','dm','dw','ods')

select
a.table_schema
,a.table_name
,a.column_name
 ,b.view_definition
from information_schema.view_column_usage a
left join information_schema.views b on a.view_name=b.table_name


云资源运营/wulan1-datalake-pro
select table_schema,table_name,column_name,data_type,character_octet_length
from information_schema.columns
where table_schema in('ext','dm','dw','ods')

云资源运营/wulan1-dws-uat
select table_schema,table_name,column_name,data_type,character_octet_length
from information_schema.columns
where table_schema in('ext','dm','dw','ods')

select
a.table_schema
,a.table_name
,a.column_name
 ,b.view_definition
from information_schema.view_column_usage a
left join information_schema.views b on a.view_name=b.table_name
where a.table_schema in('ext','dm','dw','ods')



SQL Server 教程

USE master
GO
IF NOT EXISTS (
   SELECT name
   FROM sys.databases
   WHERE name = N'TutorialDB'
)
CREATE DATABASE [TutorialDB]
GO


USE [TutorialDB]
-- Create a new table called 'Customers' in schema 'dbo'
-- Drop the table if it already exists
IF OBJECT_ID('dbo.Customers', 'U') IS NOT NULL
DROP TABLE dbo.Customers
GO
-- Create the table in the specified schema
CREATE TABLE dbo.Customers
(
   CustomerId        INT    NOT NULL   PRIMARY KEY, -- primary key column
   Name      [NVARCHAR](50)  NOT NULL,
   Location  [NVARCHAR](50)  NOT NULL,
   Email     [NVARCHAR](50)  NOT NULL
);
GO

-- Insert rows into table 'Customers'
INSERT INTO dbo.Customers
   ([CustomerId],[Name],[Location],[Email])
VALUES
   ( 1, N'Orlando', N'Australia', N''),
   ( 2, N'Keith', N'India', N'keith0@adventure-works.com'),
   ( 3, N'Donna', N'Germany', N'donna0@adventure-works.com'),
   ( 4, N'Janet', N'United States', N'janet1@adventure-works.com')
GO


