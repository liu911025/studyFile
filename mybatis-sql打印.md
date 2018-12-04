```java
	/** 性能分析拦截器，用于输出每条 SQL 语句及其执行时间 */
	@Bean
	public PerformanceInterceptor performanceInterceptor() {
		PerformanceInterceptor performanceInterceptor = new PerformanceInterceptor();
		performanceInterceptor.setMaxTime(120000); // session 超时时限
		return performanceInterceptor;
	}
```

