# 注解及controller层

## 注解的理解与使用

1. @RestController:综合了ResponseBody和Controller两个注解其中

   - controller标记此类
   - responsebody用于将return的字符串直接作为响应体返回,也可以将java对象转为json格式作为响应体返回
2. @RequestMapping,@GetMapping及@PostMapping:后两注解为@RequestMapping派生,故@RequestMapping更加通用,但也可以通过method:指定请求方式
("/...")可以指定url路径(请求行)以处理特定路径请求

3. @PathVariable:("/{}")为占位符,可以获取占位符所传的参数(在请求行中)

4. @RequestParam:作用同上,但格式?参数名=...(可通过required属性配置可选参数,即可以不传递的参数)

5. @RequestBody:获取请求体的内容json内容需配置对应Java对象

## controller层与http

1. Get与Post请求方式之间的最大不同为Post方式会多传递请求体,而Get只有请求行与请求头.
2. @RequestBody注解则可以获取请求体中的内容
3. @PathVariable与@RequestParam注解则获取请求行中对应的内容(格式对应)
4. mapping("/...")可以指定请求路径
5. return返回数据则由@RestController中的@response注解处理