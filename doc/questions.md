
### RequestQueue
每个request在加进队列（RequestQueue.add(Request)）的时候，Request会把设置它的队列（Request.setRequestQueue))。然后在Request处理结束的时候，会调用requestQueue.finish(Request)。然后RequestQueue会继续处理下一个Request

### NetworkDispatcher

### HttpStack

### Network



### Volley 启动
在开始时，需要


目测 CacheDispatcher负责把请求进行排队，而NetworkDispatcher负责做实际的处理。

HurlStack和HttpClientStack都实现了HttpStack，这个才是真正负责网络请求的类。

BasicNetwork实现了Network接口，对HttpStack进行封装，如对错误码的封装，对超时之后进行重试的操作。

NetworkDispatcher是一条网络请求线程，它不断地从网络队列里面取出一个请求，然后用Network进行实际请求，然后把返回的结果用ResponseDelivery进行提交。

ExecutorDelivery实现了ResponseDelivery接口，它里面也有一个线程池，默认它是由主线程进行处理的。


