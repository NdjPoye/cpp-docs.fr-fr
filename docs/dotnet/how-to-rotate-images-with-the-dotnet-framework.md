---
title: "Comment&#160;: faire pivoter des images avec le&#160;.NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI+ (C++), faire pivoter des images"
  - "graphiques (C++), faire pivoter des images"
ms.assetid: e32104d5-87d0-47a9-a22f-9bc835b7e8d7
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: faire pivoter des images avec le&#160;.NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'utilisation de la classe <xref:System.Drawing.Image?displayProperty=fullName> pour charger une image à partir du disque, la faire pivoter de 90 degrés et l'enregistrer en tant que nouveau fichier .jpg.  
  
> [!NOTE]
>  GDI\+ est fourni avec Windows XP et est disponible en tant que redistribuable pour Windows NT 4.0 SP 6, Windows 2000, Windows 98 et Windows Millennium Edition.  Pour télécharger le dernier redistribuable, consultez [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Pour plus d'informations, consultez [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Exemple  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );  
   image->Save("SampleImage_rotated.jpg");  
   return 0;  
}  
```  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)