---
title: "Comment : afficher des Images avec le .NET Framework | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- GDI+ [C++], displaying images
- graphics [C++], displaying images
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f50659832e04c3b8938c50bedc47b3ac770a52eb
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-display-images-with-the-net-framework"></a>Comment : afficher des images avec le .NET Framework
L’exemple de code suivant modifie le Gestionnaire d’événements OnPaint pour récupérer un pointeur vers le <xref:System.Drawing.Graphics> objet pour le formulaire principal. Le <xref:System.Windows.Forms.Form.OnPaint%2A> fonction est conçue pour une application Windows Forms, très probablement créée avec l’Assistant application Visual Studio.  
  
 L’image est représentée par la <xref:System.Drawing.Image> classe. Les données d’image sont chargées à partir d’un fichier .jpg à l’aide du <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> (méthode). Avant que l’image est dessinée au formulaire, le formulaire est redimensionné pour s’adapter à l’image. Le dessin de l’image est effectué avec la <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> (méthode).  
  
 Le <xref:System.Drawing.Graphics> et <xref:System.Drawing.Image> classes sont toutes deux dans le <xref:System.Drawing?displayProperty=fullName> espace de noms.  
  
## <a name="example"></a>Exemple  
  
```  
#using <system.drawing.dll>  
  
using namespace System;  
using namespace System::Drawing;  
  
protected:  
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override  
{  
    Graphics^ g = pe->Graphics;  
    Image^ image = Image::FromFile("SampleImage.jpg");  
    Form::ClientSize = image->Size;  
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Drawing?displayProperty=fullName>   
 [Programmation .NET avec C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)