---
title: "Relation avec l&#39;API du langage C | Microsoft Docs"
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
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "livres (C++)"
  - "livres (C++), à propos du Kit de développement logiciel (SDK) Windows et MFC"
  - "MFC (C++), API Windows"
  - "Visual C, API Windows (appels)"
  - "API Windows (C++), et MFC"
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Relation avec l&#39;API du langage C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La caractéristique unique qui sépare la bibliothèque Microsoft Foundation Class \(MFC\) des autres bibliothèques de classes pour Windows est le mappage très proche à l'API Windows écrit en langage C.  De plus, vous pouvez généralement combiner les appels de la bibliothèque de classes librement avec des appels directs dans l'API Windows.  Cet accès direct, toutefois, n'implique pas que les classes sont un remplacement complet de cette API.  Les développeurs doivent toujours, occasionnellement, effectuer des appels directs à certaines fonctions Windows, telles que [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) et [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) par exemple.  Une fonction Windows est encapsulée par une méthode de la classe lorsqu'il existe un avantage à le faire.  
  
 Comme vous devez parfois effectuer des appels de fonction de Windows, vous devez avoir accès à la documentation API Windows du langage C.  Cette documentation est incluse avec Microsoft Visual C\+\+.  
  
> [!NOTE]
>  Pour une vue d'ensemble du fonctionnement du modèle de bibliothèque MFC, consultez [Utilisation des classes pour l'écriture d'applications Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## Voir aussi  
 [Philosophie générale de conception des classes](../mfc/general-class-design-philosophy.md)