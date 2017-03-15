---
title: "Comment&#160;: dessiner des formes avec le .NET Framework | Microsoft Docs"
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
  - "dessiner, formes"
  - "GDI+, dessiner des formes"
  - "formes"
  - "formes, dessiner"
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: dessiner des formes avec le .NET Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise la classe <xref:System.Drawing.Graphics> pour modifier le gestionnaire d'événements <xref:System.Windows.Forms.Form.OnPaint%2A> afin de récupérer un pointeur vers l'objet <xref:System.Drawing.Graphics> pour le formulaire principal.  Ensuite, ce pointeur est utilisé pour définir la couleur d'arrière\-plan du formulaire et dessiner une ligne ainsi qu'un arc à l'aide des méthodes <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> et <xref:System.Drawing.Graphics.DrawArc%2A>.  
  
> [!NOTE]
>  GDI\+ est fourni avec Windows XP et est disponible en tant que redistribuable pour Windows NT 4.0 SP 6, Windows 2000, Windows 98 et Windows Me.  Pour télécharger le dernier redistribuable, consultez [http:\/\/go.microsoft.com\/fwlink\/?linkid\=11232](http://go.microsoft.com/fwlink/?linkid=11232).  Pour plus d'informations, consultez [GDI\+](_gdiplus_GDI_start_cpp).  
  
## Exemple  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## Voir aussi  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System.Drawing \(espace de noms\)](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)