# 实验一：业务流程建模
<table>
<tr>
<td>学号</td>
<td>班级</td>
<td>姓名</td>
<td>照片</td>
</tr>
<tr>
<td>201510414322</td>
<td>2015级软件工程三班</td>
<td>杨军</td>
<td><img src="yangjun1.png" width="50"/></td>
</tr>
</table>

流程图1：考试及成绩管理流程
--------------
plantuml源码如下:
```
@startuml
|教务处|
start
:安排考试;
:考试安排表]
|教师|
:出卷;
split
:A/B试卷]
split again
:打印审批表]
|系主任|
:审批签字;
:打印审批表]
end split
|教务处|
:打印试卷;
:试卷]
|学生|
:参加考试;
:答卷]
|教师|
:阅卷出成绩;
fork
:成绩单;
|教务处|
if(有不及格？）then(yes)
:安排补考;
:补考安排表]
else(no)
stop
endif
fork again
|教师|
:答卷]
:装订存档;
end fork
|教师|
:期末流程结束;
stop
@enduml
```
业务流程图如下:

![](./yangjun2.png '图1')

流程说明：

整个流程图分为按照不同的用户类别分为四列，教务处负责安排全校课程的考试时间
和地点，下发考试安排表。教师负责准备好A、B试卷，填写"试卷打印审批表"一并交
给系主任审批签字，将选中的期末试卷和已签字的试卷打印审批表交与教务处印刷部
门进行印刷。学生按时到达指定考场进行考试，考试完毕后教师进行阅卷，产出成绩
单，并对学生答卷装订存档，若课程有有不及格情况，教务处负责安排补考时间和地
点，产生补考安排表，流程结束。

流程图2:客户维修服务流程
=============
plantuml源码如下：
```
@startuml
|客户|
start
:申请服务;
|业务经理|
if(是新客户吗？)then(yes)
:登记客户信息;
:上门勘察;
else(no)
:上门勘察;
endif
:制定方案;
|客户|
if(满意与否？)then(yes)
:签订合同;
|业务经理|
fork
:安排工人;
fork again
:安排材料;
end fork
:填写派工单;
|工人|
:领取材料;
:上门服务;
|客户|
:验收并填写反馈意见;
|业务经理|
:交回派工单;
|财务人员|
:结算收款;
stop
else(no)
|客户|
stop
endif

@enduml
```
业务流程图如下:

![](./yangjun3.png '图2')

流程说明:

业务流程从客户申请服务开始、如果是新用户，业务经理将该客户的基本信息记录下来。
接下来业务经理将上门勘察，并制定具体维修方案。业务经理和客户进行沟通，如果达
成一致，则签订正式服务合同，否则流程终结。根据合同方案，业务经理将对实施维修
的人员和所需的材料进行计划，并填发派工单。工人拿到派工单后，领取指定材料上门
服务。服务完成后客户进行验收，并在派工单上填写维修信息和反馈意见。业务经理收
回派工单后，通知财务人员进行项目的结算并收款，流程结束。

