---
title: "/ALIGN (Alignement des sections) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Alignment"
  - "/align"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALIGN (option de l'éditeur de liens)"
  - "ALIGN (option de l'éditeur de liens)"
  - "-ALIGN (option de l'éditeur de liens)"
  - "alignement des sections"
  - "sections"
  - "sections, spécifier l'alignement"
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /ALIGN (Alignement des sections)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALIGN[:number]  
```  
  
## Notes  
 où :  
  
 `number`  
 Valeur d'alignement.  
  
## Notes  
 L'option \/ALIGN spécifie l'alignement de chaque section au sein de l'espace d'adressage linéaire du programme.  L'argument `number`, exprimé en octets, doit être une puissance de deux.  La valeur par défaut est 4 Ko \(4096\).  L'éditeur de liens émet un avertissement si l'alignement génère une image non valide.  
  
 Vous ne devez pas modifier l'alignement, sauf si vous écrivez une application telle qu'un pilote de périphérique.  
  
 Il est possible de modifier l'alignement d'une section donnée à l'aide du paramètre d'alignement de l'option [\/SECTION](../../build/reference/section-specify-section-attributes.md).  
  
 La valeur d'alignement spécifiée ne peut être inférieure à la valeur d'alignement la plus grande de la section.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)