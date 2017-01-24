---
title: "Comment&#160;: r&#233;cup&#233;rer du texte du Presse-papiers (C++/CLI) | Microsoft Docs"
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
  - "Presse-papiers, récupérer du texte"
  - "texte, récupérer du Presse-papiers"
ms.assetid: 99e77ba0-8573-4030-92d8-de8aa7623ee4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: r&#233;cup&#233;rer du texte du Presse-papiers (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant utilise la fonction membre <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> pour retourner un pointeur vers l'interface <xref:System.Windows.Forms.IDataObject>.  Ensuite, cette interface peut faire l'objet d'une requête visant à connaître le format de données et être utilisée pour récupérer les données réelles.  
  
## Exemple  
  
```  
// read_clipboard.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.Drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main( )  
{  
   IDataObject^ data = Clipboard::GetDataObject( );  
  
   if (data)  
   {  
      if (data->GetDataPresent(DataFormats::Text))   
      {  
         String^ text = static_cast<String^>  
           (data->GetData(DataFormats::Text));  
         Console::WriteLine(text);   
      }  
      else  
         Console::WriteLine("Nontext data is in the Clipboard.");  
   }  
   else   
   {  
      Console::WriteLine("No data was found in the Clipboard.");  
   }  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Opérations Windows](../dotnet/windows-operations-cpp-cli.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)