---
title: "&lt;binaryMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;binaryMessageEncoding&gt;
定义一个在网络上以二进制形式对 Windows Communication Foundation \(WCF\) 消息进行编码的二进制消息编码器。  
  
## 语法  
  
```  
  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10” />  
```  
  
## 特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### 特性  
  
|特性|描述|  
|--------|--------|  
|maxReadPoolSize|一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。  池越大，系统允许的活动峰值就越大，但工作集也会随之增大。  默认值为 64。|  
|maxSessionSize|一个正整数，设置用于编码的缓冲区的大小（字节）。  较大的缓冲区能够提高编码速度，代价是增加了工作集的大小。  默认值为 2048。|  
|maxWritePoolSize|一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。  池越大，系统允许的活动峰值就越大，但工作集也会随之增大。  默认值为 16。|  
|messageVersion|指定使用的或预期的 SOAP 消息和 WS\-Addressing 版本。|  
  
### 子元素  
  
|元素|描述|  
|--------|--------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。  此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。|  
  
### 父元素  
  
|元素|描述|  
|--------|--------|  
|[\<绑定\>](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## 备注  
 编码是将消息转换为一个字节序列的过程。  解码是反向过程。  Windows Communication Foundation \(WCF\) 包含三种类型的 SOAP 消息编码：文本、二进制和消息传输优化机制 \(MTOM\)。  
  
 `binaryMessageEncoding` 元素为 XML 指定 .NET 二进制格式，且包含可用于指定要使用的字符编码以及 SOAP 和 WS\-Addressing 版本的选项。  二进制消息编码器在网络上以二进制形式对 Windows Communication Foundation \(WCF\) 消息进行编码。  虽然这种编码有助于非常快速地传输消息，但是丢失了基于 WS\-\* 标准的互操作性。  
  
## 示例  
  
```  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## 请参阅  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>   
 [消息编码](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [选择消息编码器](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [绑定](../../../../../docs/framework/wcf/bindings.md)   
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)