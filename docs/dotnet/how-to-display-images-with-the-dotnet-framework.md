---
title: "Comment&#160;: afficher des images avec le&#160;.NET Framework | Microsoft Docs"
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
  - "GDI+ (C++), afficher des images"
  - "graphiques (C++), afficher des images"
ms.assetid: c0eddfa1-4bd6-4af5-a533-1fa84b360325
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: afficher des images avec le&#160;.NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant modifie le gestionnaire d'événements OnPaint pour récupérer un pointeur vers l'objet <xref:System.Drawing.Graphics> pour le formulaire principal.  La fonction <xref:System.Windows.Forms.Form.OnPaint%2A> est destinée à une application Windows Forms, très probablement créée à l'aide d'un Assistant Application de Visual Studio.  
  
 L'image est représentée par la classe <xref:System.Drawing.Image>.  Les données image sont chargées à partir d'un fichier .jpg à l'aide de la méthode <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>.  Avant que l'image soit dessinée dans le formulaire, ce dernier est redimensionné pour pouvoir l'accueillir.  Le dessin de l'image s'effectue à l'aide de la méthode <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName>.  
  
 Les classes <xref:System.Drawing.Graphics> et <xref:System.Drawing.Image> se situent toutes les deux dans l'espace de noms <xref:System.Drawing?displayProperty=fullName>.  
  
> [!NOTE]
>  GDI\+ est fourni avec Windows XP et est disponible en tant que redistribuable pour Windows NT 4.0 SP 6, Windows 2000, Windows 98 et Windows Me.  Pour télécharger le dernier redistribuable, consultez [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Pour plus d'informations, consultez la documentation du Kit de développement GDI\+ SDK dans [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Exemple  
  
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
  
## Voir aussi  
 <xref:System.Drawing?displayProperty=fullName>   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)