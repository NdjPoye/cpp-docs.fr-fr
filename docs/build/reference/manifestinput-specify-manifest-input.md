---
title: "/MANIFESTINPUT (Sp&#233;cifier l&#39;entr&#233;e de manifeste) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /MANIFESTINPUT (Sp&#233;cifier l&#39;entr&#233;e de manifeste)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie un fichier d'entrée manifeste à inclure dans le manifeste incorporé dans l'image.  
  
## Syntaxe  
  
```c#  
/MANIFESTINPUT:filename  
```  
  
#### Paramètres  
 `filename`  
 Fichier du manifeste à inclure dans le manifeste incorporé.  
  
## Notes  
 L'option **\/MANIFESTINPUT** spécifie le chemin d'accès d'un fichier d'entrée à utiliser pour créer le manifeste incorporé dans une image exécutable.  Si vous avez plusieurs fichiers d'entrée manifestes, utilisez le commutateur plusieurs fois \- une fois pour chaque fichier d'entrée.  Les fichiers d'entrée manifeste sont fusionnés pour créer le manifeste intégré.  Cette option requiert l'option **\/MANIFEST:EMBED**.  
  
 Cette option ne peut pas être définie directement dans [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  À la place, utilisez la propriété **Fichiers manifeste supplémentaires** du projet pour spécifier les fichiers manifeste supplémentaires à inclure.  Pour plus d'informations, consultez [Entrée et sortie, Outil Manifeste, Propriétés de configuration, boîte de dialogue Pages de propriétés de \<NomProjet\>](../../ide/input-and-output-manifest-tool.md).  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)