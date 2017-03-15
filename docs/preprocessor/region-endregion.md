---
title: "region, endregion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.endregion"
  - "endregion_CPP"
  - "region_CPP"
  - "vc-pragma.region"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "endregion (pragma)"
  - "pragmas, endregion"
  - "pragmas, région"
  - "region (pragma)"
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# region, endregion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le bloc **\#pragma region** vous permet de spécifier un bloc de code que vous pouvez développer ou réduire lorsque vous utilisez la [fonctionnalité mode Plan](../Topic/Outlining.md) de l'éditeur de code Visual Studio.  
  
## Syntaxe  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### Paramètres  
 `comment`\(facultatif\)  
 Commentaire qui s'affiche dans l'éditeur de code.  
  
 *name*\(facultatif\)  
 Nom de la région.  Ce nom s'affiche dans l'éditeur de code.  
  
## Notes  
 **\#pragma endregion** marque la fin d'un bloc **\#pragma region**.  
  
 Un bloc `#region` doit se terminer par **\#pragma endregion**.  
  
## Exemple  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)