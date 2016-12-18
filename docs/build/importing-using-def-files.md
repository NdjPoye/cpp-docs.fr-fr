---
title: "Importation &#224; l&#39;aide de fichiers DEF | Microsoft Docs"
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
  - "fichiers .def (C++), importer avec"
  - "fichiers def (C++), importer avec"
  - "dllimport (attribut) (C++), fichiers DEF"
  - "DLL (C++), fichiers DEF"
  - "importer des DLL (C++), fichiers DEF"
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Importation &#224; l&#39;aide de fichiers DEF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous choisissez d'utiliser **\_\_declspec\(dllimport\)** en même temps qu'un fichier .def, vous devez modifier le fichier .def de façon à utiliser DATA à la place de CONSTANT afin de réduire le risque d'un problème dû à un code incorrect :  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 Le tableau suivant en indique la raison.  
  
|Mot clé|Résultats dans la bibliothèque d'importation|Exportations|  
|-------------|--------------------------------------------------|------------------|  
|`CONSTANT`|`_imp_ulDataInDll_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 Lorsque vous utilisez **\_\_declspec\(dllimport\)** et CONSTANT, vous obtenez à la fois la version `imp` et le nom non décoré dans la bibliothèque d'importation de la DLL .lib qui est créée pour permettre la liaison explicite.  Lorsque vous utilisez **\_\_declspec\(dllimport\)** et DATA, vous obtenez uniquement la version `imp` du nom.  
  
 Si vous utilisez CONSTANT, vous pouvez utiliser l'une des constructions de code suivantes pour accéder à `ulDataInDll` :  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 ou  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Cependant, si vous utilisez DATA dans le fichier .def, seul le code compilé à l'aide de la définition suivante peut accéder à la variable `ulDataInDll` :  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 Il est plus risqué d'utiliser CONSTANT car si vous oubliez d'utiliser le niveau supplémentaire d'adressage indirect, vous pourriez éventuellement accéder au pointeur de la table des adresses d'importation désignant la variable — mais pas à la variable elle\-même.  Ce type de problème apparaît souvent en tant que violation d'accès car la table des adresses d'importation est déclarée en lecture seule par le compilateur et l'éditeur de liens.  
  
 L'éditeur de liens de Visual C\+\+ émet un avertissement s'il constate la présence de CONSTANT dans le fichier .def pour rendre compte de ce cas.  Vous n'avez réellement de raison valable d'utiliser CONSTANT que si vous ne pouvez pas recompiler un fichier objet quelconque dans lequel le fichier d'en\-tête ne répertorie pas **\_\_declspec\(dllimport\)** sur le prototype.  
  
## Voir aussi  
 [Importation dans une application](../build/importing-into-an-application.md)