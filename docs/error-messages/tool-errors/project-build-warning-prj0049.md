---
title: "Avertissement de g&#233;n&#233;ration de projet PRJ0049 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0049"
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement de g&#233;n&#233;ration de projet PRJ0049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La cible référencée '\<Reference\>' nécessite au minimum le .NET Framework \<VersionMinFramework\> et ne pourra pas s'exécuter sur le .NET Framework cible de ce projet.  
  
 Les applications créées en utilisant [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] peuvent spécifier quelle version de [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] elles doivent cibler.  Si vous ajoutez une référence à un assembly ou à un projet qui dépend d'une version de [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)]qui est ultérieure à la version ciblée, vous obtiendrez cet avertissement à la compilation.  
  
### Pour traiter cet avertissement  
  
1.  Choisissez l'une des valeurs suivantes :  
  
    -   Modifiez le Framework ciblé dans la boîte de dialogue **Pages de propriétés** du projet afin qu'il soit ultérieur ou égal à la version de Framework minimale de tous les assemblys et projets référencés.  Pour plus d'informations, consultez [Ajout de références](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Supprimez la référence à l'assembly ou au projet qui a une version de Framework minimale ultérieure au Framework ciblé.  Ces éléments seront marqués avec une icône d'avertissement dans les  **Pages de propriétés**du projet.  
  
## Voir aussi  
 [Erreurs et avertissements de génération de projet \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)