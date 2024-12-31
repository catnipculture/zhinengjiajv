> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

本基于Springboot的[智能家居系统](https://so.csdn.net/so/search?q=智能家居系统&spm=1001.2101.3001.7020)提供管理员、用户两种角色的服务。

总的功能个人中心、基础数据管理、家具管理、任务管理和用户管理。本系统可以帮助用户发布任务，帮助管理员管理家具



# 环境要求



1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。 

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA; 

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可 

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS; 

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目 

6.数据库：MySql5.7/8.0等版本均可；





# 技术栈



运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：SpringBoot + MyBatis + Vue + Bootstrap + jQuery





# 使用说明





1.使用Navicat或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件； 

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目； 

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；





# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq 

源码地址：[http://www.codegym.top](http://www.codegym.top/)





# 运行截图





![springboot198基于springboot的智能家居系统0](https://img-blog.csdnimg.cn/img_convert/9be3b3b1482844c6fe497a6b9a663182.png)

![springboot198基于springboot的智能家居系统1](https://img-blog.csdnimg.cn/img_convert/bdaebf245f310bdab94b19aaa450507c.png)



![springboot198基于springboot的智能家居系统3](https://img-blog.csdnimg.cn/img_convert/7e650718cb1464591bfb4d832be8031e.png)





### 代码

```java
	 /**
     * 查询
     */
    @RequestMapping("/query")
    public R query(CaipinxinxiEntity caipinxinxi){
        EntityWrapper< CaipinxinxiEntity> ew = new EntityWrapper< CaipinxinxiEntity>();
 		ew.allEq(MPUtil.allEQMapPre( caipinxinxi, "caipinxinxi")); 
		CaipinxinxiView caipinxinxiView =  caipinxinxiService.selectView(ew);
		return R.ok("查询菜品信息成功").put("data", caipinxinxiView);
    }
	
    /**
     * 后端详情
     */
    @RequestMapping("/info/{id}")
    public R info(@PathVariable("id") Long id){
        CaipinxinxiEntity caipinxinxi = caipinxinxiService.selectById(id);
		caipinxinxi.setClicknum(caipinxinxi.getClicknum()+1);
		caipinxinxi.setClicktime(new Date());
		caipinxinxiService.updateById(caipinxinxi);
        retu
```
