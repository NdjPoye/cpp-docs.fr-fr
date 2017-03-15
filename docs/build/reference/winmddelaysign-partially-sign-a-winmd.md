---
title: "/WINMDDELAYSIGN (signer partiellement un winmd) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDDelaySign"
dev_langs: 
  - "C++"
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDDELAYSIGN (signer partiellement un winmd)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie la signature partielle d'un fichier de métadonnées Windows Runtime \(.winmd\) en mettant la clé publique dans un fichier.  
  
```  
  
/WINMDDELAYSIGN[:NO]  
  
```  
  
## Notes  
 Ressemble à l'option de l'éditeur de liens [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) appliquée au fichier .winmd.  Utilisez **\/WINMDDELAYSIGN** si vous souhaitez inclure uniquement la clé publique dans le fichier .winmd.  Par défaut, l'éditeur de liens se comporte comme si les **\/WINMDDELAYSIGN:NO** ont été spécifiés ; autrement dit, il ne signe pas le fichier winmd.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Métadonnées Windows**.  
  
4.  Dans la zone de liste déroulante **Indications de Délais sur les Métadonnées Windows**, sélectionnez l'option désirée.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)