---
title: "-DEFAULTLIB (spécifier la bibliothèque par défaut) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs: C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40fe07543dd9dc65d93cc9f79504f5fd324204dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Spécifier la bibliothèque par défaut)
```  
/DEFAULTLIB:library  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 *bibliothèque*  
 Le nom d’une bibliothèque à rechercher lors de la résolution des références externes.  
  
## <a name="remarks"></a>Notes  
 L’option /DEFAULTLIB ajoute une *bibliothèque* à la liste des bibliothèques que LINK recherche lors de la résolution des références. Une bibliothèque spécifiée avec /DEFAULTLIB est recherchée après les bibliothèques spécifiées sur la ligne de commande et avant les bibliothèques par défaut nommées dans les fichiers .obj.  
  
 Le [ignorer toutes les bibliothèques par défaut](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB) substitue/DEFAULTLIB :*bibliothèque*. Le [ignorer les bibliothèques](../../build/reference/nodefaultlib-ignore-libraries.md) (/ NODEFAULTLIB :*bibliothèque*) substitue/DEFAULTLIB :*bibliothèque* lors de la même *bibliothèque* nom est spécifié dans les deux.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
-   Cette option de l’éditeur de liens n’est pas disponible à partir de l’environnement de développement Visual Studio. Pour ajouter une bibliothèque à la phase de liaison, utilisez la **dépendances supplémentaires** propriété à partir de la **entrée** page de propriétés.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)