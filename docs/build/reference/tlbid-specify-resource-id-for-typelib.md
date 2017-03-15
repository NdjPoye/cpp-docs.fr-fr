---
title: "/TLBID (Sp&#233;cifier l&#39;ID de ressource de TypeLib) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/tlbid"
  - "VC.Project.VCLinkerTool.TypeLibraryResourceID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .tlb, spécifier l'ID de ressource"
  - "/TLBID (option de l'éditeur de liens)"
  - "fichiers tlb, spécifier l'ID de ressource"
  - "TLBID (option de l'éditeur de liens)"
  - "-TLBID (option de l'éditeur de liens)"
  - "bibliothèques de types, spécifier l'ID de ressource"
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /TLBID (Sp&#233;cifier l&#39;ID de ressource de TypeLib)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBID:id  
```  
  
## Notes  
 où :  
  
 `id`  
 désigne une valeur spécifiée par l'utilisateur pour une bibliothèque de types créée par l'éditeur de liens.  Elle substitue l'ID de ressource par défaut de 1.  
  
## Notes  
 Lors de la compilation d'un programme utilisant des attributs, l'éditeur de liens va créer une bibliothèque de types.  L'éditeur de liens va assigner l'ID de ressource 1 à la bibliothèque de types.  
  
 Si cet ID de ressource entre en conflit avec l'une de vos ressources existantes, vous pouvez spécifier un autre ID à l'aide de \/TLBID.  La plage de valeurs que vous pouvez passer à l'`id` est comprise entre 1 et 65 535.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **IDL incorporé**.  
  
4.  Modifiez la propriété **ID de ressource de typelib**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)