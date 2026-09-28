# 解题思路与代码

```java
@RestController
@RequestMapping("/lrbackend")
public class LrbackendController {
    @RequestMapping
    public String hello(){
        System.out.println("hello world");
        return "hello world";
    }

    @PostMapping("/post")
    public String post(){
        System.out.println("hello post world");
        return "hello post world";
    }

    @RequestMapping("/json")
    public jsonResponse jsonHello(){
        return new jsonResponse("hello world","hello post world");
    }

    @GetMapping("/get/{name}")
    public String getName(@PathVariable String name){
        System.out.println("hello,"+name);
        return "hello,"+name;
    }

    @PostMapping("/post/{name}")
    public String postName(@PathVariable String name){
        System.out.println(name+",nice to meet you");
        return name+",nice to meet you";
    }

    @PostMapping("/post/json")
    public String postJsonName(@RequestBody Name name){
        System.out.println(name.getName()+",nice to meet you");
        return name.getName()+",nice to meet you";
    }
}
```

1. 配置一个<mark>请求处理类@RestController</mark>接收前端的请求
2. **请求方法**

   - @RequestMapping通用各种请求方式
   - @PostMapping接收post方式
   - @GetMapping接收get方式
   - @DeleteMapping(没用到)

3. hello world 及hello post world只需使用对应的注解即可
4. return json格式则需要新建一个javabean类,new一个对象,返回时因<u>@RestController注解会自动转为json格式返回前端</u>
5. 想接收前端的参数可以用两种注解,这里使用@PathVariable
<u>@GetMapping("/get/<mark>{name}</mark>")在方法前写上这个注解</u>
例如:localhost:8080/lrbackend/get/noy,noy则为{name}的内容
**此时在方法参数处以@PathVariable String name接收并使用**
   - <mark>@PathVariable</mark>
   - @RequestParam

6. 接收json格式数据则**需要@RequestBody注解**
<u>json格式数据接收需要对应的javabean类</u>
@RequestBody Name name接收
通过name.getter方法取出