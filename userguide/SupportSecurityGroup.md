# 安全组支持

开通安全组的用户在创建集群和新增节点时，会有如下选项框：

![](/images/userguide/安全组2.png)

如果选择` 暂不启用 `，则创建防火墙类型的节点，跟原先一致

如果选择` 安全组 `选项，则会选择安全组，此处可以选择的安全组的规则模板必须为` UK8S模板 `，参考如下（图来自[安全组产品页面](https://console.ucloud.cn/vpc/secgroup)下新建安全组）：
![](/images/userguide/安全组3.png)

规则模板中对应的安全组规则如下：

![](/images/userguide/安全组.png)
 
 如果需要使用其他类型的规则模板，则可以将目标节点的主机在安全组页面上手动绑定安全组（对于已有节点也可以这样进行操作），或者使用该模板创建云主机uhost正常启动后将其作为添加已有主机加入集群
 
 针对这种修改了安全组配置的情况，也请尽可能保证将` UK8S模板 `中的规则应用到您的自定义安全组规则下，否则可能会影响集群正常使用，

> 由于启用了安全组后网络策略变为白名单模式，所以请勿在安全组页面上将uk8s的节点的所有安全组规则解绑，这可能会导致uk8s集群网络异常