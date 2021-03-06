---
title: "如何：使用 VideoDrawing 播放媒体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2753db8e06c8c1b50c6e5cee17330d421e88511f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a>如何：使用 VideoDrawing 播放媒体
若要播放的音频或视频文件，你可以使用<xref:System.Windows.Media.VideoDrawing>和<xref:System.Windows.Media.MediaPlayer>。 加载并播放媒体有两种方法。 第一种是使用<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>通过本身，，第二种方法是创建你自己<xref:System.Windows.Media.MediaTimeline>用于<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>。  
  
> [!NOTE]
>  当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.VideoDrawing>和<xref:System.Windows.Media.MediaPlayer>播放视频文件一次。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 若要获得其他计时控制媒体，使用<xref:System.Windows.Media.MediaTimeline>与<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>对象。 <xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复视频。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.MediaTimeline>与<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>对象用于重复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意，当你使用<xref:System.Windows.Media.MediaTimeline>，你使用交互式<xref:System.Windows.Media.Animation.ClockController>从返回<xref:System.Windows.Media.Animation.Clock.Controller%2A>属性<xref:System.Windows.Media.MediaClock>控制而不是交互式的方法的媒体播放<xref:System.Windows.Media.MediaPlayer>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.VideoDrawing>  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
