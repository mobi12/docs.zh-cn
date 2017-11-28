---
title: "ICorDebugThread4::HadUnhandledException 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.HadUnhandledException Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ea29fa02e74c204cde003b18520bf512b0d21d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="b15ea-102">ICorDebugThread4::HadUnhandledException 方法</span><span class="sxs-lookup"><span data-stu-id="b15ea-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="b15ea-103">指示线程是否曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b15ea-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="b15ea-104">Syntax</span></span>  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b15ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="b15ea-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="b15ea-106">[out]指向的地址的有序枚举[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="b15ea-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b15ea-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b15ea-107">Return Value</span></span>  
 <span data-ttu-id="b15ea-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="b15ea-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b15ea-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b15ea-109">HRESULT</span></span>|<span data-ttu-id="b15ea-110">描述</span><span class="sxs-lookup"><span data-stu-id="b15ea-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b15ea-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b15ea-111">S_OK</span></span>|<span data-ttu-id="b15ea-112">线程已自创建以来未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b15ea-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="b15ea-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b15ea-113">S_FALSE</span></span>|<span data-ttu-id="b15ea-114">线程永远不会具有未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b15ea-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15ea-115">备注</span><span class="sxs-lookup"><span data-stu-id="b15ea-115">Remarks</span></span>  
 <span data-ttu-id="b15ea-116">此方法指示线程是否曾有过未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b15ea-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="b15ea-117">按时间触发未经处理的异常回调时或启动本机 JIT 附加时，此方法确保若要返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b15ea-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="b15ea-118">不能保证， [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)方法将返回未经处理的异常; 但是，它将如果进程不尚未继续出现未经处理的异常回调后，还是在时本机 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="b15ea-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="b15ea-119">此外，它有可能 （尽管可能性不大） 具有多个线程在本机 JIT 附加触发时未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b15ea-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="b15ea-120">在这种情况下没有方法来确定哪个异常触发 JIT 附加。</span><span class="sxs-lookup"><span data-stu-id="b15ea-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b15ea-121">要求</span><span class="sxs-lookup"><span data-stu-id="b15ea-121">Requirements</span></span>  
 <span data-ttu-id="b15ea-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b15ea-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b15ea-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b15ea-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b15ea-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b15ea-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b15ea-125">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b15ea-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15ea-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b15ea-126">See Also</span></span>  
 [<span data-ttu-id="b15ea-127">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="b15ea-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="b15ea-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="b15ea-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b15ea-129">调试</span><span class="sxs-lookup"><span data-stu-id="b15ea-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)