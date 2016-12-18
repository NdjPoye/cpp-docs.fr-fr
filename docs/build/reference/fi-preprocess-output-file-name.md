---
title: "/Fi (pr&#233;traiter le nom du fichier de sortie) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fi (option du compilateur C++)"
  - "Fi (option du compilateur C++)"
  - "-Fi (option du compilateur C++)"
  - "prétraiter les fichiers de sortie, nom du fichier"
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fi (pr&#233;traiter le nom du fichier de sortie)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie le nom du fichier de sortie dans lequel l'option de compilateur [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md) écrit la sortie prétraitée.  
  
## Syntaxe  
  
```  
/Fipathname  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`pathname`|Nom et chemin d'accès du fichier de sortie produit par l'option de compilateur **\/P**.|  
  
## Notes  
 Utilisez l'option du compilateur **\/Fi** en association avec l'option du compilateur **\/P**.  
  
 Si vous spécifiez uniquement un chemin d'accès pour le paramètre `pathname`, le nom de base du fichier source est utilisé comme nom de base du fichier de sortie prétraité.  Le paramètre `pathname` ne requiert pas d'extension de nom de fichier particulière.  Toutefois, une extension de « .i » est utilisée si vous ne spécifiez pas d'extension de nom de fichier.  
  
## Exemple  
 La ligne de commande suivante prétraite PROGRAM.cpp, conserve les commentaires, ajoute des directives [\#line](../../preprocessor/hash-line-directive-c-cpp.md) et écrit le résultat dans le fichier MYPROCESS.i.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [\/P \(Prétraiter jusqu'à un fichier\)](../../build/reference/p-preprocess-to-a-file.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)