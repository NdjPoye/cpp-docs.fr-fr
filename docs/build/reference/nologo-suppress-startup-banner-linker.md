---
title: "/NOLOGO (Suppression de la banni&#232;re de d&#233;marrage) (&#201;diteur de liens) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.SuppressStartupBanner"
  - "/nologo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOLOGO (option de l'éditeur de liens)"
  - "bannières, supprimer au démarrage"
  - "message de copyright"
  - "NOLOGO (option de l'éditeur de liens)"
  - "-NOLOGO (option de l'éditeur de liens)"
  - "supprimer la bannière de démarrage (option de l'éditeur de liens)"
  - "numéros de version, empêcher l'affichage de l'éditeur de liens"
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOLOGO (Suppression de la banni&#232;re de d&#233;marrage) (&#201;diteur de liens)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOLOGO  
```  
  
## Notes  
 L'option \/NOLOGO empêche l'affichage du message de copyright et du numéro de version.  
  
 Cette option supprime également la reproduction en écho des fichiers de commande.  Pour plus d'informations, consultez [Fichiers de commandes LINK](../../build/reference/link-command-files.md).  
  
 Par défaut, l'éditeur de liens envoie ces informations à la fenêtre Sortie.  Sur la ligne de commande, ces informations sont envoyées à la sortie standard et peuvent être redirigées vers un fichier.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Cette option s'exécute uniquement à partir de la ligne de commande.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Cette option n'est pas modifiable par programme.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)