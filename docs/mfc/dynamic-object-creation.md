---
title: "Cr&#233;ation d&#39;objet dynamique | Microsoft Docs"
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
  - "CObject (classe), création d'objet dynamique"
  - "création d'objet dynamique"
  - "création d'objet, dynamiquement au moment de l'exécution"
  - "objets (C++), créer dynamiquement au moment de l'exécution"
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;objet dynamique
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment créer un objet dynamiquement pendant l'exécution.  La procédure utilise les informations de classe d'exécution, comme décrit dans l'article [Informations sur l'accès aux classes d'exécution](../mfc/accessing-run-time-class-information.md).  
  
#### Pour créer dynamiquement un objet étant donné sa classe d'exécution  
  
1.  Utilisez le code suivant pour créer dynamiquement un objet à l'aide de la fonction `CreateObject` de `CRuntimeClass`.  Notez qu'en cas de échec, `CreateObject` retourne **NULL** au lieu de déclencher une exception :  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/CPP/dynamic-object-creation_1.cpp)]  
  
## Voir aussi  
 [Utilisation de CObject](../mfc/using-cobject.md)