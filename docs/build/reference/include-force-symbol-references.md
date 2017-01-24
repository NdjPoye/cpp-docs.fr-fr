---
title: "/INCLUDE (Forcer les r&#233;f&#233;rences des symboles) | Microsoft Docs"
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
  - "/include"
  - "VC.Project.VCLinkerTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCLUDE (option de l'éditeur de liens)"
  - "références des symboles forcées (option de l'éditeur de liens)"
  - "INCLUDE (option de l'éditeur de liens)"
  - "-INCLUDE (option de l'éditeur de liens)"
  - "forcer les références des symboles (éditeur de liens)"
  - "symboles, ajouter à la table des symboles"
ms.assetid: 4a039677-360a-480f-bd0b-448e239b449c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INCLUDE (Forcer les r&#233;f&#233;rences des symboles)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCLUDE:symbol  
```  
  
## Notes  
 où :  
  
 `symbol`  
 spécifie un symbole à ajouter à la table des symboles.  
  
## Notes  
 L'option \/INCLUDE indique à l'Éditeur de liens d'ajouter un symbole spécifié à la table de symboles.  
  
 Pour spécifier plusieurs symboles, tapez une virgule \(,\), un point\-virgule \(;\) ou un espace entre les noms de symboles.  Sur la ligne de commande, spécifiez \/INCLUDE:`symbol` une fois pour chaque symbole.  
  
 L'éditeur de liens résout `symbol` en ajoutant l'objet contenant la définition du symbole au programme.  Cette fonctionnalité est utile pour inclure un objet de la bibliothèque qui, sinon, ne serait pas lié au programme.  
  
 La spécification d'un symbole avec cette option substitue la suppression de ce symbole par [\/OPT:REF](../../build/reference/opt-optimizations.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Modifiez la propriété **Références des symboles forcées**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ForceSymbolReferences%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)