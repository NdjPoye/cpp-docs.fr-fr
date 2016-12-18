---
title: "/NOENTRY (Aucun point d&#39;entr&#233;e) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ResourceOnlyDLL"
  - "/noentry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOENTRY (option de l'éditeur de liens C++)"
  - "DLL (C++), créer"
  - "points d'entrée (C++), spécifier dans l'éditeur de liens"
  - "NOENTRY (option de l'éditeur de liens)"
  - "-NOENTRY (option de l'éditeur de liens)"
  - "DLL de ressources uniquement (C++), créer"
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOENTRY (Aucun point d&#39;entr&#233;e)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOENTRY  
```  
  
## Notes  
 L'option \/NOENTRY est nécessaire pour créer une DLL de ressources uniquement ne contenant aucun code exécutable.  Pour plus d'informations, consultez [Création d'une DLL de ressource uniquement](../../build/creating-a-resource-only-dll.md).  
  
 Utilisez cette option pour empêcher LINK de lier une référence à `_main` dans la DLL.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Aucun point d'entrée**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.  
  
## Voir aussi  
 [Création d'une DLL de ressource uniquement](../../build/creating-a-resource-only-dll.md)   
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)