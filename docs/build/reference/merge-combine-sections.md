---
title: "/MERGE (Combiner des sections) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/merge"
  - "VC.Project.VCLinkerTool.MergeSections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MERGE (option de l'éditeur de liens)"
  - "MERGE (option de l'éditeur de liens)"
  - "-MERGE (option de l'éditeur de liens)"
  - "sections"
  - "sections, combiner"
  - "sections, affecter des noms"
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MERGE (Combiner des sections)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MERGE:from=to  
```  
  
## Notes  
 L'option \/MERGE fusionne la première section \(*from*\) avec la seconde \(*to*\), en nommant le résultat *to*.  Par exemple, `/merge:.rdata=.text`.  
  
 Si la seconde section n'existe pas, LINK renomme la section *from* en *to*.  
  
 Cette option est utile pour créer des VxD et pour substituer les noms de sections générés par le compilateur.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Fusion des sections**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)