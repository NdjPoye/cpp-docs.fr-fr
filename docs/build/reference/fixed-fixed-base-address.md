---
title: "/FIXED (Adresse de base fixe) | Microsoft Docs"
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
  - "/fixed"
  - "VC.Project.VCLinkerTool.FixedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FIXED (option de l'éditeur de liens)"
  - "FIXED (option de l'éditeur de liens)"
  - "-FIXED (option de l'éditeur de liens)"
  - "adresse de base préférée pour télécharger un programme"
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FIXED (Adresse de base fixe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FIXED[:NO]  
```  
  
## Notes  
 Indique au système d'exploitation de charger le programme uniquement à son adresse de base préférée.  Si l'adresse de base préférée est introuvable, le système d'exploitation ne charge pas le fichier.  Pour plus d'informations, consultez [\/BASE \(Adresse de base\)](../../build/reference/base-base-address.md).  
  
 Par défaut, \/FIXED:NO est la valeur par défaut fixée pou une DLL, \/FIXED étant celle de tout autre type de projet.  
  
 Lorsque \/FIXED est spécifié, LINK ne génère pas de section de réadressage dans le programme.  Au moment de l'exécution, si le système d'exploitation ne parvient pas à charger le programme à cette adresse, il génère un message d'erreur et ne charge pas le programme.  
  
 Spécifiez \/FIXED:NO pour générer une section de réadressage dans le programme.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Tapez le nom de l'option et son paramètre dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)