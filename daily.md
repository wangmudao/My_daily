1. 二次阅读Java开发手册(黄山版)

   摘要：

   - 【强制】在POJO类中表达是与否的变量在数据库表中采用is_xxx的命名方式，而变量则采用xxx的命名方式并且在mapper.xml中采用结果集映射（ResultMap）

   - 【推荐】在变量和常量命名时表示类型的名词放在词尾

   - 【推荐】如果类、接口、模块使用了设计模式，那么在命名时将表示设计模式的名词放在词尾

   - 【推荐】接口中的方法和属性不要添加任何访问修饰符，常量也一般不在接口内定义除非一些基础的常量

   - 【强制】对于Service和DAO类，向外暴露出来的是接口，内部的接口实现类以Impl结尾

   - 【推荐】对于枚举类，在词尾加上Enum，同时，枚举成员名称必须全部大写（枚举是特殊的常量类，构造方法默认是私有的）

   - 【强制】Long、double、float定义的常量的数值的结尾分别加上L、D、F

   - 【推荐】对于不同功能的常量分别建立不同的常量类 xxxConsts

   - 【强制】对于一个类的静态方法或者静态变量，可以通过类名直接访问

   - 【强制】Object类的equals方法容易出现空指针异常，应当由确定的常量或者值来调用

   - 【强制】Integer对象之间值的比较应该使用equals方法进行

   - 【强制】浮点数之间的等值判断，基本数据类型不使用equals方法进行判断，包装数据类型不使用==进行判断

   - 【强制】BigDecimal的等值比较需要使用compareTo方法而不使用equals方法

   - 【强制】所有POJO类属性必须使用包装类并且不设定任何属性值

   - 【强制】表示日期和时间的格式new SimpleDateFormat("yyyy-MM-dd HH:mm:ss")

   - 【推荐】使用entrySet来遍历map中的KV（values方法得到的是一个V的list集合对象，keySet方法得到的是一个K的list集合对象）

   - 【强制】线程资源必须由线程池提供

   - 【强制】超过三层的if...else语句可以使用卫语句（多层的if判断语句）

   - 【推荐】可以将一个复杂的逻辑判断语句赋给一个有意义的布尔变量名从而提高代码的可读性

   - 【强制】类、类属性、类方法的注释必须使用Javadoc规范（/***/的格式）

   - 【强制】所有接口/抽象类中的方法必须要用Javadoc注释，表明该方法的功能

   - 【强制】所有的类都需要添加创建者以及创建日期

   - 【强制】所有的枚举类型字段必须要有注释，表明每个数据项的作用

   - 【强制】前后端交互的API需要明确**协议、域名、路径、请求方法、请求内容、状态码、响应体**。

   - 【强制】在前后端交互的json格式的数据中，所有的key值都以驼峰的方式进行命名

   - 【强制】对于需要使用超大整数的场景，服务器端一律使用String字符串类型返回，禁止使用Long

   - 【强制】服务器内部重定向必须使用 forward；外部重定向地址必须使用 URL 统一代理模块生成，否 则会因线上采用 HTTPS 协议而导致浏览器提示“不安全”，并且还会带来 URL 维护不一致的问题。

   - 【强制】后台输送给页面的变量必须加 $!{var} ——中间的感叹号。（如果 var 等于 null 或者不存在，那么 ${var} 会直接显示在页面上）

   - 【强制】枚举 enum（括号内）的属性字段必须是私有且不可变。

   - 【强制】事务场景中，抛出异常被 catch 后，如果需要回滚，一定要注意手动回滚事务。

   - 【强制】不要在 finally 块中使用 return

   - 【强制】应用中不可直接使用日志系统（Log4j、Logback）中的 API，而应依赖使用日志框架（SLF4J、 JCL—Jakarta Commons Logging）中的 API，使用门面模式的日志框架，有利于维护和各个类的日志处理 方式统一。

   - 【强制】在日志输出时，字符串变量之间的拼接使用占位符的方式。

   - 【强制】生产环境禁止使用 System.out 或 System.err 输出或使用 e.printStackTrace() 打印异常堆栈。

   - 【推荐】和数据库相关的单元测试，可以设定自动回滚机制，不给数据库造成脏数据。或者对单元测试 产生的数据有明确的前后缀标识。

   - 【强制】表名、字段名必须使用小写字母或数字，禁止出现数字开头禁止两个下划线中间只出现数字。数 据库字段名的修改代价很大，因为无法进行预发布，所以字段名称需要慎重考虑。

   - 【推荐】表的命名最好是遵循“业务名称_表的作用”。

   - 【强制】只能使用count(*)来统计行数

     

   

2. 在Leecode上找一些数据结构和算法的题目进行训练

   1. **数组元素积的符号**

      **题目描述：**

      已知函数 signFunc(x) 将会根据 x 的正负返回特定值：

      如果 x 是正数，返回 1 。
      如果 x 是负数，返回 -1 。
      如果 x 是等于 0 ，返回 0 。
      给你一个整数数组 nums 。令 product 为数组 nums 中所有元素值的乘积。

      返回 signFunc(product) 。

      - ```java
        class Solution {
            public int arraySign(int[] nums) {
                // 记录nums中的负数
                int sign = 0;
                for(int num : nums){
                    if(num<0){
                        sign++;
                    }else if(num == 0){
                        return 0;
                    }
                }
                if(sign%2 == 1){
                    return -1;
                }
                return 1;
            }
        }
        ```

        

   2. **两数之和**

      **题目描述**：

      给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target  的那 两个 整数，并返回它们的数组下标。

      你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

      你可以按任意顺序返回答案。

      1. 穷举法

         ```java
         class Solution {
             public int[] twoSum(int[] nums, int target) {
                 int n = nums.length;
                 for(int i = 0; i < n-1; i++){
                     for(int j = i+1; j < n; j++){
                         if(nums[i] + nums[j] == target){
                             return new int[]{i,j};
                         }
                     }
                 }
                 return null;
             }
         }
         ```

         

      2. HashMap存储法

         ```java
         class Solution {
             public int[] twoSum(int[] nums, int target) {
                 int n = nums.length;
                 HashMap<Integer, Integer> map = new HashMap<>();
                 // 存储值
                 for(int i = 0; i < n; i++){
                     map.put(target - nums[i], i);
                 }
                 
                 // 检验
                 for(int i = 0; i < n; i++){
                     int num = nums[i];
                     // 判断是否包含指定的key值以及该key值不能为自身
                     if(map.containsKey(num) && map.get(num) != i){
                         return new int[]{i, map.get(num)};
                     }
                 }
         
                 return null;
             }
         }
         ```

         