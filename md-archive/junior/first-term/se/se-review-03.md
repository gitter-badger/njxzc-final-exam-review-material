---
layout: post
title: 软件工程期末复习题(3)
tags: 软件工程
categories:
  - 软件工程习题
date: 2021-12-31 13:24:35
---




考察知识点：Java语言实现类的方法

<!--more-->

![image-20211230131130885](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301311056.png)

![image-20211230131153436](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301311819.png)

![image-20211230131205364](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112301312554.png)

```
参考解答：
没有参考答案加持，如有问题，欢迎DM！
(1)
```

```java
public class RedState extends State{
    // 界面在红色状态，push操作可改变成蓝色
    public void handlePush(Context c){
        c.setState(BlueState);
    }
    
    // 界面在红色状态，pull操作可改变成绿色
    public void handlePull(Context c){
        c.setState(GreenState);
    }
    
    public void String getColor(){
        return this.state;
    }
}
```



考察知识点：UML用例图

(书本P224页对于这种图的描述较为模糊，复习提纲中第43点提及到：`掌握用例图的概念、内容和方法`，故拿两道习题来练练手)

![image-20211231141733169](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311417259.png)

包含关系和扩展关系的区别

![image-20211231143425968](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311434014.png)

![image-20211231140841714](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311408801.png)

```	
摔倒事件报警是对摔倒动作的增强型描述
去除摔倒时间报警和床传感器检测，事件日志将无法使用。
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311800999.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20211231180036897](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311800999.png)



考察知识点：UML用例图

![image-20211231140923529](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311409657.png)

```
删除书籍和修改书籍信息是对查询书籍的增强型描述
交纳罚金是对归还书籍的增强型描述
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311512192.png" style="color:red;border-bottom
:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20211231151251100](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311512192.png)



考察知识点：类图、Java语言编写类

![image-20211231141150842](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311411985.png)

![image-20211231155254348](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311552495.png)

```
参考解答：
类图：
```

<a href="https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311615262.png" style="color:red;border-bottom:none;">看不清楚图片，请戳我！</a> :point_left:

![image-20211231161555091](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311615262.png)

```
Java语言编写该系统代码框架
【注：有些方法仅凭题干无法补全，因此做第二小问的时候，只需掌握Java面向对象
的基本操作即可，构造方法、get、set方法、一些普通方法即可】
```

```java
// 学生类
public Class Student{
    private String sno;
    private String password;
    
    // 无参构造方法
    public Student(){
        
    }
    
    // 有参构造方法
    public Student(String sno,String password){
        this.sno=sno;
        this.password=password;
    }
    
    // get方法
    public String getSno(){
        return this.sno;
    }
    public String getPassword(){
        return this.password;
    }
    
    // set方法
    public void setSno(String sno){
        this.sno=sno;
    }
    public void setPassword(String password){
        this.password=password;
    }
    
    // 登录方法
    public boolean login(String sno,String password){
        if(sno.equals("xxxxxx")&&password.equals("123456"))
            return true;
        else
            return false;
    }
    
    // 选课方法
    public boolean selectCourse(String courseID){
        
    }
    
    // 查成绩方法
    public int checkResult(String courseID){
        
    }
}
```

```java
// 教工类
public Class Staff{
    private String staffID;
    private String password;
    
    // 无参构造方法
    public Staff(){
        
    }
    
    // 有参构造方法
    public Staff(String staffID,String password){
        this.staffID=staffID;
        this.password=password;
    }
    
    // get方法
    public String getStaffID(){
        return this.staffID;
    }
    public String getPassword(){
        return this.password;
    }
    
    // set方法
    public void setStaffID(String staffID){
        this.staffID=staffID;
    }
    public void setPassword(String password){
        this.password=password;
    }
    
    // 登录方法
    public boolean login(String staffID,String password){
        if(staffID.equals("xxxxx")&&password.equals("123456"))
            return true;
        else
            return false;
    }
}
```

```java
// 教务人员类
public Class AdministriveStaff extends Staff{
    
    public boolean addCourse(){
        
    }
    
    public boolean addSchedule(){
        
    }
}
```

```java
// 教师类
public Class Teacher extends Staff{
    
    public boolean addGrade(){
        
    }
    
    public List listStudents(){
        
    }
}
```

```java
// 课程类
pulic Class Course{
    private String courseID;
    private String courseName;
    private String time;
    private String place;
    
    // 无参构造方法
    public Course(){
        
    }
    
    // 有参构造方法
    public Course(String courseID,String courseName,String time,String place){
        this.courseID=courseID;
        this.courseName=courseName;
        this.time=time;
        this.place=place;
    }
    
    // get方法
    public String getCourseID(){
        return this.courseID;
    }
    public String getCourseName(){
        return this.courseName;
    }
    public String getTime(){
        return this.time;
    }
    public String getPlace(){
        return this.place;
    }
    
    // set方法
    public void setCourseID(String courseID){
        this.courseID=courseID;
    }
    public void setCourseName(String courseName){
        this.courseName=courseName;
    }
    public void setTime(String time){
         this.time=time
    }
    public void setPlace(String place){
        this.place=place;
    }
}
```

```java
// 成绩类
public Class StudyInfo{
    private int grade;
    
    // 无参构造方法
    public StudyInfo(){
        
    }
    
    // 有参构造方法
    public StudyInfo(int grade){
        this.grade=grade;
    }
    
    // get方法
    public int getGrade(){
        return this.grade;
    }
    
    // set方法
    public void setGrade(int grade){
        this.grade=grade;
    }
}
```

```java
// 排课表类
public Class Schedule{
   
}
```



考察知识点：PAD图

![image-20211231141323140](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311413247.png)

```
参考解答：
```

![image-20211231175600118](https://gitee.com/gujiakai/pic-go-typora02/raw/master/img/202112311756187.png)