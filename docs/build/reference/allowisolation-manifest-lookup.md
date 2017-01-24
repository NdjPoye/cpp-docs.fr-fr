---
title: "/ALLOWISOLATION (Recherche de manifeste) | Microsoft Docs"
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
  - "/ALLOWISOLATION"
  - "VC.Project.VCLinkerTool.AllowIsolation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION (option de l'éditeur de liens)"
  - "-ALLOWISOLATION (option de l'éditeur de liens)"
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWISOLATION (Recherche de manifeste)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie le comportement de recherche du fichier manifeste.  
  
## Syntaxe  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## Notes  
 **\/ALLOWISOLATION:NO** indique que les DLL sont chargées comme s'il n'existait aucun manifeste et demande à l'éditeur de liens de définir le bit `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` dans le champ `DllCharacteristics` de l'en\-tête facultatif.  
  
 **\/ALLOWISOLATION** demande au système d'exploitation de rechercher et de charger des manifestes.  
  
 **\/ALLOWISOLATION** est la valeur par défaut.  
  
 Lorsque l'isolation est désactivée pour un fichier exécutable, le chargeur Windows ne tente pas de rechercher un manifeste d'application pour le processus créé récemment.  Le nouveau processus ne possédera pas de contexte d'activation par défaut, même s'il existe un manifeste à l'intérieur du fichier exécutable ou dans le même répertoire que le fichier exécutable portant le nom *executable\-name***.exe.manifest**.  
  
 Pour plus d'informations, consultez la [référence des fichiers manifeste](http://msdn.microsoft.com/library/aa375632).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Fichier manifeste**.  
  
5.  Modifiez la propriété **Autoriser l'isolation**.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)