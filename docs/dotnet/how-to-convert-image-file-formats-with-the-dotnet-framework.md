---
title: "Comment : convertir des Formats de fichier d’Image avec le .NET Framework | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: 5d5384b0-b9b7-4262-b9ad-c4cb95f75ee4
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dc2b84063c509cd870b5d02fa0a209b511d8a0f3
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-convert-image-file-formats-with-the-net-framework"></a>Comment : convertir des fichiers au format image avec le .NET Framework
L’exemple de code suivant montre la <xref:System.Drawing.Image?displayProperty=fullName> classe et le <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> énumération utilisée pour convertir et enregistrer des fichiers image. Le code suivant charge une image à partir d’un fichier .jpg et puis l’enregistre dans des formats de fichier .gif et .bmp.  
  
> [!NOTE]
>  GDI + est fourni avec Windows XP, Windows Server 2003 et Windows Vista et est disponible en tant que redistribuable pour Windows 2000. Pour télécharger le redistribuable le plus récent, consultez [http://go.microsoft.com/fwlink/p/?linkid=11232](http://go.microsoft.com/fwlink/p/?linkid=11232).   
  
## <a name="example"></a>Exemple  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
using namespace System::Drawing::Imaging;  
  
int main()  
{  
   Image^ image = Image::FromFile("SampleImage.jpg");  
   image->Save("SampleImage.png", ImageFormat::Png);  
   image->Save("SampleImage.bmp", ImageFormat::Bmp);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Drawing>   
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)