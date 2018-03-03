---
title: "-/NOENTRY (aucun Point d’entrée) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5990123d809a5fdaa00e3fd44666dd3fc37c69bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Aucun point d'entrée)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>Notes  
 L'option /NOENTRY est nécessaire pour créer une DLL de ressources uniquement ne contenant aucun code exécutable. Pour plus d’informations, consultez [création d’une DLL Resource-Only](../../build/creating-a-resource-only-dll.md).  
  
 Utilisez cette option pour empêcher LINK de lier une référence à `_main` dans la DLL.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **l’éditeur de liens** dossier.  
  
3.  Sélectionnez le **avancé** page de propriétés.  
  
4.  Modifier la **aucun Point d’entrée** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’une DLL de ressource uniquement](../../build/creating-a-resource-only-dll.md)   
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)