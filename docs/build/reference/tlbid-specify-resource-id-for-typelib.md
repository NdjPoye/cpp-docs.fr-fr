---
title: "-TLBID (spécifier l’ID de ressource de TypeLib) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a552edab9f2de646de3b869bf84467924b5db348
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (Spécifier l'ID de ressource de TypeLib)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 `id`  
 Une valeur spécifiée par l’utilisateur pour une bibliothèque de types créée par l’éditeur de liens. Il remplace l’ID de ressource par défaut de 1.  
  
## <a name="remarks"></a>Notes  
 Lorsque la compilation d’un programme qui utilise des attributs, l’éditeur de liens crée une bibliothèque de types. L’éditeur de liens affecte un ID de ressource de 1 à la bibliothèque de types.  
  
 Si cet ID de ressource est en conflit avec l’un de vos ressources existantes, vous pouvez spécifier un autre ID avec /TLBID. La plage de valeurs que vous pouvez passer à `id` est comprise entre 1 et 65535.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **IDL incorporé** page de propriétés.  
  
4.  Modifier la **ID de ressource de TypeLib** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)