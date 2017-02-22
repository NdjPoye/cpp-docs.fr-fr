---
title: "/NXCOMPAT (compatible avec la pr&#233;vention de l&#39;ex&#233;cution des donn&#233;es) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/NXCOMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NXCOMPAT (option de l'éditeur de liens)"
  - "NXCOMPAT (option de l'éditeur de liens)"
  - "-NXCOMPAT (option de l'éditeur de liens)"
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /NXCOMPAT (compatible avec la pr&#233;vention de l&#39;ex&#233;cution des donn&#233;es)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique qu'un fichier exécutable a été testé pour sa compatibilité avec la fonctionnalité de prévention de l'exécution des données de Windows.  
  
## Syntaxe  
  
```  
/NXCOMPAT[:NO]  
```  
  
## Notes  
 **\/NXCOMPAT** est activé par défaut.  
  
 **\/NXCOMPAT:NO** peut être utilisé pour spécifier explicitement un fichier exécutable comme étant non compatible avec la prévention de l'exécution des données.  
  
 Pour plus d'informations sur la prévention de l'exécution des données, consultez ces articles :  
  
-   [Une description détaillée de la fonctionnalité de Prévention de l'exécution des données \(DEP\)](http://go.microsoft.com/fwlink/?LinkID=157771) dans l'aide Microsoft et sur l'assistance web.  
  
-   [Prévention de l'exécution des données](http://go.microsoft.com/fwlink/?LinkID=157770) sur le site Web MSDN  
  
-   [Prévention de l'exécution des données \(fenêtres incorporées\)](http://go.microsoft.com/fwlink/?LinkID=157768) sur le site Web MSDN  
  
### Pour définir cette option de l'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)