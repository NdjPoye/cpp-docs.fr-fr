---
title: "Exceptions : exceptions dans les constructeurs | Microsoft Docs"
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
  - "constructeurs [C++], exceptions"
  - "exceptions, dans les constructeurs"
  - "lever des exceptions, dans les constructeurs"
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions : exceptions dans les constructeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En levant une exception dans un constructeur, nettoyez tout objet et allocations de mémoire que vous avez effectués avant de lever une exception, comme expliqué dans [Exceptions : Lever des exceptions à vos propres fonctions](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).  
  
 En levant une exception dans un constructeur, la mémoire de l'objet lui\-même a déjà été validée avant que le constructeur soit appelé.  Par conséquent, le compilateur libèrera automatiquement la mémoire occupée par l'objet après que l'exception est levée.  
  
 Pour plus d'informations, consultez [Exceptions : Libération des objets dans les exceptions](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)