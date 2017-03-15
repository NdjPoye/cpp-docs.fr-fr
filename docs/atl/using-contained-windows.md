---
title: "Using Contained Windows | Microsoft Docs"
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
helpviewer_keywords: 
  - "ATL, fenêtres"
  - "contained windows in ATL"
  - "windows [C++], ATL"
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using Contained Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les outils ATL contenaient des fenêtres à [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md).  Une fenêtre contenue représente une fenêtre qui délègue ses messages à un objet conteneur au lieu de les gérer dans sa propre classe.  
  
> [!NOTE]
>  Vous n'avez pas besoin de dériver une classe d' `CContainedWindowT` pour utiliser les fenêtres contenues.  
  
 Avec les fenêtres contenues, vous pouvez surclassement les fenêtres existantes classe ou sous\-classe une fenêtre existante.  Pour créer une fenêtre que les surclasse les fenêtres existantes fichier, spécifier d'abord le nom de classe existant dans le constructeur de l'objet d' `CContainedWindowT` .  Appelez ensuite `CContainedWindowT::Create`.  Sous\-classer une fenêtre existante, vous n'avez pas besoin de spécifier un nom de classe de fenêtre \(exécution **NULL** au constructeur\).  Appelez simplement la méthode d' `CContainedWindowT::SubclassWindow` avec le handle à la fenêtre est sous\-classée.  
  
 Vous utilisez généralement des fenêtres contenues comme données membres d'une classe de conteneur.  Le conteneur n'a pas besoin d'être une fenêtre ; toutefois, il doit dériver de [CMessageMap](../atl/reference/cmessagemap-class.md).  
  
 Une fenêtre contenue peut utiliser des tables des messages secondaires pour gérer ses messages.  Si vous avez plusieurs fenêtre contenue, vous devez déclarer plusieurs tables des messages secondaires, chacune correspondant à une fenêtre contenue distincte.  
  
## Exemple  
 Voici un exemple d'une classe de conteneur avec deux fenêtres contenues :  
  
 [!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/CPP/using-contained-windows_1.h)]  
  
 Pour plus d'informations sur les fenêtres contenues, consultez l'exemple de [SUBEDIT](../top/visual-cpp-samples.md) .  
  
## Voir aussi  
 [classes de fenêtre](../atl/atl-window-classes.md)