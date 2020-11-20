flask `app = Flask(__name__, static_folder="frontend/dist", template_folder="frontend/dist")`这样配置时，flask对于静态资源的路由会默认加上'dist'，因此，如果前端的页面里路由的是'http://locahost:5000/js/chunk-ec4cd624.c6da4346.js' 时，会导致找不到资源

有两种方式可以解决，一个是添加一个参数static_url_path=''，见https://blog.csdn.net/Likianta/article/details/89363973 ，这样，后端的路由就没有dist了，因此可以访问'http://locahost:5000/js/chunk-ec4cd624.c6da4346.js'

但是，这种方式会导致所有的路由都去找static_folder里的资源，如果写了接口，就会导致接口解析不到，因此不能用这种方法

所以要从前端修改，让前端去找'http://locahost:5000/dist/js/chunk-ec4cd624.c6da4346.js' 的资源，vue-cli3.0的配置方法是在vue.config.js中配置

```
module.exports = {
  publicPath: "dist/",
};
```
