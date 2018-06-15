# RobotFramework
### 被测系统
* Tinyshop
### 开发IDE
* RIDE

### 项目结构
![img](https://github.com/ericyishi/img-folder/blob/master/RF/structure.png)
* 采用的分层的结构进行
```
  --case 用例层
  --action 动作层
  --flows 业务层
  
```
* 依然采用PO模型。其核心是分离测试对象和测试数据。
* 将关键字进行二次封装，方便业务层调用。
* 因为考虑到实际，前后台由不同的前端人员进行开发的，所以在命名规范不能保证完全统一，因此在动作层以及业务层做了两套，分别对应前后台
* 在操作中，发现前后端的在动作层均有“输入用户名”“输入密码”的相同命名，调用时候会报错，所以避免这个问题将前端动作名前加上f，后端动作名加上b
![img](https://github.com/ericyishi/img-folder/blob/master/RF/duplicateName.png)
* 其实还可以将打开浏览器这类公共动作剥离出来，放入common动作中

### 运行
* 以商品添加功能模块作为一个测试集，运行下面的所有测试用例
![img](https://github.com/ericyishi/img-folder/blob/master/RF/error.png)
* 发现三个测试用例失败，经检验是因为当“成本价”“市场价”“零售价”为负数的也能够提交，这是bug。

### RF框架
* 比较适合测试团队编写代码人员较少，又要开展自动化的公司。
* 将动作和流程都封装成关键字，测试用例直接填表调用即可。
![img](https://github.com/ericyishi/img-folder/blob/master/RF/caseSample.png)
* 关键字还支持中文，所以在测试团队中容易推广。


