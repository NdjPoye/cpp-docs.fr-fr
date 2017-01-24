---
title: "/MACHINE (Sp&#233;cifier la plate-forme cible) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TargetMachine"
  - "/machine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MACHINE (option de l'éditeur de liens)"
  - "MACHINE (option de l'éditeur de liens)"
  - "-MACHINE (option de l'éditeur de liens)"
  - "fichiers de mappage, créer avec l'éditeur de liens"
  - "plate-forme cible"
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MACHINE (Sp&#233;cifier la plate-forme cible)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## Notes  
 L'option \/MACHINE spécifie la plateforme cible du programme.  
  
 En règle générale, il n'est pas nécessaire de spécifier l'option \/MACHINE.  LINK déduit le type d'ordinateur à partir des fichiers .obj.  Il arrive cependant que LINK ne puisse pas déterminer le type d'ordinateur ; une [erreur des outils Éditeur de liens LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md) est alors émise  Si une telle erreur se produit, spécifiez \/MACHINE.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Ordinateur cible**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)