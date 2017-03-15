---
title: "Comment&#160;: lire un fichier binaire (C++/CLI) | Microsoft Docs"
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
  - "fichiers binaires, lire en C++"
  - "fichiers (C++), binaire"
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: lire un fichier binaire (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment lire des données binaires à partir d'un fichier, en utilisant deux classes de l'espace de noms <xref:System.IO?displayProperty=fullName> : <xref:System.IO.FileStream> et <xref:System.IO.BinaryReader>.  <xref:System.IO.FileStream> représente le fichier réel.  <xref:System.IO.BinaryReader> fournit une interface au flux de données qui autorise l'accès binaire.  
  
 L'exemple de code lit un fichier nommé data.bin, qui contient des entiers au format binaire.  Pour plus d'informations sur ce type de fichier, consultez [Comment : écrire un fichier binaire](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
## Exemple  
  
```  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
  
## Voir aussi  
 [Fichier et flux de données E\/S](../Topic/File%20and%20Stream%20I-O.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)