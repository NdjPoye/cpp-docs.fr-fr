---
title: "Fichiers .ilk en tant qu&#39;entr&#233;e dans l&#39;&#233;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .ilk"
  - "fichiers ILK"
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers .ilk en tant qu&#39;entr&#233;e dans l&#39;&#233;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lors de la liaison incrémentielle, LINK met à jour le fichier d'état .ilk créé pendant le premier lien incrémentiel.  Ce fichier a le même nom de base que le fichier .exe ou .dll et porte l'extension .ilk.  Lors des liens incrémentiels suivants, LINK met à jour le fichier .ilk.  S'il est manquant, LINK établit un lien complet et crée un nouveau fichier .ilk.  S'il est inutilisable, LINK crée un lien non incrémentiel.  Pour plus d'informations sur la liaison incrémentielle, consultez l'option [\/INCREMENTAL \(lier par incrément\)](../../build/reference/incremental-link-incrementally.md).  
  
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)