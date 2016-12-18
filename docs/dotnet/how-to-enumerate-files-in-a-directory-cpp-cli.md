---
title: "Comment&#160;: &#233;num&#233;rer les fichiers d&#39;un r&#233;pertoire (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "répertoires (C++), lister les fichiers"
  - "fichiers (C++), lister les fichiers"
ms.assetid: ebfc2666-229f-4b94-a9a1-e8f1b5d946d6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;num&#233;rer les fichiers d&#39;un r&#233;pertoire (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment récupérer la liste des fichiers dans un répertoire.  En outre, les sous\-répertoires sont énumérés.  L'exemple de code suivant utilise les méthodes <xref:System.IO.Directory.GetFiles%2A>, <xref:System.IO.Directory.GetFiles%2A> et <xref:System.IO.Directory.GetDirectories%2A> pour afficher le contenu du répertoire C:\\Windows.  
  
## Exemple  
  
```  
// enum_files.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ folder = "C:\\";  
   array<String^>^ dir = Directory::GetDirectories( folder );  
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);  
   for (int i=0; i<dir->Length; i++)  
      Console::WriteLine(dir[i]);  
  
   array<String^>^ file = Directory::GetFiles( folder );  
   Console::WriteLine("--== Files inside '{0}' ==--", folder);  
   for (int i=0; i<file->Length; i++)  
      Console::WriteLine(file[i]);  
  
   return 0;  
}  
```  
  
## Voir aussi  
 [Fichier et flux de données E\/S](../Topic/File%20and%20Stream%20I-O.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)