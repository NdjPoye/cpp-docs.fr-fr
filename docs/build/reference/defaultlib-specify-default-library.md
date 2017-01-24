---
title: "/DEFAULTLIB (Sp&#233;cifier la biblioth&#232;que par d&#233;faut) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.DefaultLibraries"
  - "/defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DEFAULTLIB (option de l'éditeur de liens)"
  - "DEFAULTLIB (option de l'éditeur de liens)"
  - "-DEFAULTLIB (option de l'éditeur de liens)"
  - "bibliothèques, ajouter à la liste de"
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DEFAULTLIB (Sp&#233;cifier la biblioth&#232;que par d&#233;faut)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEFAULTLIB:library  
```  
  
## Notes  
 où :  
  
 *bibliothèque*  
 désigne le nom d'une bibliothèque à rechercher lors de la résolution des références externes.  
  
## Notes  
 L'option \/DEFAULTLIB ajoute une *bibliothèque* à la liste des bibliothèques que LINK recherche lors de la résolution des références.  Une bibliothèque spécifiée à l'aide de l'option \/DEFAULTLIB est recherchée après les bibliothèques spécifiées sur la ligne de commande et avant les bibliothèques par défaut nommées dans les fichiers .obj.  
  
 L'option [Ignorer toutes les bibliothèques par défaut](../../build/reference/nodefaultlib-ignore-libraries.md) \(\/NODEFAULTLIB\) substitue \/DEFAULTLIB:*library*.  L'option [Ignorer les bibliothèques](../../build/reference/nodefaultlib-ignore-libraries.md) \(\/NODEFAULTLIB:*library*\) substitue \/DEFAULTLIB:*library* lorsque le même nom de bibliothèque \(*library*\) est spécifié dans les deux.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
-   Cette option de l'éditeur de liens n'est pas disponible dans l'environnement de développement Visual Studio.  Pour ajouter une bibliothèque à la phase de liaison, utilisez la propriété **Dépendances supplémentaires** dans la page de propriétés **Entrée**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)