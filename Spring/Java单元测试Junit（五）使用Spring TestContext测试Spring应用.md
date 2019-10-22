**Java单元测试Junit（五）使用Spring TestContext测试Spring应用**

*https://my.oschina.net/wangdaoliang/blog/1203884*



JUnit 4 开始使用 Java 5 中的注解（annotation），常用的几个 annotation 介绍： 
`@BeforeClass：针对所有测试，只执行一次，且必须为static void` 
`@Before：初始化方法` 
`@Test：测试方法，在这里可以测试期望异常和超时时间` 
`@After：释放资源` 
`@AfterClass：针对所有测试，只执行一次，且必须为static void` 
`@Ignore：忽略的测试方法`

一个单元测试用例执行顺序为： `@BeforeClass –> @Before –> @Test –> @After –> @AfterClass` 

每一个测试方法的调用顺序为：` @Before –> @Test –> @After`

