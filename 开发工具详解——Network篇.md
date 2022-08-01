# chrome开发工具详解——Network篇

> Network 面板记录页面上每个网络操作的相关信息，包括详细的耗时数据、HTTP 请求与响应标头和 Cookie，等等。

## 一、Network面板概览

<img src="C:\Users\wangrj32319\AppData\Roaming\Typora\typora-user-images\image-20211229201547667.png" alt="image-20211229201547667" style="zoom: 67%;" />

## 二、Network组成部分的作用

1. **控制器**：控制面板的外观与功能。

   ![image-20220228201613586](D:\typora笔记\工作遇到的问题\img\2016)

2. **过滤器**：过滤请求列表中显示的资源，然后点击过滤器可以同时选择多个过滤器。

3. **网页截图信息**：看见页面加载过程的显示内容，如果追求性能和体验的极致，那就需要通过这个去分析。

4. **时间线**：显示获取到资源的时间轴信息。

5. **详情列表**：默认时间排序，可选择显示列。可以看到所有的资源请求，包括网络请求，图片资源，html,css，js文件等请求，可以根据需求筛选请求项，一般多用于网络请求的查看和分析，分析后端接口是否正确传输，获取的数据是否准确，请求头，请求参数的查看。

   1. Name 资源名称，点击名称可以查看资源的详情情况，包括Headers、Preview、Response、Cookies、Timing。
   2. Status HTTP状态码。
   3. Type 请求的资源MIME类型,MIME是Multipurpose Internet Mail Extensions (html,css,js等)。
   4. Initiator 标记请求是由哪个对象或进程发起的（请求源）它可能有以下几种值：
      1. Parser（解析器）：请求是由页面的html解析时发送
      2. Redirect（重定向）：请求是由页面重定向发送
      3. Script（脚本）：请求是由script脚本处理发送
      4. other : 请求是由其他过程发送的，比如页面里的Link链接点击
   5. Size 从服务器下载的文件和请求的资源大小。如果是从缓存中取得的资源则该列会显示(from cache)
   6. Time 请求或下载的时间，从发起Request到获取到Response所用的总时间。
   7. Watefall显示所有网络请求的可视化瀑布流(时间状态轴)，点击时间轴，可以查看该请求的详细信息，点击列头则可以根据指定的字段可以排序。

   **鼠标右键单击，添加其他列：**

   <img src="https://img-blog.csdnimg.cn/20190719144710435.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTk0ODA3NQ==,size_16,color_FFFFFF,t_70" alt="在这里插入图片描述" style="zoom: 33%;" />

   **还可以自定义header头：**

   <img src="https://img-blog.csdnimg.cn/20190719150023680.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTk0ODA3NQ==,size_16,color_FFFFFF,t_70" alt="在这里插入图片描述" style="zoom:33%;" />

   

   

   **通过点击某个资源的Name可以查看该资源的详细信息，根据选择的资源类型显示的信息也不太一样，可能包括如下Tab信息：**

   1. Headers 该资源的HTTP头信息。
   2. Preview 根据你所选择的资源类型（JSON、图片、文本）显示相应的预览。
   3. Response 显示HTTP的Response信息。
   4. Cookies 显示资源HTTP的Request和Response过程中的Cookies信息。
   5. Timing 显示资源在整个请求生命周期过程中各部分花费的时间。

   **对某一请求右键点击：**

   <img src="D:\typora笔记\工作遇到的问题\img\2025" alt="image-20220228202530675" style="zoom: 80%;" />

   - Copy Request Headers：复制HTTP请求头到系统剪贴板

   - Copy Response Headers：复制HTTP响应头到系统剪贴板

   - Copy Response：复制HTTP响应内容到系统剪贴板

   - Copy as
     cURL：将网络请求作为一个curl的命令字符复制到系统剪贴板(curl是一种开源的命令行工具和库，用于配合url语法进行数据传输)

   - Copy All as HAR：将网络请求记录信息以HAR格式复制到系统剪贴板(what is HAR file)

   - Save as HAR with Content：将资源的所有的网络信息保存到HAR文件中(.har文件)

   - Clear Browser Cache：清除浏览器缓存

   - Clear Browser Cookies：清除浏览器cookies

   - Open in Sources Panel：当前选中资源在Sources面板打开

   - Open Link in New Tab：在新tab打开资源链接

   - Copy Link Address：复制资源url到系统剪贴板

6. **下载信息**： 显示请求总数、总数据量、总花费时间等。

