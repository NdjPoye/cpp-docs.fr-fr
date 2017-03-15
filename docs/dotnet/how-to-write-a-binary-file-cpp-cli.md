---
title: "Comment&#160;: &#233;crire un fichier binaire (C++/CLI) | Microsoft Docs"
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
  - "fichiers binaires, écrire en C++"
  - "fichiers (C++), binaire"
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: &#233;crire un fichier binaire (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant illustre l'écriture de données binaires dans un fichier.  Deux classes de l'espace de noms <xref:System.IO> sont utilisées : <xref:System.IO.FileStream> et <xref:System.IO.BinaryWriter>.  <xref:System.IO.FileStream> représente le fichier réel, tandis que <xref:System.IO.BinaryWriter> fournit une interface vers le flux de données qui autorise l'accès binaire.  
  
 L'exemple de code suivant écrit un fichier qui contient des entiers au format binaire.  Ce fichier peut être lu à l'aide du code fourni dans la rubrique [Comment : lire un fichier binaire](../dotnet/how-to-read-a-binary-file-cpp-cli.md).  
  
## Exemple  
  
```  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  
  
## Voir aussi  
 [Fichier et flux de données E\/S](../Topic/File%20and%20Stream%20I-O.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)