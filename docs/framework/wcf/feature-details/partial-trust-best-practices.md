---
title: "部分信任最佳实践"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 74b1bd42472da61497124a04620aa02af25b32bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="partial-trust-best-practices"></a>部分信任最佳实践
本主题描述在部分信任环境中运行 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 时的最佳实践。  
  
## <a name="serialization"></a>序列化  
 当在部分受信任的应用程序中使用 <xref:System.Runtime.Serialization.DataContractSerializer> 时，请应用以下做法。  
  
-   必须使用 `[DataContract]` 属性显式标记所有可序列化类型。 在部分信任环境中不支持以下技术：  
  
-   使用 <xref:System.SerializableAttribute> 标记要序列化的类。  
  
-   实现 <xref:System.Runtime.Serialization.ISerializable> 接口以允许类控制其序列化过程。  
  
### <a name="using-datacontractserializer"></a>使用 DataContractSerializer  
  
-   使用 `[DataContract]` 属性标记的所有类型都必须是公共的。 在部分信任环境中无法序列化非公共类型。  
  
-   可序列化 `[DataContract]` 类型中的所有 `[DataContract]` 成员都必须是公共的。 在部分信任环境中无法序列化具有非公共 `[DataMember]` 的类型。  
  
-   必须将处理序列化事件的方法（如 `OnSerializing`、`OnSerialized`、`OnDeserializing` 和 `OnDeserialized`）声明为公共的。 但是，同时支持 <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> 的显式实现和隐式实现。  
  
-   在程序集中实现的、使用 `[DataContract]` 标记的 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 类型不得在类型构造函数中执行与安全相关的操作，因为在反序列化期间 <xref:System.Runtime.Serialization.DataContractSerializer> 不调用新实例化的对象的构造函数。 具体说来，对于 `[DataContract]` 类型，必须避免使用以下常见安全技术：  
  
-   尝试通过使类型的构造函数变为内部或私有来限制部分信任访问。  
  
-   通过将 `[LinkDemand]` 添加到类型的构造函数来限制对该类型的访问。  
  
-   假定由于已成功实例化对象，构造函数强制执行的任何验证检查已成功通过。  
  
### <a name="using-ixmlserializable"></a>使用 IXmlSerializable  
 以下最佳实践适用于实现 <xref:System.Xml.Serialization.IXmlSerializable> 且使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化的类型：  
  
-   <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> 静态方法实现必须为 `public`。  
  
-   实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口的实例方法必须为 `public`。  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a>从允许来自部分受信任的调用方的调用的完全受信任平台代码使用 WCF  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 部分信任安全性模型假定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 公共方法或属性的任何调用方在承载应用程序的代码访问安全性 (CAS) 上下文中运行。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 还假定对于每个 <xref:System.AppDomain> 只存在一个应用程序安全性上下文，并由受信任的主机（例如，通过调用 <xref:System.AppDomain> 或由 ASP.NET 应用程序管理器）在 <xref:System.AppDomain.CreateDomain%2A> 创建时建立此上下文。  
  
 此安全模型适用于无法断言其他 CAS 权限的用户编写应用程序，如在 Medium Trust ASP.NET 应用程序中运行的用户代码。 但是，在代表部分受信任的应用程序调用到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中时，必须当心完全受信任的平台代码（例如，在全局程序集缓存中安装并接受来自部分受信任代码的调用的第三方程序集），以免引入应用程序级安全漏洞。  
  
 在代表部分受信任的代码调用 <xref:System.Security.PermissionSet.Assert%2A> API 之前，完全信任代码应该避免更改当前线程的 CAS 权限集（通过调用 <xref:System.Security.PermissionSet.PermitOnly%2A>、<xref:System.Security.PermissionSet.Deny%2A> 或 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 更改）。 断言、拒绝或通过其他方式创建特定于线程且独立于应用程序级安全上下文的权限上下文可能会导致意外行为。 根据应用程序，此行为可能会导致应用程序级安全漏洞。  
  
 必须准备好使用线程特定的权限上下文调用到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的代码，才能处理可能出现的以下情况：  
  
-   在操作期间可能未维护线程特定的安全上下文，这导致潜在的安全异常。  
  
-   内部 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 代码以及用户提供的任何回调均可能在与最初启动调用所在的安全上下文不同的安全上下文中运行。 这些上下文包括：  
  
    -   应用程序权限上下文。  
  
    -   其他用户线程以前创建的任何线程特定的权限上下文，用于在当前正在运行的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的生存期内调入 <xref:System.AppDomain>。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可保证部分受信任的代码无法获取完全信任权限，除非此类权限在调入 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 公共 API 中之前已由完全受信任的组件断言。 但是，它不保证断言完全信任的效果隔离到特定的线程、操作或用户操作。  
  
 作为最佳实践，避免通过调用 <xref:System.Security.PermissionSet.Assert%2A>、<xref:System.Security.PermissionSet.PermitOnly%2A> 或 <xref:System.Security.PermissionSet.Deny%2A> 创建线程特定的权限上下文。 而是对应用程序本身授予或拒绝特权，以便不需要 <xref:System.Security.PermissionSet.Assert%2A>、<xref:System.Security.PermissionSet.Deny%2A> 或 <xref:System.Security.PermissionSet.PermitOnly%2A>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Xml.Serialization.IXmlSerializable>
