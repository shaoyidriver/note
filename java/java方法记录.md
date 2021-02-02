# java

## util

### Map

#### computeIfAbsent

java8新增map取值的方式，优化了map取空值时进行新增并添加的操作；

```java
// 源码
default V computeIfAbsent(K key, Function<? super K, ? extends V> mappingFunction) {
    Objects.requireNonNull(mappingFunction);
    V v;
    if ((v = get(key)) == null) {
        V newValue;
        if ((newValue = mappingFunction.apply(key)) != null) {
            put(key, newValue);
            return newValue;
        }
    }
    return v;
}
```

操作方式对比：

```java
// java8之前。从map中根据key获取value操作可能会有下面的操作
Object val = map.get(key);
if (val == null) {
    val = new Object();
    map.put(key, val);
}

// java8之后。上面的操作可以简化为一行，若key对应的value为空，会将第二个参数的返回值存入并返回
Object val = map.computeIfAbsent(key, k -> new Object());

```

