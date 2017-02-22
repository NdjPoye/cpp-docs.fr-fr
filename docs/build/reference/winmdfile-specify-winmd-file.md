---
title: "/WINMDFILE (sp&#233;cifier un fichier winmd) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadataFile"
dev_langs: 
  - "C++"
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDFILE (sp&#233;cifier un fichier winmd)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie le nom du fichier de sortie au format .winmd \(métadonnées Windows Runtime\), généré par l'option de l'éditeur de liens [\/WINMD](../../build/reference/winmd-generate-windows-metadata.md).  
  
```  
  
/WINMDFILE:filename  
  
```  
  
## Notes  
 Utilisez la valeur spécifiée dans `filename` pour remplacer le nom de fichier de la valeur par défaut .winmd \(`binaryname`.winmd\).  Notez que vous n'ajoutez pas « .winmd » à `filename`. Si plusieurs valeurs sont répertoriées sur la ligne de commande de **\/WINMDFILE**, la dernière est prioritaire.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Métadonnées Windows**.  
  
4.  Dans la zone **Fichier de métadonnées Windows**, entrez l'emplacement du fichier.  
  
## Voir aussi  
 [\/WINMD \(générer des métadonnées Windows\)](../../build/reference/winmd-generate-windows-metadata.md)   
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)