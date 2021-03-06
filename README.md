# etcd4j: Java binding for etcd

A more powerful and stable Java client library for the awesome etcd, a highly available key value store. This library is based on Apache HttpAsyncClient, provides async api. It supports all key based etcd requests, adds request redirect handler and retry handler, which is really useful when you put etcd into production cluster.**This library has been used in real production for period of time.**

## Download


### Maven

```
<dependency>
    <groupId>com.xqbase</groupId>
    <artifactId>etcd4j</artifactId>
    <version>1.2</version>
</dependency>
```
### Gradle

```
compile 'com.xqbase:etcd4j:1.2'
```
## Usage

Check out the [EtcdClientTest.java] for more details about how to use this library, but here's a quick code example:

```
EtcdClient client = new EtcdClient(URI.create("http://127.0.0.1:4001"));

String key = "/message";
// set the key
client.set(key, "beepboop");
// get the value of the key
String value = client.get(key);
Assert.assertEquals("beepboop", value);
// delete the key
client.delete(key);
value = client.get(key);
Assert.assertNull(value);
```
## Licence

(The MIT License)

Copyright (c) 2010 [TonyAdo]

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[EtcdClientTest.java]: https://github.com/AdoHe/etcd4j/blob/master/src/test/java/com/westudio/java/etcd/EtcdClientTest.java
[TonyAdo]: https://github.com/AdoHe