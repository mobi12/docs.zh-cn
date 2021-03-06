---
title: "SoundPlayer 类概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6df44df3582ed806d338e2d4565c5c11f69ce21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="soundplayer-class-overview"></a>SoundPlayer 类概述
<xref:System.Media.SoundPlayer> 类使你能够轻松地将声音纳入应用程序。  
  
 <xref:System.Media.SoundPlayer>类，可以播放.wav 格式，从资源或 UNC 或 HTTP 位置的声音文件。 此外，<xref:System.Media.SoundPlayer>类使你能够加载或以异步方式播放声音。  
  
 还可使用 <xref:System.Media.SystemSounds> 类播放常见的系统声音，包括提示音。  
  
## <a name="commonly-used-properties-methods-and-events"></a>常用的属性、方法和事件  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> 属性|声音的文件路径或 Web 地址。 可接受的值可以是 UNC 或 HTTP。|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> 属性|程序引发异常前等待加载声音的毫秒数。 默认值为 10 秒。|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> 属性|一个指示声音是否加载完毕的布尔值。|  
|<xref:System.Media.SoundPlayer.Load%2A> 方法|同步加载声音。|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> 方法|开始异步加载声音。 加载完成后，它会发出<xref:System.Media.SoundPlayer.OnLoadCompleted%2A>事件。|  
|<xref:System.Media.SoundPlayer.Play%2A> 方法|播放声音中指定<xref:System.Media.SoundPlayer.SoundLocation%2A>或<xref:System.Media.SoundPlayer.Stream%2A>在新线程中的属性。|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> 方法|播放声音中指定<xref:System.Media.SoundPlayer.SoundLocation%2A>或<xref:System.Media.SoundPlayer.Stream%2A>当前线程中的属性。|  
|<xref:System.Media.SoundPlayer.Stop%2A> 方法|停止当前播放的任何声音。|  
|<xref:System.Media.SoundPlayer.LoadCompleted>事件|尝试加载声音后引发。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
