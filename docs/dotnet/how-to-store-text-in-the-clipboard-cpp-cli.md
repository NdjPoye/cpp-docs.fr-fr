---
title: "Comment&#160;: stocker du texte dans le Presse-papiers (C++/CLI) | Microsoft Docs"
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
  - "Presse-papiers, stocker du texte"
  - "texte, stocker dans le Presse-Papiers"
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: stocker du texte dans le Presse-papiers (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise l'objet <xref:System.Windows.Forms.Clipboard> défini dans l'espace de noms <xref:System.Windows.Forms> pour stocker une chaîne.  Cet objet fournit deux fonctions membres : <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> et <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.  Les données sont stockées dans le Presse\-papiers en envoyant tout objet dérivé de <xref:System.Object> à <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.  
  
## Exemple  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Comment : récupérer du texte du Presse\-papiers](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)