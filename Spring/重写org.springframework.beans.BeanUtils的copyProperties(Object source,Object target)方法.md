**重写org.springframework.beans.BeanUtils的copyProperties(Object source,Object target)方法**
*https://blog.csdn.net/liangshishen/article/details/28951451*



在使用BEAN对象接收数据时，其中populate、copyProperties方法可以正常使用，但data数据类型出现异常，不支持java.util.Date类型，用ConvertUtils.register进行转换处理：

```java
ConvertUtils.register(new Converter() {

  public Date convert(Class type, Object value) {

  // 内部类：value接收data转换成string类型

  if (value != null) {

   try {

   // SimpleDateFormat中的parse方法可以 把String型的字符串转换成特定格式的date类

   return new SimpleDateFormat("yyyy-MM-dd").parse(value.toString());

   } catch (ParseException e) {

   e.printStackTrace();

   }

  }

  return null;

  }

 }, Date.class);
```
