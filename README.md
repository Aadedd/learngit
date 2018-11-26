# 1.django中使用cookies
    1.设置cookies的值
      语法：
        响应对象.set_cookies(key,value,exprise)
          key:cookies的名字
          values:cookies的值
          exprise:保存时间，以s为单位
        e.g.
            响应对象.set_cookies('uname','tom',60*60*24*365)
        响应对象：
          1.HttpResponse
            resp=HttpResponse("给客户端的一句话")
            resp.set_cookies('key','value',exprise)
            return resp
          2.render()
            resp=render(request,'xxx.html',locals())
            resp.set_cookies('key','value',exprise)
            return resp
          3.HttpResponseRedirect/redirect
            resp=redirect('/地址/')
            resp.set_cookies('key','value',exprise)
            return resp
    2.获取cookies的值
        通过request.COOKIES获取当前站点
