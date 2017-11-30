---
title: "ISymUnmanagedDispose 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDispose
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDispose
helpviewer_keywords: ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 12e0d9c2cec1f9fc8439a9b9434e1eff506f8d7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="b3afd-102">ISymUnmanagedDispose 接口</span><span class="sxs-lookup"><span data-stu-id="b3afd-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="b3afd-103">释放非托管资源。</span><span class="sxs-lookup"><span data-stu-id="b3afd-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3afd-104">方法</span><span class="sxs-lookup"><span data-stu-id="b3afd-104">Methods</span></span>  
  
|<span data-ttu-id="b3afd-105">方法</span><span class="sxs-lookup"><span data-stu-id="b3afd-105">Method</span></span>|<span data-ttu-id="b3afd-106">描述</span><span class="sxs-lookup"><span data-stu-id="b3afd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3afd-107">Destroy 方法</span><span class="sxs-lookup"><span data-stu-id="b3afd-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="b3afd-108">导致要释放所有内部引用，并在任何后续方法调用返回失败的基础对象。</span><span class="sxs-lookup"><span data-stu-id="b3afd-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3afd-109">要求</span><span class="sxs-lookup"><span data-stu-id="b3afd-109">Requirements</span></span>  
 <span data-ttu-id="b3afd-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b3afd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3afd-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3afd-111">See Also</span></span>  
 [<span data-ttu-id="b3afd-112">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="b3afd-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)