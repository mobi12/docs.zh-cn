---
title: "如何：使用 EdmGen.exe 生成模型和映射文件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 741da2e7f69d5f8fa54f07046d88fec9cf722dbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>如何：使用 EdmGen.exe 生成模型和映射文件
本主题描述如何使用 EDM 生成器 (EdmGen.exe) 工具生成以下文件（基于 School 数据库）：  
  
-   概念模型（.csdl 文件）。  
  
-   存储模型（.ssdl 文件）。  
  
-   概念模型与存储模型之间的映射（.msl 文件）。  
  
-   使用 Visual Basic 或 C# 的对象层代码。  
  
-   视图文件。  
  
 EdmGen.exe 工具使用 /mode:FullGeneration 生成上面列出的文件。 有关 EdmGen.exe 命令的详细信息，请参阅[EDM 生成器 (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md)。  
  
 如果使用 EdmGen.exe 生成模型和映射文件，则仍需要将 [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 项目配置为使用[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]。 有关详细信息，请参阅[如何： 手动配置实体框架项目](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)。  
  
> [!NOTE]
>  由 EdmGen.exe 生成的概念模型包含数据库中所有对象。 如果希望生成仅包含特定对象的概念模型，请使用实体数据模型向导。 有关详细信息，请参阅[如何： 使用实体数据模型向导](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>使用 EdmGen.exe 为 Visual Basic 项目生成 School 模型  
  
1.  创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。  
  
2.  在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>使用 EdmGen.exe 为 C# 项目生成 School 模型  
  
1.  创建 School 数据库。 有关详细信息，请参阅[创建 School 示例数据库](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)。  
  
2.  在命令提示符下执行以下命令（无换行符）：  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [建模和映射](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [如何： 手动配置实体框架项目](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [如何： 预生成视图来提高查询性能](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [ADO.NET 实体数据模型工具](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [如何： 使用 EdmGen.exe 验证模型和映射文件](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
