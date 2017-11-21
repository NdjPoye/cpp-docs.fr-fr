---
title: "-HEAP (définir la taille du tas) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs: C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 702b8dfa6561d79f8ea9bf496e9652f89c8d34f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="heap-set-heap-size"></a>/HEAP (Définir la taille des tas)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>Remarques  
 L’option /HEAP définit la taille du segment de mémoire en octets. Cette option est uniquement pour une utilisation lors de la création d’un fichier .exe.  
  
 Le *réserver* argument spécifie l’allocation totale des tas dans la mémoire virtuelle. La taille de segment de mémoire par défaut est 1 Mo. L’éditeur de liens arrondit la valeur spécifiée aux plus proche de 4 octets.  
  
 Le paramètre facultatif `commit` argument est soumis à l’interprétation par le système d’exploitation. Dans Windows NT et Windows 2000, il spécifie la quantité de mémoire physique à allouer à la fois. Mémoire virtuelle dédiée, espace à réserver dans le fichier d’échange. Un degré plus élevé `commit` valeur fait gagner du temps quand l’application requiert davantage d’espace du tas, mais augmente les besoins en mémoire et éventuellement le temps de démarrage.  
  
 Spécifiez le *réserver* et `commit` les valeurs dans la notation décimale ou en langage C.  
  
 Cette fonctionnalité est également disponible via un fichier de définition de module avec [HEAPSIZE](../../build/reference/heapsize.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **système** page de propriétés.  
  
4.  Modifier la **taille de la validation du tas** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)