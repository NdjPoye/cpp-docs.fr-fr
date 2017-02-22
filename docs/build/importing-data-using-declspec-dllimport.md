---
title: "Importation de donn&#233;es &#224; l&#39;aide de __declspec(dllimport) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) (mot clé C++)"
  - "dllimport (attribut) (C++), importations de données"
  - "importer des données (C++)"
  - "importer des DLL (C++), __declspec(dllimport)"
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Importation de donn&#233;es &#224; l&#39;aide de __declspec(dllimport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans le cas des données, l'utilisation de **\_\_declspec\(dllimport\)** est pratique car elle permet de supprimer une couche d'adressage indirect.  Lorsque vous importez des données à partir d'une DLL, vous devez encore passer par la table des adresses d'importation.   Cela signifie qu'avant l'existence de **\_\_declspec\(dllimport\)**, il fallait penser à effectuer un niveau supplémentaire d'adressage indirect lors de l'accès aux données exportées à partir de la DLL :  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 Il fallait alors exporter les données dans le fichier .DEF :  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 et y accéder depuis l'extérieur de la DLL :  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 Lorsque vous marquez les données en tant que **\_\_declspec\(dllimport\)**, le compilateur génère automatiquement le code d'adressage indirect.  Vous n'avez plus à vous préoccuper des étapes ci\-dessus.  Comme indiqué précédemment, n'utilisez pas la déclaration **\_\_declspec\(dllimport\)** sur les données lors de la génération de la DLL.  Les fonctions de la DLL n'utilisent pas la table des adresses d'importation pour accéder à l'objet de données ; le niveau supplémentaire d'adressage indirect sera donc supprimé.  
  
 Pour exporter les données automatiquement à partir de la DLL, utilisez cette déclaration :  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## Voir aussi  
 [Importation dans une application](../build/importing-into-an-application.md)